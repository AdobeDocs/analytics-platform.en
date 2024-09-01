---
title: Calculated metrics overview
description: Learn about filtered metrics that are derived at report run time.
feature: Calculated Metrics
exl-id: c9205c95-8b01-4177-a89c-038886f41d3d
role: User
---
# Calculated metrics overview

Calculated and Advanced Calculated (or Derived) Metrics are custom metrics that you can create from existing metrics. Our Calculated Metrics tools offer a highly flexible way of building, managing and curating metrics. They allow you as marketers, product managers and analysts to ask questions of the data without having to change your implementation.

You can

* Create filtered metrics that are derived at report run time, without having to change the implementation. These can be viewed historically because they are based on filters.
* (Advanced Calculated Metrics only) Filter on metrics. For example, you can create a metric for "New persons", with a count of people for whom this is the first session.
* (Advanced Calculated Metrics only) Incorporate statistical functions to help you better describe your data. For example, you can count the number of items in a report or add in the number of standard deviations for each item.


You can build and save calculated metrics in the [Calculated metrics builder](cm-workflow/cm-build-metrics.md). This builder allows you to:

* Create calculated and advanced calculated metrics using advanced allocation models.
* Add filters inline to metric formulas.
* Compare filters in the same report. For example, compare local persons vs. international persons.
* Use statistical functions.
* Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it).
* Copy definitions into new metrics.
* Provide an inline metric preview.
* Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up.
* Tag metrics

You use the [Calculated metrics manager](cm-workflow/cm-manager.md) to collect, tag, approve, favor, share and export calculated metrics across your organization.

See [Create filters](/help/components/filters/create-filters.md) for the various options available to create filters.

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

## Calculated Metrics templates in Customer Journey Analytics

| Calculated Metric Name | Calculated Metric description |
| --- | --- |
| Sessions Per Person | Average number of sessions per person |
| Session Start Rate | The percent of time that any dimension item occurred on the first event of a session. |
| Session End Rate | The percent of time that any dimension item occurred on the last event of a session. |
| Time Spent per Person | The average amount of time a person spent on any given dimension item. |
| Time Spent Per Session | The average amount of time a person spent per Session on any given dimension item. |
