---
title: How replays work
description: Understand the concept of "replay" in Cross-channel Analytics
---

# How replays work

Cross-channel Analytics makes two passes on data on a given connection:

* **Live-stitching**: CCA attempts to stitch each hit as it comes in. Net new devices to the dataset that have never logged in are typically not stitched at this level. Devices already recognized are stitched immediately.
* **Replay**: Approximately once a week, CCA "replays" data based on unique identifiers it has learned. This stage is where new devices to the connection become stitched.

## Step 1: Live-stitching

As soon as a hit is collected, CCA attempts to stitch it to known devices. Consider the following example, where Bob uses two devices.

*Data as it appears the day it is collected:*

| Timestamp | ECID | eVar1 or CustomerID | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob on his desktop computer, unauthenticated | `1` (246) |
| `2` | `246` | `Bob` | Bob logs in on his desktop | `2` (246 and Bob) |
| `3` | `3579` | - | Bob on his mobile device, unauthenticated | `3` (246, Bob, and 3579) |
| `4` | `3579` | `Bob` | Bob logs in on mobile | `3` (246, Bob, and 3579) |
| `5` | `246` | - | Bob accesses your site on desktop again, unauthenticated | `3` (246, Bob, and 3579) |
| `6` | `246` | `Bob` | Bob logs in again via desktop | `3` (246, Bob, and 3579) |
| `7` | `3579` | - | Bob accesses your site again on mobile | `3` (246, Bob, and 3579) |
| `8` | `3579` | `Bob` | Bob logs in again via mobile | `3` (246, Bob, and 3579) |

Both unauthenticated and authenticated hits on new devices are counted as separate people (temporarily). Unauthenticated hits on recognized devices are live-stitched from that point forward.

Attribution works as soon as the identifying custom variable ties to a device. In the example above, all hits except hits 1 and 3 are live-stitched (they all use the `Bob` identifier). Attribution works on hits 1 and 3 after replay stitching.

## Step 2: Replay stitching

Approximately once a week, CCA recalculates historical data based on devices it now recognizes. If a device initially sends data while not authenticated and then logs in, CCA ties those unauthenticated hits to the correct person. The following table represents the same data as above, but shows different numbers based on replaying the data.

*The same data after replay:*

| Timestamp | ECID | eVar1 or CustomerID | Explanation of hit | People metric (cumulative) using Device Graph | People metric (cumulative) using Field-based stitching |
| --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | Bob on his desktop computer, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | Bob logs in on his desktop | `1` (Bob) |
| `3` | `3579` | - | Bob on his mobile device, unauthenticated | `1` (Bob) |
| `4` | `3579` | `Bob` | Bob logs in on mobile | `1` (Bob) |
| `5` | `246` | - | Bob accesses your site on desktop again, unauthenticated | `1` (Bob) |
| `6` | `246` | `Bob` | Bob logs in again via desktop | `1` (Bob) |
| `7` | `3579` | - | Bob accesses your site again on mobile | `1` (Bob) |
| `8` | `3579` | `Bob` | Bob logs in again via mobile | `1` (Bob) |

## Recap

* Data less than a week old immediately stitches known devices, but does not immediately stitch new or unrecognized devices.
* Data is replayed once a week, and changes historical data in the connection based on devices it has learned to identify.
