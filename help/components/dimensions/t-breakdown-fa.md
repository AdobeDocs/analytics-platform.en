---
description: Break down dimensions and dimension items in Analysis Workspace.
keywords: Analysis Workspace
title: Break down dimensions
feature: Dimensions
exl-id: 6b433db3-02c1-4deb-916e-b01c0b79889e
---
# Break down dimensions in Workspace

>[!NOTE]
>
>You are viewing the documentation for Analysis Workspace in Customer Journey Analytics. Its feature set differs slightly from [Analysis Workspace in traditional Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Learn more...](/help/getting-started/cja-aa.md)

Break down dimensions and dimension items in Analysis Workspace.

Break down your data in unlimited ways for your specific needs; build queries using relevant metrics, dimensions, filters, time lines, and other analysis breakdown values.

1. [Create a project](/help/analysis-workspace/home.md) with a data table.
1. In the data table, right-click a line item and select **[!UICONTROL Breakdown]** > *`<item>`*.

   ![Step Result](assets/fa_data_table_actions.png)

   You can break down metrics by dimension items or audience filters across selected time periods. You can also drill down further to a more granular level.

   >[!NOTE]
   >
   >The number of breakdowns to show in the table is limited to 200. This limit will increase for exporting breakdowns.

**Video: Dimensions in Analysis Workspace**

>[!VIDEO](https://video.tv.adobe.com/v/23971)

**Video: Dimension Breakdowns**

>[!VIDEO](https://video.tv.adobe.com/v/23969)

## Apply attribution models to breakdowns

Any breakdown within a table can also have any attribution model applied to it. This attribution model can be the same or different from the parent column. For example, you can analyze linear Orders on your Marketing Channels dimension but apply U-Shaped Orders to the specific tracking codes within a Channel. To edit the attribution model applied to a breakdown, hover over the breakdown model and click **[!UICONTROL Edit]**:

![Breakdown settings](assets/breakdown_settings.png)

This is the expected behavior when applying attribution models to breakdowns or editing them:

* If you apply an attribution when no other attributions exist, then the attribution applies to the entire column tree.

* If you add a breakdown after an attribution has been applied, it will use the default for the given breakdown that was added (if that dimension has a default). Otherwise it will use the breakdown from the parent column. Some dimensions have a default allocation. For example, Time dimensions and Referrer use Same Touch. The Product dimension uses Last Touch. Other dimensions don’t have a default, and will use the parent column allocation.

* If there are already attributions in the column tree, changing the attribution only impacts the one you are editing.

## Videos

Adding dimensions and metrics to your project in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/30606)

Working with dimensions in a Freeform Table:

>[!VIDEO](https://video.tv.adobe.com/v/40179)

Dimension breakdowns by position:

>[!VIDEO](https://video.tv.adobe.com/v/24033)
