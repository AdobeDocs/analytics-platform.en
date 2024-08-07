---
description: Configure a Journey canvas visualization
title: Journey canvas
feature: Visualizations
role: User
---
# Configure a Journey canvas visualization

The Journey canvas visualization allows you to analyze and gain deep insights on the journeys that you provide to your users and customers. 

## Journey canvas overview

See [Journey canvas overview](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md) to learn more about Journey canvas, including:

* Key features

* Differences between Journey canvas and Fallout

* Details about analyzing Journey Optimizer journeys

* And more

## Begin building a Journey canvas visualization

1. Add a blank panel to your project, select the [!UICONTROL **Visualizations**] icon in the left rail, then drag the [!UICONTROL **Journey canvas**] visualization into the panel.

   Or

   Add a the Journey canvas visualization in any of the ways described in the [Add visualizations to a panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) section in [Visualizations overview](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Specify the following basic information:
   
   | Field | Function | 
   |---------|----------|
   | [!UICONTROL **Primary metric**] | The primary metric affects the following aspects of the Journey canvas visualization:  <ul><li>The total number shown on each node.<p>For example, if People is the primary metric, each node shows the number of people who reached that node in the journey.</p></li><li>The percentage shown on each node. (After the visualization is built, you can choose to show either the percentage of the total or of the previous node.)</li><p>For example, if People is the primary metric, each node shows the percentage of people who reached that node in the journey (either the percentage of the total or of the previous node).</p></li><li>When a dimension is added to the visualization, the top 3 nodes of the visualization are added, based on the primary metric.</li></ul>  | 
   | [!UICONTROL **Secondary metric**] | The secondary metric is optional. When one is selected, the following information is shown on each node below the primary metric: <ul><li>The total number<p>For example, if Sessions is the secondary metric, each node shows the number of sessions that reached that node in the journey.</p></li><li>The percentage (After the visualization is built, you can choose to show either the percentage of the total or of the previous node.)</li><p>For example, if Sessions is the secondary metric, each node shows the percentage of sessions that reached that node in the journey (either the percentage of the total or of the previous node).</p></li></ul> |
   | [!UICONTROL **Journey Optimizer journey**]<!-- name? --> |  Select the Journey Optimizer journey that you want to use as the basis for your analysis in Journey canvas. (Alternatively, you can leave this option blank if you want a blank canvas from which to build your analysis within Analysis Workspace.)</p> <p>When you analyze a Journey Optimizer journey in Journey canvas, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer. For more information, see [Analyze Journey Optimizer journeys](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in [Journey canvas overview](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Note**: This option displays only when Journey Optimizer data is detected in the same data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</p> |

1. (Optional) Select [!UICONTROL **Show advanced settings**], then specify the following information:

   | Field | Function | 
   |---------|----------|
   | [!UICONTROL **Journey canvas container**] | Select from the following options: <ul><li>[!UICONTROL **Session**]: </li><li>[!UICONTROL **People**]: <p>This option is selected by default.</p></li></ul> | 

1. Select [!UICONTROL **Build**].

   If you have Journey Optimizer and you selected a Journey Optimizer journey, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer. For more information, see [Analyze Journey Optimizer journeys](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in [Journey canvas overview](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md)

   If you do not have Journey Optimizer or if you didn't select a Journey Optimizer journey, a blank canvas displays where you can begin populating the journey, as described in [Configure a journey](#configure-a-journey).


## Configure a journey





## Open a journey from Journey Optimizer


In Journey Optimizer, open the journey that you want to analyze in Journey canvas.

1. Select [!UICONTROL **Analyze in CJA**]. <!-- ?? -->

