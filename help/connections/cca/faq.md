---
title: Cross-Channel Analytics FAQ
description: Frequently asked questions for Cross-Channel Analytics
exl-id: 2ad78c19-4b13-495b-a0aa-44e0a3c95b5e
---
# Frequently asked questions

## How can I use CCA to see how people move from one channel to another?

You can use a Flow visualization with the Dataset ID dimension.

1. Log in [analytics.adobe.com](https://analytics.adobe.com) and create a blank Workspace project.
2. Click the Visualizations tab on the left, and drag a Flow visualization to the canvas on the right.
3. Click the Components tab on the left, and drag the dimension 'Dataset ID' to the center location labled 'Dimension or Item'.
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

If you would like to rename dataset ID dimension items, you can use a lookup dataset.

## How far back does CCA rekey visitors?

The lookback window for rekeying depends on your desired frequency of data [replay](replay.md). For example, if you set up CCA to replay data once every week, the lookback window for rekeying is 7 days. If you set up CCA to replay data every day, the lookback window for rekeying is 1 day.

## How are shared devices handled?

In some situations it is possible that multiple people log in from the same device. Examples include a shared device at home, shared PCs in a library, or a kiosk in a retail outlet.

The transient ID overrides the persistent ID, so shared devices are considered separate people (even if they originate from the same device).

## How does CCA handle situations where a single person has a large number of persistent IDs?

In some situations, an individual user can associate with a large number of persistent IDs. Examples include an individual frequently clearing browser cookies, or using the browser's private/incognito mode.

The number of persistent IDs is irrelevant in favor of the transient ID. A single user can belong to any number of devices without impacting CCA's ability to stitch across devices.

## Once I contact my Account Manager with the desired information, how long does it take for the rekeyed dataset to become available?

Live stitching is available approximately 1 week after Adobe enables Cross-Channel Analytics. Backfill availability depends on the amount of existing data. Small datasets (less than 1 million events per day) typically take a couple days, while large data sets (1 billion events per day) can take a week or more.

## How does Cross-Channel Analytics handle GDPR and CCPA requests?

Adobe handles GDPR and CCPA requests in accordance to local and international laws. Adobe offers the [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) to submit data access and deletion requests. The requests apply to both the original and rekeyed datasets.
