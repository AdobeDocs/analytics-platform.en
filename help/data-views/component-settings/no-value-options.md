---
title: No value options component settings
description: Determine how to handle a dimension if it is empty.
---

# No Value Options component settings

No value options let you to determine how Analysis Workspace handles situations where an event in a dataset contains a metric but the dimension did not contain a value. You can choose the name of this dimension item, hide it entirely, or even treat it as an actual value.

![No value options](../assets/no-value-options.png)

| Setting | Description |
| --- | --- |
| [!UICONTROL If shown, call "No value"] | A text field that lets you rename the **[!UICONTROL No value]** dimension item to something else. |
| [!UICONTROL Don't show No value by default] | Does not show this value in reporting. Metric occurrences not tied to this dimension are not visible in the report. |
| [!UICONTROL Show No value by default] | Shows this value in reporting. |
| [!UICONTROL Treat No value as a value] | Replaces blank values in the data with the text that you specified under [!UICONTROL If shown, call "No value"]. For example, if you had Mobile device types as the dimension, you could rename the **[!UICONTROL No value]** item to "Desktop". When you change this field to a custom value, the custom value is treated as a legitimate string value. Therefore, if you enter the value "Red" into this field, any instances of the string "Red" appearing in the data itself rolls under the same line item that you have specified. |
