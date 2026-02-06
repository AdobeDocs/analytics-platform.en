---
title: Field-based Stitching
description: Explains of the concept and working of field-based stitching.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: e5cb55e7-aed0-4598-a727-72e6488f5aa8
---
# Field-based stitching

In field-based stitching, you specify an event dataset as well as the persistent ID (cookie) and person ID for that dataset. Field-based stitching attempts to make the person ID info available for Customer Journey Analytics data analysis, on any anonymous events coming with a specific persistent ID.  That info is retrieved from the rows that have a person ID for that specific persistent ID.

If the person ID info cannot be retrieved for an event, the persistent ID is used instead for that *unstitched* event. As a result, in a [data view](/help/data-views/data-views.md) that is associated with a [connection](/help/connections/overview.md) that contains the dataset enabled for stitching, the person ID component contains either the person ID value or persistent ID value at the event level.

You can use field-based stitching when using Customer Journey Analytics as a standalone solution (not having access to the Experience Platform Identity Service and associated identity graph). Or, when you do not want to use the available identity graph.

![Field-based stitching](/help/stitching/assets/fbs.png)


## IdentityMap

Field-based stitching supports the use of the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) in the following scenarios:

- Use of the primary identity in `identityMap` namespaces to define the persistentID:
  - If multiple primary identities are found in different namespaces, the identities in the namespaces are sorted lexicographically, and the first identity is selected.
  - If multiple primary identities are found in a single namespace, the first lexicographical available primary identity is selected.
  
  In the example below, the namespaces and identities result in a sorted primary identities list, and finally the selected identity.

  <table style="table-layout:auto">
     <tr>
       <th>Namespaces</th>
       <th>Identities list</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>&nbsp;]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Sorted identities list</th>
      <th>Selected identity</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>PrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-2", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-1", "namespace": "ECID"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "namespace": "ECID"}<br/>]<br/>NonPrimaryIdentities [<br/>&nbsp;&nbsp;{"id": "ccid-1", "namespace": "CCID"},<br/>&nbsp;&nbsp;{"id": "ecid-3", "namespace": "ECID"}<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ccid-2",<br/>"namespace": "CCID"</code></pre></td>
    </tr>
  </table>


- Use of `identityMap` namespace to define either the persistent ID or person ID or both:
  - If multiple values for persistent ID or person ID are found in an `identityMap` namespace, the first lexicographical available value is used.
  - Namespaces for persistent ID and person ID have to be mutually exclusive.

  In the example below, you have selected ECID as the namespace to use. That selection results in a sorted identities list, and finally the selected identity.

    <table style="table-layout:auto">
     <tr>
       <th>Namespaces</th>
       <th>Identities list</th>
     </tr>
     <tr>
       <td>ECID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ecid-3"},<br/>&nbsp;&nbsp;{"id": "ecid-2", "primary": true},<br/>&nbsp;&nbsp;{"id": "ecid-1", "primary": true}<br/>]</code></pre></td>
     </tr>
     <tr>
       <td>CCID</td>
       <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;{"id": "ccid-1"},<br/>&nbsp;&nbsp;{"id": "ccid-2", "primary": true}<br/>]</code></pre></td>
     </tr>
   </table>

  <table style="table-layout:auto">
    <tr>
      <th>Sorted identities list</th>
      <th>Selected identity</th>
    </tr>
    <tr>
      <td><pre lang="json"><code>[<br/>&nbsp;&nbsp;"id": "ecid-1",<br/>&nbsp;&nbsp;"id": "ecid-2",<br/>&nbsp;&nbsp;"id": "ecid-3"<br/>]</code></pre></td>
      <td><pre lang="json"><code>"id": "ecid-1",<br/>"namespace": "ECID"</code></pre></td>
    </tr>
  </table>

## How field-based stitching works

Stitching makes a minimum of two passes on data in a given dataset.

- **Live stitching**: attempts to stitch each hit (event) as it comes in. Hits from devices that are *new* to the dataset (have never authenticated) are typically not stitched at this level. Hits from devices already recognized are stitched immediately.

- **Replay stitching**: *replays* data based on unique identifiers (person IDs). This stage is where hits from previously unknown devices (persistent IDs) become stitched (to person IDs). Two parameters determine the replay: **frequency** and **lookback window**. Adobe offers the following combinations of these parameters:
    - **Daily lookback on a daily frequency**: Data replays every day with a 24-hour lookback window. This option holds an advantage that replays are much more frequent, but unauthenticated profiles must authenticate the same day that they visit your site.
    - **Weekly lookback on a weekly frequency**: Data replays once a week with a weekly lookback window (see [options](#options)). This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, unstitched data less than a week old is not reprocessed until the next weekly replay.
    - **Biweekly lookback on a weekly frequency**: Data replays once every week with a biweekly lookback window (see [options](#options)). This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, unstitched data less than two weeks old is not reprocessed until the next weekly replay.
    - **Monthly lookback on a weekly frequency**: Data replays every week with a monthly lookback window (see [options](#options)). This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, unstitched data less than a month old is not reprocessed until the next weekly replay.

- **Privacy**: When privacy-related requests are received, in addition to removing the requested identity, any stitching of that identity across unauthenticated events must be undone.
  
  >[!IMPORTANT]
  >
  >The unstitching process, as part of privacy requests, changes at the start of 2025. The current unstitching process restitches events using the latest version of known identities. This reassignment of events to another identity might have undesirable legal consequences. To remedy these concerns, from 2025 on, the new unstitching process updates events that are subject of the privacy request with the persistent ID.
  > 


Data beyond the lookback window is not replayed. A profile must be authenticated within a given lookback window for an unauthenticated visit and an authenticated visit to be identified together. Once a device is recognized, that device is live stitched from that point forward.

### Step 1: Live stitching

Live stitching attempts to stitch each event upon collection to known devices and channels. 

+++ Details

Consider the following example, where Bob records different events as part of an event dataset. 

*Data as it appeared the day it is collected:*

| Event | Timestamp | Persistent ID (Cookie ID) | Person ID | Resulting ID (after live stitch) |
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`246`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg)| `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`**|
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`**|
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg)| - | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`81911`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg)|
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** |
| | | **3 devices** | | **4 people**:<br/>`246`, `Bob`, `3579`, `81911` |

Both unauthenticated and authenticated events on new devices are counted as separate people (temporarily). Unauthenticated events on recognized devices are live stitched.

Attribution works when the identifying custom variable is tied to a device. In the example above, all events except events 1, 8, 9 and 10 are live stitched (they all use the `Bob` identifier). Live stitching 'resolves' the resulting ID for event 4, 6 and 12.

Delayed data (data with a timestamp over 24 hours old) is handled on a 'best effort' basis, while prioritizing the stitching of current data for the highest quality.

+++ 

### Step 2: Replay stitching

At regular intervals (once a week or once a day, depending on the chosen lookback window), replay stitching recalculates historical data based on devices it now recognizes. If a device initially sends data while not authenticated and then logs in, replay stitching ties those unauthenticated events to the correct person. 

+++ Details

The following table represents the same data as above, but shows different numbers based on replaying the data.

*The same data after replay:*

| Event | Timestamp | Persistent ID (Cookie ID) | Person ID | Resulting ID (after live stitch) | Resulting ID (after replay) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** |
| 2 | 2023-05-12 12:02 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 3 | 2023-05-12 12:03 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | Bob |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`**| `Bob` |
| 5 | 2023-05-12 12:05 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`**| `Bob` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg)| `Bob` | `Bob` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | - | **`3579`** | **`3579`** |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg)| `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg)| `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` |
| | | **3 devices** | | **4 people**:<br/>`246`, `Bob`, `3579`, `81911` | **2 people**:<br/>`Bob`, `3579` |

{style="table-layout:auto"}

Attribution works when the identifying custom variable is tied to a device. In the example above, event 1 and 10 are stitched as a result from the replay, leaving only event 8, and 9 unstitched. And reducing the people metric (cumulative) to 2.

+++ 

### Step 3: Privacy Request

When you receive a privacy request, any identifier info set by stitching process to person ID value is updated in all records to persistent ID value, for the user subject of the privacy request.

+++ Details

The following table represents the same data as above, but shows the effect that a privacy request for Bob has on the data after processing it. The rows where Bob is authenticated are removed (2, 3, 5, 7, and 11) along with removing Bob as a person ID for other rows.

*The same data after a privacy request for Bob:*

| Event | Timestamp | Persistent ID (Cookie ID) | Person ID | Resulting ID (after live stitch) | Resulting ID (after replay) | Person ID | Resulting ID (after privacy request) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | `246` | - | `246` | **`Bob`** | - | `246` |
| 2 | 2023-05-12 12:02 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` | `Bob` ![Arrow Up](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `246` |
| 3 | 2023-05-12 12:03 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg)  | `246` |
| 4 | 2023-05-12 12:04 | `246` | - | **`Bob`**| `Bob` | - | `246` |
| 5 | 2023-05-12 12:05 | `246` | Bob ![ArrowRight](/help/assets/icons/ArrowRight.svg)  | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg) | `Bob` | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg)  | `246` |
| 6 | 2023-05-12 12:06 | `246` | - | **`Bob`**| `Bob` | - | `246` |
| 7 | 2023-05-12 12:07 | `246` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg)  | `Bob` | `Bob` |![RemoveCircle](/help/assets/icons/RemoveCircle.svg)  | `246` |
| 8 | 2023-05-12 12:03 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg)  | - | **`3579`** | **`3579`** | - | `3579` |
| 9 | 2023-05-12 12:09 | `3579` ![ArrowRight](/help/assets/icons/ArrowRight.svg)  | - | **`3579`** | **`3579`** | - | `3579` |
| 10 | 2023-05-12 12:02 | `81911` | - | `81911` | **`Bob`** | - | `81911` |
| 11 | 2023-05-12 12:05 | `81911` | `Bob` ![ArrowRight](/help/assets/icons/ArrowRight.svg) | `Bob` ![ArrowDown](/help/assets/icons/ArrowDown.svg)| `Bob` ![ArrowUp](/help/assets/icons/ArrowUp.svg) | ![RemoveCircle](/help/assets/icons/RemoveCircle.svg) | `81911` |
| 12 | 2023-05-12 12:12 | `81911` | - | **`Bob`** | `Bob` | - | `81911` |
| | | **3 devices** | | **4 people**:<br/>246, `Bob`, `3579`, `81911` | **2 people**:<br/>Bob, `3579` |  | **3 people**:<br/>`246`, `3579`, `81911` |

+++ 

## Prerequisites

The following prerequisites apply specifically to field-based stitching:

- The event dataset in Adobe Experience Platform, to which you want to apply stitching, must have two columns that help identify profiles:
  
  - A **persistent ID**, an identifier available on every row. For example, a visitor ID generated by an Adobe Analytics AppMeasurement library or an ECID generated by the Adobe Experience Platform Identity Service.
  - A **person ID**, an identifier available on only some rows. For example, a hashed username or email address once a profile authenticates. You can use virtually any identifier that you like. Stitching considers this field to hold the actual person ID info. For best stitching results, a person ID should be sent within the dataset's events at least once for each persistent ID. If you plan to include this dataset within a Customer Journey Analytics connection, it is preferable that the other datasets also have a similar common identifier.

<!--
- Both columns (persistent ID and person ID) must be defined as an identity field with an identity namespace in the schema for the dataset you want to stitch. When using identity stitching in Real-time Customer Data Platform, using the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity), you still need to add identity fields with an identity namespace. This identification of identity fields is required as Customer Journey Analytics stitching does not support the `identityMap` field group. When adding an identity field in the schema, while also using the `identityMap` field group, do not set the additional identity field as a primary identity. Setting an additional identity field as primary identity interferes with the `identityMap` field group used for Real-time Customer Data Platform.

-->

## Limitations

The following limitations apply specifically to field-based stitching:

- Current rekeying capabilities are limited to one step (persistent ID to person ID). Multiple-step rekeying (for example, persistent ID to a person ID, then to another person ID) is not supported.
- If multiple people share a device and the total number of transitions between users exceeds 50,000, Customer Journey Analytics stops stitching data for that device.
- Custom ID maps used in your organization are not supported.
- Stitching is case-sensitive. For datasets generated through the Analytics source connector, Adobe recommends reviewing any VISTA rules or processing rules that apply to the person ID field. This review ensures that none of these rules are introducing new forms of the same ID. For example, you should ensure that no VISTA or processing rules are introducing lowercasing to the person ID field on only a portion of the events.
- Stitching does not combine or concatenate fields. 
- The person ID field should contain a single type of ID (IDs from a single namespace). For instance, the person ID field should not contain a combination of login IDs and email IDs.
- If multiple events occur with the same timestamp for the same persistent ID, but with different values in the person ID field, stitching selects the ID based on alphabetical order. So, if persistent ID A has two events with the same timestamp and one of the events specifies Bob and the other specifies Ann, stitching selects Ann.
- Be cautious of scenarios where the person IDs contain placeholder values, for example `Undefined`. See the [FAQ](faq.md) for more information.
- You cannot use the same namespace for both persistent ID and person ID, the namespaces need to be mutually exclusive.
