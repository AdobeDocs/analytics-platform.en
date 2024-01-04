---
description: Learn about the error messages in Adobe Analysis Workspace and its related components
title: Common error messages in Analysis Workspace
feature: FAQ
exl-id: 792c3b2e-bd24-4e98-b9ea-983c1189d52e
role: User
---
# Common error messages

You may encounter errors when interacting with Analysis Workspace that will also influence performance. Listed below are the most common error types, why they occur, and optimizations that can be made.

| Error message | Why does this occur? | Optimization |
| --- | --- | --- |
| [!UICONTROL A system error has occurred. Please log a Customer Care request under **[!UICONTROL Help > Submit Support Ticket]** and include your error code.] | Adobe is experiencing an issue that needs to be resolved. | Submit the error code to Customer Care. |
| [!UICONTROL Error 500: Failed to load page] | Issues with your local network, such as company [firewall settings](https://experienceleague.adobe.com/docs/analytics/technotes/ip-addresses.html), are a contributing factor to this error. Additionally, Adobe may be experiencing an issue that needs to be resolved. | Try logging in again after several minutes. If the issue persists, submit the EIM instance ID code to Customer Care. |
| [!UICONTROL One of the filters or the search in this visualization contains a text search that returned too many results.] | Your filter criteria or report filter is too broad. | Narrow your search text criteria and try the request again. |
| [!UICONTROL The request is too complex.] |Your reporting request is too large and cannot be executed. Contributors to this error are timeouts due to the request's size, too many matched items in a filter or search filter, too many metrics included, incompatible dimension and metric combinations, etc. | Simplify your request by removing some columns or rows in your table, or consider splitting the table into separate requests. |
| [!UICONTROL Your request failed as a result of too many columns or pre-configured rows.] | Your table has too many freeform cells (row * columns). | Remove columns or rows in your table, or consider splitting the table into separate requests. |
