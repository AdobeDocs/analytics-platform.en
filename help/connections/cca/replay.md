---
title: How replays work
description: Understand the concept of "replay" in Cross-Channel Analytics
exl-id: 1100043a-4e4f-4dbc-9cfc-9dcba5db5f67
---
# How replays work

Cross-Channel Analytics makes two passes on data on a given connection:

* **Live-stitching**: CCA attempts to stitch each hit as it comes in. Net new devices to the dataset that have never logged in are typically not stitched at this level. Devices already recognized are stitched immediately.
* **Replay**: CCA "replays" data based on unique identifiers it has learned. This stage is where new devices to the connection become stitched. Adobe offers two replay intervals:
  * Daily: Data replays every day with a 24-hour lookback window. This option holds an advantage that replays are much more frequent, but unauthenticated visitors must authenticate the same day that they visit your site.
  * Weekly: Data replays once a week with a 7-day lookback window. This option holds an advantage that allows unauthenticated sessions a much more lenient time to authenticate. However, data less than a week old is not stitched.

## Step 1: Live-stitching

CCA attempts to stitch each event upon collection to known devices and channels. Consider the following example, where Bob uses two different channels.

*Data as it appears the day it is collected:*

| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `246` | Bob visits your site on his desktop, unauthenticated | `1` (246) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `2` (246 and Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob makes a call to customer service | `2` (246 and Bob) |
| `4` | `3579` | - | - | `3579` | Bob accesses your site on his mobile device, unauthenticated | `3` (246, Bob, and 3579) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `3` (246, Bob, and 3579) |
| `6` | - | - | `Bob` | `Bob` | Bob makes another call to customer service | `3` (246, Bob, and 3579) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on his desktop again, unauthenticated | `3` (246, Bob, and 3579) |

Both unauthenticated and authenticated events on new devices are counted as separate people (temporarily). Unauthenticated events on recognized devices are live-stitched.

Attribution works as soon as the identifying custom variable ties to a device. In the example above, all events except events 1 and 4 are live-stitched (they all use the `Bob` identifier). Attribution works on events 1 and 4 after replay stitching.

## Step 2: Replay stitching

At regular intervals (once a week or once a day depending on the chosen lookback window), CCA recalculates historical data based on devices it now recognizes. If a device initially sends data while not authenticated and then logs in, CCA ties those unauthenticated events to the correct person. The following table represents the same data as above, but shows different numbers based on replaying the data.

*The same data after replay:*

| Timestamp | Web dataset Persistent ID | Web dataset Transient ID | Call center person ID | Person ID used | Explanation of hit | People metric (cumulative) |
| --- | --- | --- | --- | --- | --- | --- |
| `1` | `246` | - | - | `Bob` | Bob visits your site on his desktop, unauthenticated | `1` (Bob) |
| `2` | `246` | `Bob` | - | `Bob` | Bob logs in on desktop | `1` (Bob) |
| `3` | - | - | `Bob` | `Bob` | Bob makes a call to customer service | `1` (Bob) |
| `4` | `3579` | - | - | `Bob` | Bob accesses your site on his mobile device, unauthenticated | `1` (Bob) |
| `5` | `3579` | `Bob` | - | `Bob` | Bob logs in via mobile | `1` (Bob) |
| `6` | - | - | `Bob` | `Bob` | Bob makes another call to customer service | `1` (Bob) |
| `7` | `246` | - | - | `Bob` | Bob visits your site on his desktop again, unauthenticated | `1` (Bob) |

## Recap

* CCA immediately stitches known devices, but does not immediately stitch new or unrecognized devices.
* Data is replayed at regular intervals, and changes historical data in the connection based on devices it has learned to identify.
