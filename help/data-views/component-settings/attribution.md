### Configure Attribution settings

![](assets/attribution-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Set attribution] | Lets you specify the attribution settings you want to apply to this metric by default when it is used. This default can be overridden in a [!UICONTROL Freeform Table] or in a Calculated Metric. |
| [!UICONTROL Attribution model] | Lets you specify a default attribution model - only active when you turn on the [!UICONTROL Use Non-default attribution model] setting. Defaults to [!UICONTROL Last Touch]. Options are: Last Touch, First Touch, Linear, Participation, Same Touch, U-Shaped, J Curve, Inverse J, Time Decay, Custom, Algorithmic. Some of these options create additional fields that need to be filled out - like Custom or Time Decay. You can create multiple metrics using the same field - this means you can have one [!UICONTROL Last touch] revenue metric and one [!UICONTROL First Touch] revenue metric, but based on the same revenue field in the schema. |
| [!UICONTROL Lookback window] | Lets you specify a default lookback window to a metric - only active when you turn on the [!UICONTROL Use Non-default attribution model] setting. Options are: [!UICONTROL Person] (Reporting Window), [!UICONTROL Session], [!UICONTROL Custom]. When [!UICONTROL Custom] is selected, we also give you the option to select any number of days/weeks/months/etc. (up to 90 days), just like [!UICONTROL Attribution IQ]. You can have multiple metrics using the same schema field, but each with a separate lookback window. |