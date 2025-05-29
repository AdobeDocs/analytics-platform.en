---
title: No value options component settings
description: Determine how to handle a dimension if it is empty.
exl-id: c7f226c5-0058-4151-9c9a-652b37266beb
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# No Value Options component settings {#no-value-options-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_novalueoptions"
>title="No value options"
>abstract="Configure the default behavior for when no value is present in a dimension."

<!-- markdownlint-enable MD034 -->


[!UICONTROL No value options] let you to determine how Analysis Workspace handles situations where an event in a dataset contains a metric but the dimension did not contain a value. You can choose the name of this dimension item, hide it entirely, or even treat it as an actual value. 

![No value options](../assets/no-value-options.png)

## Settings {#settings}

| Setting | Description |
| --- | --- |
| **[!UICONTROL If shown, call "No value"]** | A text field that lets you rename the **[!UICONTROL No value]** dimension item to something else. |
| **[!UICONTROL Don't show "No value" by default]** | Does not show this value in reporting. Metric occurrences not tied to this dimension are not visible in the report. |
| **[!UICONTROL Show "No value" by default]** | Shows this value in reporting. |
| **[!UICONTROL Treat "No value" as a value]** | (Not supported for numeric dimensions) Replaces blank values in the data with the text that you specified under [!UICONTROL If shown, call "No value"]. For example, if you had Mobile device types as the dimension, you could rename the **[!UICONTROL No value]** item to "Desktop". When you change this field to a custom value, the custom value is treated as a legitimate string value. Therefore, if you enter the value "Red" into this field, any instances of the string "Red" appearing in the data itself rolls under the same line item that you have specified. |

## "No value" support for numeric dimensions {#numeric}

When using a numeric value as a dimension, you can 

* Configure the "No value" option in a data view. Note that all configuration settings shown above are supported except for **[!UICONTROL Treat "No value" as a value]**. 
* Use **[!UICONTROL Include "No value"]** for numeric dimensions in a Freeform table in Workspace.
* In the Segment builder, use the **[!UICONTROL exists]** or **[!UICONTROL does not exist]** operators with numeric dimensions.


>[!MORELIKETHIS]
>
>[The complete playbook for handling "No value" in Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/the-complete-playbook-for-handling-no-value-in-adobe-cja/ba-p/756696#M598).


