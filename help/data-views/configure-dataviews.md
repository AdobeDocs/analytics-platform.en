---
title: Configure data views and attribution
description: Describes how to create a data view to a Platform dataset in Customer Journey Analytics
---

# Configure data views and attribution

eVars, props, and events in the traditional Adobe Analytics sense no longer exist in Customer Journey Analytics. Instead, you have unlimited schema elements (dimensions, metrics, list fields ). All of the attribution settings that you used to apply to eVars and props during the data collection process are now applied at query time - also known as report-time processing. 

Keep this in mind before you apply attribution settings:

* In the data views user interface, you specify the default attribution. You can later override these settings in Workspace projects (not sure if this latter functionality will be there right off the bat).

* Attribution settings in Customer Journey Analytics are non-destructive and retroactive. In other words, you cannot do irreparable harm to your datasets in Customer Journey Analytics. Even if you accidentally delete something, you can always go back to Experience Platform and bring the dataset back in. (Keep in mind, however, that bringing the dataset back in will incur additional cost.)

* You can create multiple data views for a single dataset. For example, you could have one data view where all dimensions are set to "Last Touch", and, simultaneously, another data view (based on the same dataset) with all dimensions set to "First Touch".

* If you wish to have a dimension "behave" like a traditional eVar (conversion variable), you should configure it with "Last Touch Visit" attribution by default.

* If you wish to have a dimension "behave" like a traditional prop (traffic variable), you should configure it with "Same Hit" attribution by default.

* If you wish to have a metric "behave" like a default metric, you shouldn't change anything (not clear what this means, but I wrote it down in my notes).

For reference: [Attribution IQ doc](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html)]

## Specify attribution settings on a data field

To specify an attribution settings:

1. 