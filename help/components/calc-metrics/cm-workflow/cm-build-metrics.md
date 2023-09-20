---
description: The Calculated Metrics Builder provides a canvas to drag and drop Dimensions, Metrics, Filters, and Functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple calculated metrics or complex advanced calculated metrics.
title: Build Metrics
feature: Calculated Metrics
exl-id: 4d03a51d-c676-483c-98e2-d7283e8d71b0
---
# Build metrics

Customer Journey Analytics provides a canvas to drag and drop dimensions, metrics, filters, and functions to create custom metrics based on container hierarchy logic, rules, and operators. This integrated development tool lets you build and save simple calculated metrics or complex advanced calculated metrics.

## Begin building a calculated metric

You can begin creating a calculated metric in any of the follows ways:

* In Analysis Workspace, open a project, then select **[!UICONTROL Components]** > **[!UICONTROL Create metric]**.
* In Analysis Workspace, open a project, then select the **Plus** icon next to the [!UICONTROL **Metrics**] section in the left rail.
* In [!DNL Customer Journey Analytics], go to **[!UICONTROL Components]** > **[!UICONTROL Calculated metrics]**, then select **[!UICONTROL + Add]** at the top of the Calculated metrics page.

## Areas of the Calculated metrics builder

The following image and accompanying table explain some of the main areas and features of the Calculated metrics builder.

![](assets/cm_builder_ui.png)

| Field | Description |
| --- | --- |
| Title | Naming the metric is mandatory. You cannot save the metric unless it is named. |
| Description | Give it a user-friendly description to show what it's used for and to distinguish it from similar ones. <p>The description also appears within a report. It's best NOT to put the formula into the description - instead, describe what this metric should and should not be used for. (The formula is generated as you build the metric, underneath the Summary heading. As a result, there is no need to add the formula to the description.) </p> |
| Format | Choices include Decimal, Time, Percent, and Currency. |
| Decimal Places | Shows how many decimal places will be shown in the report. The maximum number of decimal places you can specify is 10. |
| Show Upward Trend As... | This metric polarity setting shows whether Analytics should consider an upward trend in the metric as good (green) or bad (red). As a result, the report's graph will show as green or red when it's going up. |
| Currency | The base currency for this data view. |
| Tags | Tagging is a good way to organize metrics. All users can create tags and apply one or more tags to a metric. However, you can see tags only for those filters that you own or that have been shared with you. What kinds of tags should you create? Here are some suggestions for useful tags:<ul><li>**Team names**, such as Social Marketing, Mobile Marketing.</li><li>**Projects** (analysis tags), such as Entry-page analysis.</li><li>**Categories**, such as Women's; Geography.</li><li>**Workflows**, such as To be approved; Curated for (a specific business unit)</li></ul> |
| Summary | <p>The Summary formula updates anytime you make a change to the metric definition. This formula also shows up in the metrics rail on the left when you hover over a metric and click the <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Info_18_N.svg" id="image_BDA0EAF89C19440CB02AE248BA3F968E" /> icon. </p> |
| Definition | This is where you drag in metrics/calculated metrics, filters, and/or functions to build the calculated metric. <ul><li>If you drag in a calculated metric, it will expand its metric definition automatically. </li> <li>You can nest definitions with containers. However, unlike filter containers, these containers function like a math expression and determine the order of operations. </li> </ul> |
| Operator | Divided by ( <img placement="inline"  src="https://spectrum.adobe.com/static/icons/workflow_18/Smock_Divide_18_N.svg" width="15" id="image_320D7363DE024BDEB21E44606C8B367F" width="25px" /> ) is the default operator, plus there are the +, -, and x operators. |
| Preview | Provides a quick read on any possible errors. The preview covers the last 90 days. This is a way of initially gauging whether you have selected the right components for your metric. An unexpected result would mean you need to take a second look at the metric definition. |
| Product compatibility | For any calculated metrics that you create in Customer Journey Analytics, this value is always listed as [!UICONTROL **Fully Processed Data**]. Calculated metrics can only include data from event datasets. |
| Add | For all types of calculated metrics, you can add containers and static numbers to the definition. For advanced calculated metrics, you can also add filters and functions.<ul><li>Containers function like a math expression and determine the order of operations. So anything in a container will get processed before the next operation.</li><li>Dragging a filter onto a container filters everything in that container. (Advanced calculated metrics only)</li><li>You can stack multiple filters in a container.</li></ul> |
| Gear icon (Metric Type, Attribution) | Selecting the gear icon next to a metric lets you specify the metric type and attribution models. <!-- <p>**Note:** Consider the following when updating a component's attribution to a non-default attribution model:</p><ul><li>**When using the component in a report with *a single dimension*:** The component's attribution ignores the allocation model when a non-default attribution model is used.</li><li>**When using the component in a report with *multiple dimensions*:** The component's attribution retains the allocation model when a non-default attribution model is used.</li><li>Multiple dimensions are available only when [exporting data to the cloud](/help/analysis-workspace/export/export-cloud.md).</li></ul> --> <p>For more information about allocation, see [Persistence component settings](/help/data-views/component-settings/persistence.md).</p>|
| Plus (+) icon | Lets you create a new component, such as a new filter (which takes you to the  Filter Builder .)|
| Search Components | This search bar lets you search for dimensions, metrics, filters (advanced calculated metrics only), and functions (advanced calculated metrics only). |
| List of Dimensions | Rather than leaving the Calculated metric builder in order to build a simple filter (in the Filter builder), e.g. "Page = Homepage", you can drag in Page and select Homepage directly from the Calculated metric builder. This results in a much more streamlined workflow for creating filtered calculated metrics.|
| List of Metrics | Metrics come in 3 categories:<ul><li>Standard metrics</li><li>Calculated metrics</li><li>Metrics templates - at the bottom of the list.</li></ul>When you hover over a metric, you can see the Info icon to the right of it. Clicking this icon gives you the following information:<ul><li>The formula of how it is calculated.</li><li>A preview trend of the metric.</li><li>An edit (pencil) icon at the top right that will take you to the Calculated metric builder where you can edit this calculated metric.</li></ul> |
| List of Filters | (Advanced calculated metrics only) As an Admin, this list shows all filters created in your login company. If you are a non-Admin user, this list shows filters you own and those shared with you. |
| List of Functions | (Advanced calculated metrics only) Functions are divided into two lists: Basic (used most often) and Advanced .|
| Data view selector | This selector (at the top right) lets you switch to a different data view. |
