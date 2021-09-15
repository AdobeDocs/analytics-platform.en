### Configure [!UICONTROL No Value Options] settings

[!UICONTROL No Value Options] settings are analogous to [!UICONTROL Unspecified] or [!UICONTROL None] values in reporting. In the data views UI, on a component-by-component basis, you can decide how you want these values to be treated in reporting. You can also rename [!UICONTROL No value] to something that better suits your environment, such as [!UICONTROL Null], [!UICONTROL Not set], or others.

Also note that whatever you specify in this field can be used for special UI treatment of the [!UICONTROL No Value] line item in reporting as stated in the [!UICONTROL No Value Options] setting.

![](assets/no-value-options.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL If shown, call No value...] | This is where you can rename **[!UICONTROL No value]** to something else. |
| [!UICONTROL Don't show No value by default] | Does not show this value in reporting. |
| [!UICONTROL Show No value by default] | Does show this value in reporting. |
| [!UICONTROL Treat No value as a value] | This setting replaces blank values in the data with the text that you specified under [!UICONTROL If shown, call No value ...]. For example, if you had Mobile device types as the dimension, you could rename the **[!UICONTROL No value]** item to "Desktop". Note that when you change this field to a custom value, the custom value is treated as a legitimate string value. Therefore, if you enter the value "Red" into this field, any instances of the string "Red" appearing in the data itself rolls under the same line item that you have specified.|