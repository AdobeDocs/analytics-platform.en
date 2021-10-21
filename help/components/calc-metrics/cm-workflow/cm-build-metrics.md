---
description: The Calculated Metrics Builder provides a canvas to drag and drop Dimensions, Metrics, Filters, and Functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple calculated metrics or complex advanced calculated metrics.
title: Build Metrics
---
# Build Metrics

The Calculated Metrics Builder provides a canvas to drag and drop Dimensions, Metrics, Filters, and Functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple calculated metrics or complex advanced calculated metrics.

There are several ways to get to the Calculated Metric Builder:

* In Analysis Workspace, open a project and click  **[!UICONTROL + New]** > **[!UICONTROL Create Metric]** .
* In [!DNL Analytics], go to **[!UICONTROL Components]** > **[!UICONTROL Calculated Metrics]**.

* Click **[!UICONTROL + Add]** at the top of the [Calculated Metric Manager](/help/components/calc-metrics/cm-workflow/cm-manager.md), or 

* Go to **[!UICONTROL Analytics]** > **[!UICONTROL Reports]**, open any report and click the Metrics icon  ![](assets/metrics_icon.png) to bring up the Metrics rail, then click **[!UICONTROL Add]**.

![](assets/cm_builder_ui.png)

## UI Components {#ui-components}

| Field | Description |
| --- | --- |
| Title | Naming the metric is mandatory. You cannot save the metric unless it is named. |
| Description | Give it a user-friendly description to show what it's used for and to distinguish it from similar ones. The description also appears within a report. It's best NOT to put the formula into the description - instead, describe what this metric should and should not be used for. (The formula is generated as you build the metric, underneath the Summary heading. As a result, there is no need to add the formula to the description.) |
| Format | Choices include Decimal, Time, Percent, and Currency. |
| Decimal Places | Shows how many decimal places will be shown in the report. The maximum number of decimal places you can specify is 10. |
| Show Upward Trend As... | This metric polarity setting shows whether Analytics should consider an upward trend in the metric as good (green) or bad (red). As a result, the report's graph will show as green or red when it's going up. |
| Currency | 
| Tags | Tagging is a good way to organize metrics. All users can create tags and apply one or more tags to a metric. However, you can see tags only for those segments that you own or that have been shared with you. What kinds of tags should you create? Here are some suggestions for useful tags:<ul><li>Tags based on team names, such as Social Marketing, Mobile Marketing.</li><li>Project tags (analysis tags), such as Entry-page analysis.</li><li>Category tags: Men's; geography.</li><li>Workflow tags: To be approved; Curated for (a specific business unit)</li></ul> |
| Summary | The [!UICONTROL Summary] formula updates anytime you make a change to the metric definition. This formula also shows up in the metrics rail on the left when you hover over a metric and click the icon. |
| Definition | This is where you drag in metrics/calculated metrics, filters, and/or functions to build the calculated metric. If you drag in a calculated metric, it will expand its metric definition automatically. You can nest definitions with containers. However, unlike segment containers, these containers function like a math expression and determine the order of operations. |
| Operator | [!UICONTROL Divided by] is the default operator, plus there are the +, -, and x operators.|
| Preview | Provides a quick read on any possible errors. The preview covers the last 90 days. This is a way of initially gauging whether you have selected the right components for your metric. An unexpected result would mean you need to take a second look at the metric definition. |
| Add | For all types of calculated metrics, you can add containers and static numbers to the definition. For advanced calculated metrics, you can also add filters and functions.<ul><li>Containers function like a math expression and determine the order of operations. So anything in a container will get processed before the next operation.</li><li>Dragging a segment onto a container segments everything in that container. (Advanced calculated metrics only)</li><li>You can stack multiple filters in a container.</li></ul> |
| Gear icon (Metric Type, Attribution) | Selecting the gear icon next to a metric lets you specify the metric type and attribution models. |
| + New | Lets you create a new component, such as a new filter (which takes you to the  Filter Builder .)|
| Search Components | This search bar lets you search for dimensions, metrics, segments (advanced calculated metrics only), and functions (advanced calculated metrics only). |
| List of Dimensions | Rather than leaving the Calculated Metric Builder in order to build a simple filter (in the Filter Builder), e.g. "Page = Homepage", you can drag in Page and select Homepage directly from the Calculated Metric Builder. This results in a much more streamlined workflow for creating filtered calculated metrics.|
| List of Metrics | Metrics come in 3 categories:<ul><li>Standard metrics</li><li>Calculated metrics</li><li>Metrics templates - at the bottom of the list.</li></ul>When you hover over a metric, you can see the Info icon to the right of it. Clicking this icon gives you the following information:<ul><li>The formula of how it is calculated.</li><li>A preview trend of the metric.</li><li>An edit (pencil) icon at the top right that will take you to the Calculated Metrics Builder where you can edit this calculated metric.</li></ul> |
| List of Filters | (Advanced calculated metrics only) As an Admin, this list shows all filters created in your login company. If you are a non-Admin user, this list shows filters you own and those shared with you. |
| List of Functions | (Advanced calculated metrics only) Functions are divided into two lists: Basic (used most often) and Advanced .|
| Data view selector | This selector (at the top right) lets you switch to a different data view. |

