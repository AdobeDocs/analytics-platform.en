---
title: Attribution component settings
description: Lets you set default attribution for a metric.
exl-id: bc7ae6e3-7c9b-4994-97ce-690f3bdcbee5
---
# Attribution component settings

Attribution lets you set a default attribution model for a metric. You can override a given metric's attribution model while working in Analysis Workspace.

![Attribution](../assets/attribution-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Set attribution] | Enables a default attribution model when this metric is used. This default can be overridden in a [!UICONTROL Freeform Table] or in a Calculated Metric. |
| [!UICONTROL Attribution model] | Lets you specify which default [attribution model](/help/analysis-workspace/attribution/models.md) to use. Defaults to [!UICONTROL Last Touch]. Options are: Last Touch, First Touch, Linear, Participation, Same Touch, U-Shaped, J Curve, Inverse J, Time Decay, Custom, Algorithmic. Some of these options create additional fields that need to be filled out - like Custom or Time Decay. You can create multiple metrics using the same field - this means you can have one [!UICONTROL Last touch] revenue metric and one [!UICONTROL First Touch] revenue metric, but based on the same revenue field in the schema. |
| [!UICONTROL Lookback window] | Lets you specify a default lookback window to a metric. Options are: [!UICONTROL Person] (Reporting Window), [!UICONTROL Session], [!UICONTROL Custom]. When [!UICONTROL Custom] is selected, we also give you the option to select any number of days/weeks/months/etc. (up to 90 days), just like [!UICONTROL Attribution IQ]. You can have multiple metrics using the same schema field, but each with a separate lookback window. |
