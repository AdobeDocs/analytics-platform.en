---
title: Include Exclude values component settings
description: Conditionally include or exclude a dimension item depending on its value.
exl-id: 1a3f8ab5-bd82-415a-989a-f93e6714df4b
---
# Include Exclude values component settings

Include Exclude values lets you create rules that depend on the value of a dimension item. Values that don't meet the criteria that you set are treated in Analysis Workspace as if they never existed, though the data still exists in the underlying dataset.

![Include exclude](../assets/include-exclude.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Set include/exclude values] | A checkbox that lets you enable conditions where data is included in a data view. |
| [!UICONTROL Case sensitive] | Visible on String schema data types. Defaults to on. This setting applies only to the [!UICONTROL Include/Exclude Values] logic, not to the resulting value. It allows you to specify if the rule is case sensitive. |
| [!UICONTROL Match] | Lets you specify which values you would like to consider for reporting prior to attribution and filters (e.g., only use values containing the phrase "error"). You can specify **[!UICONTROL If all criteria are met]** or **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Lets you specify the match logic that should be applied to a specific filter rule.<ul><li>**String**: Contains the phrase, Contains any term, Contains all terms, Does not contain any term, Does not contain the phrase, Equals, Does not equal, Starts with, Ends wit</li><li>**Double/Integer**: equals, does not equal, is greater than, is less than, is greater than or equal to, is less than or equal to</li><li>**Date**: equals, does not equal, is later than, is before, occurs within</li></ul> |
| [!UICONTROL Match operand] | Lets you specify the match operand that the match operator should be applied to.<ul><li>**String**: Text field</li><li>**Double/Integer**: Text Field with up/down arrows for numeric values</li><li>**Date**: Day granularity selector (calendar)</li><li>**Date Time**: Date and time granularity selector</li></ul> |
| [!UICONTROL Add rule] | Lets you specify an additional match operator and operand. |
