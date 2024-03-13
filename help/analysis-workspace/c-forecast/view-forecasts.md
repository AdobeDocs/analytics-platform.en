---
description: Learn how to view forecasts in a table or in a line chart.
title: How to view forecasts in Analysis Workspace
feature: Visualizations
role: User
exl-id: 4a8b602c-e6aa-4a46-bba9-642387e6af88
---
# View forecasts in Analysis Workspace

You can view forecasts in a freeform table or in a line chart.

## View forecasts in a table

You can view forecasts in a time-series freeform table. When [!UICONTROL Show forecast] is enabled for Freeform table in [user preferences](../user-preferences.md), forecasting is automatically shown for the first metric column added to the table. For any additional column:

1. Select the column settings icon ![Column settings](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in the column header, then ensure that **[!UICONTROL Show forecast]** is selected in the list of options. For more information, see [Column settings](../visualizations/freeform-table/column-row-settings/column-settings.md).

1. Click outside the **[!UICONTROL Column settings]** menu to save the setting and view the updated table.
   
Forecasts are shown in the table as follows:

![Show forecast in table](assets/show-forecast-table.png)

* The forecast value and percentage for each cell are displayed in **dark grey**.
* To indicate a forecast value, a forecast symbol <img src="./assets/forecast.svg" alt="Forecast symbol" width=20/> is displayed in the upper-right corner of the cell.


## View forecasts in a line chart

A line chart is the only visualization that allows you to view forecasts.

1. Select the settings icon ![Column settings](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in the visualization header, then ensure that **[!UICONTROL Show forecast]** is selected in the list of options.

1. (optional) To allow the forecasts to scale the chart properly, select **[!UICONTROL Allow forecast to scale Y-axis]**. This option is not selected by default because it can sometimes render a less legible chart.

1. Click outside the **[!UICONTROL Settings]** menu to view the updated line chart.

Forecasts are show in the line chart as follows:

![Show forecast in line chart](assets/show-forecast-linechart.png)

* The current values for the metrics in the line chart are indicated by a vertical bar. If you hover over that vertical line, a popup is displayed with the last current date.
* Forecasted values for one or more metrics are displayed right from the vertical bar using dotted lines. You can hover over any data point for a metric. This will show a popup with:
  * date of the forecast
  * forecasted value for the metric
  * upper bound of forecasted value for the metric
  * lower bound of forecasted value for the metric
* The shaded area shows the confidence band of the forecast.
