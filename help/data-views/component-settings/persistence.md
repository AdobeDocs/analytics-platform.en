---
title: Persistence Component Settings
description: Determine how or whether dimension values persist from one event to the next.
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---

# [!UICONTROL Persistence] component settings {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="Persistence"
>abstract="Configure the default allocation model applied to a dimension. Allocation applies before segments in reporting."

<!-- markdownlint-enable MD034 -->



[!UICONTROL Persistence] is the ability for a given dimension value to attribute to a metric beyond the event it is set on. It uses a combination of allocation and expiration.

![Data views window highlighting the Persistence options](../assets/persistence.png)

* **Allocation** lets you determine which value to keep when more than one dimension item can persist at a time in a single column.

  >[!NOTE]
  >
  >If you have a [non-default attribution model](/help/data-views/component-settings/attribution.md) set on a metric in a report, the attribution model ignores the allocation you set on the dimension for the same report.
  >
  >However, when doing a [full table export](/help/analysis-workspace/export/export-cloud.md) that includes multiple dimensions, attribution retains the allocation models applied to each dimension.

* **Expiration** lets you determine how long a dimension item persists beyond the event it is set on.

[!UICONTROL Persistence] is available only in dimensions, and is retroactive to the data it is applied to. It is an immediate data transformation that happens before segmenting or other analysis operations are applied.

| Setting | Description |
| --- | --- |
| [!UICONTROL Set persistence] | Enable persistence for the dimension. If persistence is not enabled, the dimension only relates to metrics that exist in the same event. This setting is disabled by default. |
| [!UICONTROL Allocation] | Specify the allocation model used on a dimension for persistence. Options are:<ul><li>**[!UICONTROL Most recent]**: Values in the dimension persist until overwritten by subsequent values</li><li> **[!UICONTROL Original]**: The first value for this dimension persists and is not overwritten by subsequent values</li><li>**[!UICONTROL All]**: All values for this dimension persist simultaneously</li><li>**[!UICONTROL First known]**: The first value for this dimension is used and will be applied to all events before and after.</li><li>**[!UICONTROL Last known]**: The last value for this dimension is used and will be applied to all events before and after.</li></ul> |
| [!UICONTROL Expiration] | Specify the persistence window for a dimension. Options are: <ul><li>**[!UICONTROL Session]** (default)</li><li>**[!UICONTROL Person]**</li><li>**[!UICONTROL Custom Time]**</li><li>**[!UICONTROL Metric]**</li></ul>. You might need to be able to expire the dimension on a purchase (such as internal search terms or other merchandising use cases). The maximum expiration time that you can set is 90 days. If you select an allocation of [!UICONTROL All], only [!UICONTROL Session] or [!UICONTROL Person] expiration is available. |

{style="table-layout:auto"}

## [!UICONTROL Allocation] settings

The available allocation settings are:

* **[!UICONTROL Most Recent]**: persists the most recent (by timestamp) value present in the dimension. Any subsequent values that occur within the dimension's expiration period replaces the previously persisting value. If "Treat 'No Value' as a value" is enabled on this dimension under [No value options](no-value-options.md), empty values overwrite previously persisted values. For example, consider the following table with [!UICONTROL Most recent] allocation and [!UICONTROL Session] expiration:

  | Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Dataset values |  | C | B |  | A |
  | Most recent allocation |  | C | B | B | A |

* **[!UICONTROL Original]**: Persists the original value by timestamp that is present within the dimension for the duration of the expiration period. If this dimension has a value, it is not overwritten when a different value is seen in a subsequent event. For example, consider the following table with [!UICONTROL Original] allocation and [!UICONTROL Session] expiration:

  | Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Dataset values |  | C | B |  | A |
  | Original allocation |  | C | C | C | C |

* **[!UICONTROL All]**: Acts similarly to the [!UICONTROL Participation] attribution model for metrics. Persists all values equally so each get full credit for the metric in reporting. For example, consider the following table with [!UICONTROL All] allocation and [!UICONTROL Session] expiration:

  | Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Dataset values | A | B | C |  | A |
  | All allocation | A | A,B | A,B,C | A,B,C | A,B,C |

* **[!UICONTROL First Known]** and **[!UICONTROL Last Known]**: (Jan 19, 2022 ) These two allocation models satisfy "entry" and "exit" dimension use cases. They take the first or last observed value for a dimension within a specified persistence scope (session, person, or custom time period with lookback) and apply it to all events within the specified scope. Example:

  | Dimension | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 |
  | --- | --- | --- | --- | --- | --- |
  | Timestamp (min) | 1 | 2 | 3 | 6 | 7 |
  | Original values |  | C | B |  | A |
  | First known | C | C | C | C | C |
  | Last known | A | A | A | A | A |


## [!UICONTROL Expiration] settings

The available expiration settings are:

* **Session**: Expires after a given session. Default expiration window.
* **Person Reporting Window**: Expires at the end of the reporting window.
* **Global Account Reporting Window** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Expires at the end of the reporting window.
* **Account Reporting Window** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Expires at the end of the reporting window.
* **Opportunity Reporting Window** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Expires at the end of the reporting window.
* **Buying Group Reporting Window** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}: Expires at the end of the reporting window.
* **Custom Time**: Expires after a specified time period (up to 90 days). This expiration option is only available for Original and Most Recent allocation models. When using time-based expiration, values previous to the start of your reporting window (up to 90 days) are considered.
* **Metric**: When this metric is seen in a event, immediately expire the persisted value in the dimension. You can use any metric as the expiration end for this dimension. This expiration option is only available for Original and Most Recent allocation settings.


## [!UICONTROL Binding Dimension]

A drop-down menu that lets you bind the persistence of a dimension value to dimension values in another dimension. Valid options include other dimensions included in the data view.

See [Using binding dimensions and metrics in Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) for examples on how to use binding dimensions effectively.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Binding dimensions](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/data-views/binding-dimensions-in-data-views){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## [!UICONTROL Binding Metric]

A drop-down menu that lets you choose a metric that acts as a binding trigger. Valid options include metrics included in the data view.

This setting only appears when the Binding Dimension is lower in the object array than the component. When the binding metric is present in an event, dimension values are copied from the event-level dimension down to the lower schema level of the binding dimension.

See the second example under [Using binding dimensions and metrics in Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md) for more information on how to use binding metrics effectively.
