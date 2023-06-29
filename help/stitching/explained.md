---
title: How stitching works
description: Understand the concept of stitching
solution: Customer Journey Analytics
feature: Stitching
---
# How stitching works

Stitching makes a minimum of two passes on data in a given dataset:

* **Live stitching**: attempts to stitch each hit as it comes in. Net new devices to the dataset that have never logged in are typically not stitched at this level. Devices already recognized are stitched immediately.

* **Replay stitching**: "replays" data based on unique identifiers it has learned. This stage is where new devices to the connection become stitched. Adobe offers two replay intervals:
    * **Daily**: Data replays every day with a 24-hour lookback window. This option holds an advantage that replays are much more frequent, but unauthenticated visitors must authenticate the same day that they visit your site.
    * **Weekly**: Data replays once a week with a 7-day lookback window. This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, data less than a week old is not stitched.

* **Privacy (optional)**: When privacy-related requests are received, in addition to removing the requested identity, any stitching of that identity across unauthenticated events must be undone.

Data beyond the lookback window is not replayed. A visitor must authenticate within a given lookback window for an unauthenticated visit and authenticated visit to be identified together. Once a device is recognized, it is live stitched from that point forward. Privacy requests are processed across stitched data regardless of time.

## Step 1: Live stitching

Live stitching attempts to stitch each event upon collection to known devices and channels. Consider the following example, where Bob records different events as part of an event dataset. 

*Data as it appears the day it is collected:*

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | 
|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **246** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | 
| 4 | 2023-05-12 12:04 | 246 | - | **Bob**|
| 5 | 2023-05-12 12:05 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob**| | 
| 7 | 2023-05-12 12:07 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | 
| 8 | 2023-05-12 12:03 | 3579 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| - | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** |
| 10 | 2023-05-12 12:02 | 81911 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **81911** |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg)|
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** |
| | | **3 devices** | | **4 people**:<br/>246, Bob, 3579, 81911 |

{style="table-layout:auto"}

<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Stitched ID after live stitch | Call enter Person ID | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visits your site on a desktop, unauthenticated | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `2` (246 and Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `2` (246 and Bob) |
| `4` | `3579` | - | - | `3579` | Bob accesses your site on a mobile device, unauthenticated | `3` (246, Bob, and 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `3` (246, Bob, and 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `3` (246, Bob, and 3579) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `3` (246, Bob, and 3579) |
-->

Both unauthenticated and authenticated events on new devices are counted as separate people (temporarily). Unauthenticated events on recognized devices are live stitched.

Attribution works when the identifying custom variable ties to a device. In the example above, all events except events 1, 8, 9 and 10 are live stitched (they all use the `Bob` identifier). Live stitching 'resolves' the stitched ID for event 4, 6 and 12.

## Step 2: Replay stitching

At regular intervals (once a week or once a day, depending on the chosen lookback window), replay stitching recalculates historical data based on devices it now recognizes. If a device initially sends data while not authenticated and then logs in, replay stitching ties those unauthenticated events to the correct person. The following table represents the same data as above, but shows different numbers based on replaying the data.

*The same data after replay:*

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | Stitched ID (after replay) |
|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Arrow Up](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob**| Bob |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob**| Bob | 
| 7 | 2023-05-12 12:07 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob |
| 8 | 2023-05-12 12:03 | 3579 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 9 | 2023-05-12 12:09 | 3579 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | 
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg)| Bob ![Arrow Up](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | 
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | 
| | | **3 devices** | | **4 people**:<br/>246, Bob, 3579, 81911 | **2 people**:<br/>Bob, 3579 | 

{style="table-layout:auto"}

Attribution works when the identifying custom variable ties to a device. In the example above, event 1 and 10 are stitched as a result from the replay, leaving only event 8, and 9 unstitched. And reducing the people metric (cumulative) to 2.

## Step 3: Privacy Request

When you receive a privacy request, the row containing the original user information is removed, along with any stitched IDs that contain this same person information. The following table represents the same data as above, but shows the effect that a privacy request for Bob has on the data after processing it. The rows where Bob authenticated are removed (2, 3, 5, 7, and 11) along with removing Bob as a transient ID for other rows.

*The same data after a privacy request for Bob:*

| Event | Timestamp | Persistent ID (Cookie ID) | Transient ID (Login ID) | Stitched ID (after live stitch) | Stitched ID (after replay) | Transient ID (Login ID) | Stitched ID (after privacy request) |
|---|---|---|---|---|---|---|---|
| 1 | 2023-05-12 12:01 | 246 | - | 246 | **Bob** | - | 246 |
| 2 | 2023-05-12 12:02 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob ![Arrow Up](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 3 | 2023-05-12 12:03 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg)| Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 4 | 2023-05-12 12:04 | 246 | - | **Bob**| Bob | - | 246 |
| 5 | 2023-05-12 12:05 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg) | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 6 | 2023-05-12 12:06 | 246 | - | **Bob**| Bob | - | 246 | 
| 7 | 2023-05-12 12:07 | 246 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob | Bob | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 246 |
| 8 | 2023-05-12 12:03 | 3579 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 | 
| 9 | 2023-05-12 12:09 | 3579 ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | - | **3579** | **3579** | - | 3579 |
| 10 | 2023-05-12 12:02 | 81911 | - | 81911 | **Bob** | - | 81911 |
| 11 | 2023-05-12 12:05 | 81911 | Bob ![Arrow Right](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowRight_18_N.svg) | Bob ![Arrow Down](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowDown_18_N.svg)| Bob ![Arrow Up](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ArrowUp_18_N.svg) | <img src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_RemoveCircle_18_N.svg"/> | 81911 |
| 12 | 2023-05-12 12:12 | 81911 | - | **Bob** | Bob | - | 81911 |
| | | **3 devices** | | **4 people**:<br/>246, Bob, 3579, 81911 | **2 people**:<br/>Bob, 3579 |  | **3 people**:<br/>246, 3579, 81911 |


<!--
| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used (stitched ID) | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on a desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob calls customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on a mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob calls customer service again | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on a desktop again, unauthenticated | `1` (Bob) |
-->

## Summary

* Stitching immediately stitches known devices, but does not immediately stitch new or unrecognized devices.
* Data is replayed at regular intervals, and changes historical data in the connection based on devices it has learned to identify.
* Live stitching and replay stitching are performed on one dataset. The result is a new elevated dataset that is better suited to be used when combined with other datasets (for example, call-center data) to perform cross-channel analysis.
* Privacy requests remove identities that were spread to unauthenticated rows.
