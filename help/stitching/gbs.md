---
title: Graph-based stitching
description: Explains the concept and working of graph-based stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
exl-id: ea5c9114-1fc3-4686-b184-2850acb42b5c
---
# Graph-based stitching


In graph-based stitching, you specify an event dataset as well as the persistent ID (cookie) and the namespace of the person ID for that dataset. Graph-based stitching adds a new column for the stitched ID to the event dataset. And then uses the persistent ID to query the identity graph from the Experience Platform Identity Service, using the namespace specified, to update the stitched ID.

>[!NOTE]
>
>You must ensure the dataset is [enabled for the Identity Service](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service).
>


![Graph-based-stitching](/help/stitching/assets/gbs.png)

## IdentityMap

Graph-based stitching supports the use of the [`identityMap` field group](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/schema/composition#identity) in the following scenarios:

- Use of the primary identity in `identityMap` namespaces to define the persistentID:
  - If multiple primary identities found in different namespaces, the identities in the namespaces are sorted lexigraphically and the first identity is selected.
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

- Use of `identityMap` namespace to define the persistentID:
  - If multiple values for persistentID are found in an `identityMap` namespace, the first lexicographical available identity is used.

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
 

## How graph-based stitching works

Stitching makes a minimum of two passes on data in a given dataset.

- **Live stitching**: attempts to stitch each hit (event) as it comes in, using the persistent ID to look up the person ID for the selected namespace by querying the identity graph. If the person ID is available from the lookup, this person ID is immediately stitched.

- **Replay stitching**: *replays* data based on updated identities from the identity graph. This stage is where hits from previously unknown devices (persistent IDs) become stitched as the identity graph has resolved the identity for a namespace. The replay is determined by two parameters: **frequency** and **lookback window**. Adobe offers the following combinations of these parameters:
    - **Daily lookback on a daily frequency**: Data replays every day with a 24-hour lookback window. This option holds an advantage that replays are much more frequent, but unauthenticated profiles must authenticate the same day that they visit your site.
    - **Weekly lookback on a weekly frequency**: Data replays once a week with a weekly lookback window (see [options](#options)). This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, unstitched data less than a week old is not reprocessed until the next weekly replay.
    - **Biweekly lookback on a weekly frequency**: Data replays once every week with a biweekly lookback window (see [options](#options)). This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, unstitched data less than two weeks old is not reprocessed until the next weekly replay.
    - **Monthly lookback on a weekly frequency**: Data replays every week with a monthly lookback window (see [options](#options)). This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, unstitched data less than a month old is not reprocessed until the next weekly replay.

- **Privacy**: When privacy-related requests are received, in addition to removing the requested identity from the source dataset, any stitching of that identity across unauthenticated events must be undone. Also, the identity must be removed from the identity graph to prevent future graph-based stitching for that specific identity.

  >[!IMPORTANT]
  >
  >The unstitching process, as part of privacy requests, changes at the start of 2025. The current unstitching process restitches events using the latest version of known identities. This reassignment of events to another identity might have undesirable legal consequences. To remedy these concerns, from 2025 on, the new unstitching process updates events that are subject of the privacy request with the persistent ID.
  > 

Data beyond the lookback window is not replayed. A profile must authenticate within a given lookback window for an unauthenticated visit and an authenticated visit to be identified together. Once a device is recognized, it is live stitched from that point forward.

Consider the following two identity graphs for persistent id `246` and `3579`, how these identity graphs are updated over time, and how these updates impact the steps in graph-based stitching.

![Identity Graph 246](assets/identity-graph-246.svg)
![Identity Graph 3579](assets/identity-graph-3579.svg)

You can view an identity graph over time for a specific profile using the [Identity Graph Viewer](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-viewer). See also [Identity Service linking logic](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-linking-logic) to get a better understanding of the logic used when linking identities.

### Step 1: Live stitching

Live stitching attempts to stitch each event, upon collection, to known information at that time from the identity graph. 

+++ Details

| | Time | Persistent ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID (after live stitch) | 
|--:|---|---|---|---|
| 1 | 2023-05-12 11:00   | `246` |  `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` |
| 2 | 2023-05-12 14:00  | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` | 
| 3 | 2023-05-12 15:00  | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com`   | 
| 4 | 2023-05-12 17:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `3579` |
| 5 | 2023-05-12 19:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `ted.w@gmail.com` |
| 6 | 2023-05-13 15:00 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` | `bob.a@gmail.com` |
| 7 |2023-05-13 16:30 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

You can see how for each event the stitched id is resolved. Based on the time, the persistent id, and the lookup of the identity graph for the specified namespace (at that same time). 
When the lookup resolves to more than one stitched id (like for event 7), the lexicographic first id returned by the identity graph is selected (`a.b@yahoo.co.uk` in the example).

+++

### Step 2: Replay stitching

At regular intervals (depending on the chosen lookback window), replay stitching recalculates historical data based on the most recent version of the identity graph, at the time of the interval. 

+++ Details

With a replay stitching happening at 2023-05-13 16:30, with a 24-hour lookback window configuration, some events from the sample are re-stitched (indicated by ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg)).

| | Time | Persistent ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID<br/>(after live stitch) | Stitched ID<br/>(after replay 24 hours) | 
|---|---|---|---|---|---|
| 2 | 2023-05-12 14:00  | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` |  `bob.a@gmail.com` | `bob.a@gmail.com` |
| 3 | 2023-05-12 15:00  | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` |  `bob.a@gmail.com` | `bob.a@gmail.com` |
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com`| 
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` |  `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` |  `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 |2023-05-13 16:30 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com`|  `a.b@yahoo.co.uk`  | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}


With replay stitching happening at 2023-05-13 16:30, with a 7-day lookback window configuration, all events from the sample are re-stitched.


| | Time | Persistent ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID<br/>(after live stitch) | Stitched ID<br/>(after replay 7 days) | 
|---|---|---|---|---|---|
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 1 | 2023-05-12 11:00   | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) *undefined* | `246` | `a.b@yahoo.co.uk` | 
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 2 | 2023-05-12 14:00  | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` |  `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 3 | 2023-05-12 15:00  | `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.a@gmail.com` |  `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 4 | 2023-05-12 17:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` | `ted.w@gmail.com`| 
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 5 | 2023-05-12 19:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` |  `ted.w@gmail.com` | `ted.w@gmail.com` |
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 6 | 2023-05-13 15:00 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` |  `bob.a@gmail.com` | `a.b@yahoo.co.uk` |
| ![Replay](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Replay_18_N.svg) 7 |2023-05-13 16:30 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` |  `a.b@yahoo.co.uk`  | `a.b@yahoo.co.uk` |

{style="table-layout:auto"}

+++

### Step 3: Privacy Request

When you receive a privacy request, the stitched id is deleted in all records for the user subject of the privacy request.

+++ Details

The following table represents the same data as above, but shows the effect that a privacy request (for example at 2023-05-13 18:00) has for the sample events.

| | Time | Persistent ID<br/>`ECID` | Namespace<br/>`Email` ![Graph](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataMapping_18_N.svg) | Stitched ID (after privacy request) | 
|--:|---|---|---|---|
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 1 | 2023-05-12 11:00   | `246` | `246`  ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 2 | 2023-05-12 14:00  | `246` | `246`  ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 3 | 2023-05-12 15:00  | `246` | `246`  ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 4 | 2023-05-12 17:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 5 | 2023-05-12 19:00  | `3579` | `3579` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `ted.w@gmail.com` | `3579` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 6 | 2023-05-13 15:00 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk` | `246` |
| <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> 7 |2023-05-13 16:30 |  `246` | `246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `a.b@yahoo.co.uk`<br/>`246` ![Link](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Branch1_18_N.svg) `bob.ab@gmail.com` | `246` |

{style="table-layout:auto"}

+++

## Prerequisites

The following prerequisites apply specifically to graph-based stitching:

- The event dataset in Adobe Experience Platform, to which you want to apply stitching, must have one column that identifies a profile on every row, the **persistent ID**. For example, a visitor ID generated by an Adobe Analytics AppMeasurement library or an ECID generated by the Experience Platform Identity Service. 
- The persistent ID must also be [defined as an identity](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/ui/fields/identity) in the schema.
- The identity graph from Experience Platform Identity Service must have a namespace (for example `Email`, or `Phone`) you want to use during stitching to resolve the **person ID**. See [Experience Platform Identity Service](https://experienceleague.adobe.com/en/docs/experience-platform/identity/home) for more information.

>[!NOTE]
>
>You do **not** require a Real-time Customer Data Platform license for graph-based stitching. The **Prime** package or higher of Customer Journey Analytics includes the required Experience Platform Identity Service entitlements.


## Limitations

The following limitations apply specifically to graph-based stitching:

- Timestamps are not taken into account when querying for the person ID using the specified namespace. So, it is possible that a persistent ID is stitched with a person ID from a record that has an earlier timestamp.
- In shared device scenarios, where the namespace in the graph contains multiple identities, the first lexicographic identity is used. If namespace limits and priorities are configured as part of the release of graph-linking rules, the last authenticated user's identity is used. See [Shared devices](/help/use-cases/stitching/shared-devices.md) for more information.
- There is a hard limit of three months of backfilling identities into the identity graph. You would use backfilling identities in case you are not using an Experience Platform application, like Real-time Customer Data Platform, to populate the identity graph.
- The [Identity Service guardrails](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails) apply. See, for example, the following [static limits](https://experienceleague.adobe.com/en/docs/experience-platform/identity/guardrails#static-limits):
  - Maximum number of identities in a graph: 50.
  - Maximum number of links to an identity for a single batch ingestion: 50. 
  - Maximum number of identities in an XDM record for graph ingestion: 20.
  - Minimum number of identities in an XDM record for graph ingestion: 2.
