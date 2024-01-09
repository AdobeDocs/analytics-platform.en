---
description: Learn how to view forecasting in a table or in a line chart.
title: How to view forecasting in Analysis Workspace
feature: Forecasting
role: User
---
# View forecasts in Analysis Workspace

You can view forecasts in a freeform table or in a line chart.

## View forecasting in a table

You can view forecasting in a time-series freeform table.

1. Select the column settings icon ![Column settings](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in the column header, then ensure that **[!UICONTROL Show forecasting]** is selected in the list of options. For more information, see [Column settings](/help/visualizations/freeform-table/column-row-settings/column-settings.md).

1. Click outside the **[!UICONTROL Column settings]** menu to save the setting and view the updated table.
   
1. Forecasts are shown in the table as follows:

    ![Show forecasts in table](assets/show-forecast-table.png)

    * The value and percentage for each cell are displayed in **dark grey**.
    * A forecast symbol <img src="./assets/forecast.svg" alt="Forecast symbol" width=20/> is displayed in the upper-right corner of the cell.


## View forecasting in a line chart

A line chart is the only visualization that allows you to view forecasting.

1. Select the settings icon ![Column settings](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg) in the visualization header, then ensure that **[!UICONTROL Show forecast]** is selected in the list of options.

1. (optional) To allow the forecasts to scale the chart properly, select Allow forecasting to scale Y-axis. This option is not selected by default because it can sometimes render a less legible chart.

1. Click outside the **[!UICONTROL Settings]** menu to view the updated line chart.

1. Forecasts are show in the line chart as follows:

    ![Show forecast in line chart](assets/show-forecast-linechart.png)

    * The current values for the metrics in the line chart are indicated by a vertical bar. If you hover over that vertical line, a popup is displayed with the last current date.
    * Forecasted values for one or more metrics are displayed right from the vertical bar using dotted lines. You can hover over any data point for a metric. This will show a popup with:
      * date of the forecast
      * forecasted value for the metric
      * upper bound of forecasted value for the metric
      * lower bound of forecasted value for the metric
    * the shaded area shows the confidence band of the forecast.

