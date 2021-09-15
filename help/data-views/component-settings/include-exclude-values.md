### Configure Include/Exclude Values settings

This setting allows you to modify the underlying data that you are reporting on, at query time. It is not the same as a filter. But filters will respect this new dimension, as will pathing and attribution.

For example, you could create a dimension out of the pageTitle field, but call it "error pages" and include any page that [!UICONTROL contains the phrase] "error".

![](assets/include-exclude.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Case sensitive] | Default = On. This setting applies only to the [!UICONTROL Include/Exclude Values] section. It allows you to say whether the include/exclude rule you are applying should be case sensitive. |
| [!UICONTROL Match] | Lets you specify which values you would like to consider for reporting prior to attribution and filters (e.g., only use values containing the phrase "error"). You can specify: **[!UICONTROL If all criteria are met]**, or **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Lets you specify the match logic that should be applied to a specific filter rule.<ul><li>**String**: Contains the phrase, Contains any term, Contains all terms, Does not contain any term, Does not contain the phrase, Equals, Does not equal, Starts with, Ends wit</li><li>**Double/Integer**: equals, does not equal, is greater than, is less than, is greater than or equal to, is less than or equal to</li><li>**Date**: equals, does not equal, is later than, is before, occurs within</li></ul> |
| [!UICONTROL Match operand] | Lets you specify the match operand that the match operator should be applied to.<ul><li>**String**: Text field</li><li>**Double/Integer**: Text Field with up/down arrows for numeric values</li><li>**Date**: Day granularity selector (calendar)</li><li>**Date Time**: Date and time granularity selector</li></ul> |
| [!UICONTROL Add rule] | Lets you specify an additional match operator and operand. |