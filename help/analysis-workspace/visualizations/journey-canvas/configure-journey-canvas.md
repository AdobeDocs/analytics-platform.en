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
   | [!UICONTROL **Primary metric**] | The primary metric affects the following aspects of the Journey canvas visualization:  <ul><li>Defines how users move through the journey.</li><li>The total number shown on each node.<p>For example, if People is the primary metric, each node shows the number of people who reached that node in the journey.</p></li><li>The percentage shown on each node. (After the visualization is built, you can choose to show either the percentage of the total or of the previous node.)</li><p>For example, if People is the primary metric, each node shows the percentage of people who reached that node in the journey (either the percentage of the total or of the previous node).</p></li><li>When a dimension is added to the visualization, the top 3 nodes of the visualization are added, based on the primary metric.</li></ul>  | 
   | [!UICONTROL **Secondary metric**] | The secondary metric is optional. When one is selected, the following information is shown on each node below the primary metric: <ul><li>The total number<p>For example, if Sessions is the secondary metric, each node shows the number of sessions that reached that node in the journey.</p></li><li>The percentage (After the visualization is built, you can choose to show either the percentage of the total or of the previous node.)</li><p>For example, if Sessions is the secondary metric, each node shows the percentage of sessions that reached that node in the journey (either the percentage of the total or of the previous node).</p></li></ul> |
   | [!UICONTROL **Journey Optimizer journey**]<!-- name? --> |  Select the Journey Optimizer journey that you want to use as the basis for your analysis in Journey canvas. (Alternatively, you can leave this option blank if you want a blank canvas from which to build your analysis within Analysis Workspace.)</p> <p>When you analyze a Journey Optimizer journey in Journey canvas, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer. For more information, see [Analyze Journey Optimizer journeys](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in [Journey canvas overview](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Note**: This option displays only when Journey Optimizer data is detected in the same data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</p> |

1. (Optional) Select [!UICONTROL **Show advanced settings**], then specify the following information:

   | Field | Function | 
   |---------|----------|
   | [!UICONTROL **Journey canvas container**] | Choose the container that you want to focus on throughout the journey. The container that you choose determines the statistics that are displayed in the visualization. (If your container names differ from the default names shown below, they were customized in your data view.)<ul><li>**Sessions:** Constrains the statistics of the visualization to fall within a single defined session for a given user. This means that the numbers and percentages that appear on each node (that are based on the primary and secondary metrics) must occur within a single session for each user.</li><li>**People:** Allows the statistics of the visualization to span multiple sessions for a given user. This means that the numbers and percentages that appear on each node (that are based on the primary and secondary metrics) can occur across any number of sessions, as long as the sessions belong to the same user. This is the default setting.</li></ul> | 

1. Select [!UICONTROL **Build**].

   If you have Journey Optimizer and you selected a Journey Optimizer journey, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer. 

   <!-- add screen shot -->

   If you do not have Journey Optimizer or if you didn't select a Journey Optimizer journey, a blank canvas displays where you can begin populating the journey.

   <!-- add screen shot -->

1. Whether you are creating a new analysis from a blank canvas or you are are analyzing a Journey Optimizer journey, you can configure the journey as described in [Configure a Journey canvas visualization](#begin-building-a-journey-canvas-visualization). 


## Configure a Journey canvas visualization

You need to [build a Journey canvas visualization](#begin-building-a-journey-canvas-visualization) before you can configure it as described in the following sections. 

### Configure settings

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Configure any of the following settings that are displayed across the top of the visualization:

   | Setting | Function | 
   |---------|----------|
   | [!UICONTROL **Node type**] | Allows you to configure which node types are shown in the visualization. To hide a node type from the visualization, select the (x) next to the node type, or deselect it from the drop-down menu. To show a hidden node type, select it from the drop-down menu. <p>Depending on the contents of your visualization, possible node types include:</p><ul><li>[!UICONTROL **Read segment**]</li><li>[!UICONTROL **End**]</li><li>[!UICONTROL **Dimension**]</li><li>[!UICONTROL **Metric**]</li></ul>  | 
   | [!UICONTROL **Percentage value**] | B2 | 
   | [!UICONTROL **Arrow settings**] | Choose from the following options:<ul><li>[!UICONTROL **None**]: </li><li>[!UICONTROL **Condition**]: </li><li>[!UICONTROL **All labels**]: </li></ul><p>**Note**: This option displays only when Journey Optimizer data is detected in the same data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</p>  |
   | [!UICONTROL **Show fallout**] | B3 |

### Add a node

Nodes in a Journey canvas visualization represent the events or actions of a user journey. You create nodes by dragging Workspace components from the left rail to the canvas.

Nodes display as a rectangular box with the following information:

* Component name

* The component type (such as metric or dimension)

* Primary metric statistics (total and percent)

* Secondary metric statistics (total and percent) 

To add a node to a Journey canvas visualization:

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Drag a metric, dimension, or dimension item from the left rail onto the canvas. 

   The visualization is updated as follows, depending on the area of the canvas where you place the component: 
   
   | Placement of component | Visualization updates | 
   |---------|----------|
   | Blank area of the canvas | The node displays where the component was dropped, unconnected with any existing nodes. | 
   | An existing node | Components automatically combine to form a new node with the same OR/AND logic as fallout.<p>See [Combine nodes](#combine-nodes) for more information.</p> |
   | An arrow that connects 2 existing nodes | The node displays between the two existing nodes where it was dropped and is connected to both existing nodes. <p>See [Connect nodes](#connect-nodes) for more information.</p> | 
   | The edge of an existing node | The node displays next to the node where it was dropped and is connected to it. <p>See [Connect nodes](#connect-nodes) for more information.</p> |

### Connect nodes

The connection between nodes in Journey canvas determines the sequence of events in the journey. 

To connect nodes in Journey canvas:

1. Select either of the 2 nodes that you want to connect. 

1. Select any of the 4 blue dots that appear on each side of the node.

1. Drag the dot to any of the 4 sides of the node that you want to connect to. 

### Combine nodes

The logic that is applied to nodes when they are combined differs depending on the component types you are combining, as follows:

* When you combine multiple filters, they are joined with AND.

* When you combine multiple dimension items or metrics, they are joined with OR.

Do either of the following to combine nodes in Journey canvas:

* Drag a node onto another node.

* Select the nodes that you want to combine, right-click one of the selected nodes, then select **Combine**.<!--Is there a limit on how many you can combine? -->

### Rearrange nodes

Journeys in Journey canvas consist of a flexible graph of nodes and arrows representing any combination of events, dimension items, and filters. 

You can drag nodes on the canvas to rearrange the events and conditions of the journey. As you do, data updates accordingly. 

### Manage existing nodes

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Right-click an **individual node** on the canvas, then select any of the following options:
   
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Create segment**] | B1 |
   | [!UICONTROL **Publish audience**] | B2 |
   | [!UICONTROL **Trend**] | B3 | 
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Get top next ...**] | B2 |
   | [!UICONTROL **Change color**] | B2 |
   | [!UICONTROL **Rename**] | B2 |
   | [!UICONTROL **Delete**] | B2 |

1. Select **multiple nodes** on the canvas, right-click one of the selected nodes, then select any of the following options:

   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Combine**] | B1 |
   | [!UICONTROL **Delete**] | B2 |
   | [!UICONTROL **Duplicate**] | B3 | 
   | [!UICONTROL **Trend**] | B2 |
   | [!UICONTROL **Breakdown**] | B2 |
   | [!UICONTROL **Create segment**] | B2 |
   | [!UICONTROL **Publish audience**] | B2 |


## Open a journey from Journey Optimizer


In Journey Optimizer, open the journey that you want to analyze in Journey canvas.

1. Select [!UICONTROL **Analyze in CJA**]. <!-- ?? -->

