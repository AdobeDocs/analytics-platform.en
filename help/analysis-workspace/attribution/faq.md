---
title: Attribution FAQ
description: Get answers to commonly asked questions around attribution.
exl-id: 3153d8c9-4ca8-4189-8a2f-511a87e8ac17
---
# Attribution FAQ

>[!NOTE]
>
>You are viewing the documentation for Analysis Workspace in Customer Journey Analytics. Its feature set differs slightly from [Analysis Workspace in traditional Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Learn more...](/help/getting-started/cja-aa.md)

**What is the "None" line item when using attribution?**

The 'None' line item is a catch-all item that represents all conversions that happened without any touch points within the lookback window. Try including a longer time range in your reporting window.

**Why do I sometimes see dates outside of my reporting window when using attribution models?**

These extra dates are due to the visitor reporting lookback window. See [Data appearing outside reporting window](https://helpx.adobe.com/analytics/kb/data-appearing-outside-reporting-window.html) in the Analytics KB for more information. Adobe plans to filter out these extra rows in an upcoming release.

**When should I use a visit vs. visitor attribution lookback?**

The choice of attribution lookback depends on your use case. If conversions typically take longer than a single visit, a visitor lookback is recommended. Creating a data view with a longer visit definition is also a potential solution.

**How do props and eVars compare when using attribution?**

Attribution is recalculated at report runtime, so there is no difference between a prop or eVar (or any other dimension) for the sake of attribution modeling. Props can persist using any lookback window or attribution model, and eVar allocation/expiration settings are ignored.

**What dimensions and metrics are not supported?**

The attribution panel supports all dimensions. Unsupported metrics include:

* Unique Visitors
* Visits
* Occurrences
* Page Views
* A4T metrics
* Time Spent metrics
* Bounces
* Bounce rate
* Entries
* Exits
* Pages Not Found
* Searches
* Single Page Visits
* Single Access

**How does attribution work with filters?**

Attribution always runs before filters, and global filters run before any other report filters are applied.
