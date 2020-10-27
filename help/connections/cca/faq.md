---
title: Cross-channel Analytics FAQ
description: Frequently asked questions for Cross-channel Analytics
---

# Frequently asked questions

## How can I use CCA to see how people move from one device type to another?

You can use a Flow visualization with the Mobile Device Type dimension.

1. Log in [analytics.adobe.com](https://analytics.adobe.com) and create a blank Workspace project.
2. Click the Visualizations tab on the left, and drag a Flow visualization to the canvas on the right.
3. Click the Components tab on the left, and drag the dimension 'Mobile Device Type' to the center location labled 'Dimension or Item'.
4. This flow report is interactive. Click any of the values to expand the flows to subsequent or previous pages. Use the right-click menu to expand or collapse columns. Different dimensions can also be used within the same flow report.

## How far back does CCA stitch visitors?

Adobe keeps device stitching data for approximately 30 days. If a device is intitially not identified but is later identified within 30 days, CCA goes back and restates that device as belonging to identified person up to 30 days in the past. If some of a user's unidentified behavior falls outside the 30-day lookback window, that portion of the user's journey is not stitched.

## How are shared devices handled?

In some situations it is possible that multiple people log in from the same device. Examples include a shared device at home, shared PCs in a library, or a kiosk in a retail outlet.

The transient ID overrides the persistent ID, so shared devices are considered separate people (even if they originate from the same device).

## How does CCA handle situations where a single person has a large number of persistent IDs?

In some situations, an individual user can associate with a large number of persistent IDs. Examples include an individual frequently clearing browser cookies, or using the browser's private/incognito mode.

The number of persistent IDs is irrelevant in favor of the transient ID. A single user can belong to any number of devices without impacting CCA's ability to stitch across devices.

## Cross-channel Analytics stitches unique visitors together. Can it stitch visits together?

Yes. If an individual sends hits from two separate devices within your data view's visit timeout (typically 30 minutes), they are stitched into the same visit.

<!-- Talk about SLA? Backfill approx. time based on volume -->

<!-- GDPR question, how we handle it. How does CCA handle GDPR/CCPA requests? we do so in accordance with the law -->

<!-- how does CCA handle data atlerations, such as GDPR/CCPA requests, or other alterations?  data in CJA reflects the current/latest dataset from Platform, Link to platform docs about editing/deleting data. -->
