---
title: Calculated metrics overview
description: Learn about filtered metrics that are derived at report run time.
feature: Calculated Metrics
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
role: User
---
# Calculated metrics overview

Calculated metrics are metrics that you create from existing metrics and offer a flexible way to build, manage and curate custom defined metrics. Calculated metrics allow marketers, product managers and analysts to analyze data without having to change the implementation.

A typical workflow for calculated metrics consists of the following steps:

| Workflow Task | Description |
| --- | --- |
| Plan | Especially, for metrics that are going to be officially approved ![Checkmark](/help/assets/icons/Checkmark.svg), carefully plan and structure the calculated metrics you anticipate being used often.  |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | Build, modify, and save calculated metrics. |
| [Apply](/help/components/use-components-in-workspace.md) | Apply calculated metrics directly within your Workspace projects. |
| [Manage](/help/components/calc-metrics/cm-workflow/cm-manager.md) | Manage calculated metrics. You can [tag](/help/components/calc-metrics/cm-workflow/cm-tagging.md), [approve](/help/components/calc-metrics/cm-workflow/cm-approving.md), [unapprove](/help/components/calc-metrics/cm-workflow/cm-approving.md), [filter](/help/components/calc-metrics/cm-workflow/cm-filter.md), [favor](/help/components/calc-metrics/cm-workflow/cm-favorite.md) or [unfavor](/help/components/calc-metrics/cm-workflow/cm-favorite.md), [share](/help/components/calc-metrics/cm-workflow/cm-sharing.md), or [copy](/help/components/calc-metrics/cm-workflow/cm-copy.md) one or more calculated metrics. |


<!--
Let's review this, as it does not really make sense....



* Create filtered metrics that are derived at report run time, without having to change the implementation. These can be viewed historically because they are based on filters.
* (Advanced Calculated Metrics only) Filter on metrics. For example, you can create a metric for "New persons", with a count of people for whom this is the first session.
* (Advanced Calculated Metrics only) Incorporate statistical functions to help you better describe your data. For example, you can count the number of items in a report or add in the number of standard deviations for each item.
* Plan Calculated Metrics. Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined.
* [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components.
* [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization.
* [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical.
* Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]).
* Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.)
* Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.
-->

See [Create calculated metrics](/help/components/filters/create-filters.md) for the various options available to create calculated metrics. You build, modify, and save the definition of the calculated metrics in the [Calculated metrics builder](cm-workflow/cm-build-metrics.md).

You use calculated metric directly in Analysis Workspace. See [Use components in Analysis Workspace](/help/components/use-components-in-workspace.md)

You manage calculated metrics in the [Calculated metrics manager](cm-workflow/cm-manager.md).

<!--
## Calculated metrics versus advanced calculated metrics

Here is a comparison of Calculated Metrics and Advanced Calculated Metrics capabilities: 

|  <br/>Builder Options  | <br/>Calculated Metrics  | Advanced Calculated<br/>(Derived) Metrics  |
|---|:---:|:---:|
| Format types (decimal, time, percent, currency)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  |
| Attribution changes (default, linear, participation, etc.)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  |
| Metric types (standard, total) | ![Checkmark](/help/assets/icons/Checkmark.svg)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  |
| Apply filters | ![Close](/help/assets/icons/Close.svg)  | ![Checkmark](/help/assets/icons/Checkmark.svg)  |
| [Basic functions (count, abs value, mean, and more)](/help/components/calc-metrics/cm-functions.md)  | ![Close](/help/assets/icons/Close.svg)   | ![Checkmark](/help/assets/icons/Checkmark.svg)  |
| [Advanced functions (regression, if/then, t-score, and more)](/help/components/calc-metrics/cm-adv-functions.md)  | ![Close](/help/assets/icons/Close.svg)   | ![Checkmark](/help/assets/icons/Checkmark.svg)  |

## Tools

| Tool | Capabilities |
|--- |--- |
|Calculated metric builder|The calculated metric builder allows you to:<ul><li>Create calculated and advanced calculated metrics using advanced allocation models.</li><li>Add filters inline to metric formulas.</li><li>Compare filters in the same report. For example, compare local persons vs. international persons.</li><li>Use statistical functions.</li><li> Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it).</li><li>Copy definitions into new metrics.</li><li>Provide an inline metric preview.</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up.</li><li>Tag metrics.</li></ul>|
|Calculated metric manager|<ul><li>Share metrics with others.</li><li>Approve and curate metrics.</li><li>Organize (tag) your metrics so people can find them.</li><li>Delete metrics.</li><li>Rename metrics.</li></ul>|
|API for Calculated Metrics|Part of the Customer Journey Analytics API set.|

-->
## Default calculated metrics

Adobe provides a number of default calculated metrics, identified by ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg). See [Default calculated metrics](/help/components/calc-metrics/default-calcmetrics.md) for more information.
