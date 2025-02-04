---
description: Learn about the error messages and how to troubleshoot in Adobe Analysis Workspace
title: Common errors and troubleshooting in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
---
# Errors and troubleshooting

You may encounter errors when interacting with Analysis Workspace that can influence its functionality or performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

## Error messages

Some common error messages you might see when using Analysis Workspace:

| Error message | Why does the error occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL The data view is experiencing unusually heavy reporting. Please try again later.] | Your organization is trying to run too many concurrent requests against a specific data view. Contributors to this error are API requests, scheduled projects, scheduled reports, scheduled alerts, and concurrent users making reporting requests. | Spread your requests and schedules for the data view more evenly throughout the day.<p>Administrators can use the [Reporting Activity Manager to identify and cancel requests](/help/reporting-activity-manager/reporting-activity-overview.md) that are consuming reporting capacity.</p> |
| [!UICONTROL This report is too complex. Please review best practices for building Analysis Workspace reports.] |Your reporting request is too large and cannot be executed. Contributors to this error are timeouts due to the request's complexity. | Simplify your request. For example, shorten the date range, or simplify the filter criteria, or remove some columns or rows in your table. You might also consider splitting the table into separate requests. |
| [!UICONTROL The data view is currently exceeding its reporting capacity. Please simplify the request or try again later.] |  Your organization is trying to run too many concurrent requests against a specific data view. Contributors to this error are API requests, scheduled projects, and concurrent users making reporting requests. | Spread your requests and schedules for the data view more evenly throughout the day. |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](/help/technotes/ip-addresses.md), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |


## Troubleshooting

When using Analysis Workspae, you can use the information below to troubleshoot some common issues.

| Issue | How to troubleshoot |
|---|---|
| When I drag a metric over, it says *Invalid data*. | Invalid data means that Adobe cannot return data using the combination of dimensions and metrics used in the report. For example, two metrics stacked on top of each other cannot be returned as data, as there is no way to display two metrics that way. Instead, place the metrics side by side. |
| When I drag a metric over, I don't see any actual data - just zeros. | If you successfully created a workspace report but there's no data, there are a few things you can check:<ul><li>If you applied a filter in your report, the filter criteria might not match any data. Try removing the filter or adjusting the filter definition.</li><li>Check the date range in the upper right corner and make sure it's set to a value that you expect.</li><li>Navigate to your website and use the [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.</li></ul> |
