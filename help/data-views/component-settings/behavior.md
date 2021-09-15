### Configure Behavior settings

Lets you specify how a metric should behave in reporting.

![](assets/behavior-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Count values] | For Boolean metrics only, this setting allows you to specify whether you want to [!UICONTROL Count True], [!UICONTROL Count False], or [!UICONTROL Count True or False] as the metric value. The default is [!UICONTROL Count True]. This gives you the actual value of a metric, such as "50" if there was an order value of 50. |
| [!UICONTROL Count instances] | Lets you specify whether a numeric or date type field used as a metric should count the times it was set rather than the value itself.<br> If you want to add up the instances of a numeric field and want to simply add up the number of times a field was *set* rather than the actual value inside.<br>This is useful for creating an [!UICONTROL Orders] metric from a [!UICONTROL Revenue] field, for example. If revenue was set, then we want to count 1 single order rather than the numeric revenue amount. |
| [!UICONTROL Lower case] | Used with string dimensions. De-duplicates rows that have the same value but different cases. If enabled, all instances of a dimension with the same value are reported as lower case. For example, your data set contains the values `"liverpool"`, `"Liverpool"`, and `"LIVERPOOL"` in a string dimension. If [!UICONTROL Lower case] is enabled, all three values are combined into `"liverpool"`. If disabled, all three values are treated as distinct values:<br>![case-sensitive dimension](assets/case-sens-workspace.png)<br>|

>[!NOTE]
>
>If you enable [!UICONTROL Lower case] on a lookup dataset dimension, multiple lookup values can exist for the same identifier. If this conflict happens, CJA uses the first ASCII collated value (Uppercase values precede lowercase values). Adobe advises against using lookup datasets that contain the same value when [!UICONTROL Lower case] is enabled.