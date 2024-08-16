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

* Potential insights

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
   | [!UICONTROL **Primary metric**] | The primary metric affects the following aspects of the Journey canvas visualization:  <ul><li>Defines how users move through the journey.</li><li>The total number shown on each node.<p>For example, if People is the primary metric, each node shows the number of people who reached that node in the journey.</p></li><li>The percentage shown on each node. (After the visualization is built, you can choose to show either the percentage of the total or of the starting node.)</li><p>For example, if People is the primary metric, each node shows the percentage of people who reached that node in the journey (either the percentage of the total or of the starting node).</p></li><li>When a dimension is added to the visualization, the top 3 nodes of the visualization are added, based on the primary metric.</li></ul>  | 
   | [!UICONTROL **Secondary metric**] | The secondary metric is optional. When one is selected, the following information is shown on each node below the primary metric: <ul><li>The total number<p>For example, if Sessions is the secondary metric, each node shows the number of sessions that reached that node in the journey.</p></li><li>The percentage (After the visualization is built, you can choose to show either the percentage of the total or of the starting node.)</li><p>For example, if Sessions is the secondary metric, each node shows the percentage of sessions that reached that node in the journey (either the percentage of the total or of the starting node).</p></li></ul> |
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
   | [!UICONTROL **Node type**] | Allows you to configure which node types are shown in the visualization. To hide a node type from the visualization, select the (x) next to the node type, or deselect it from the drop-down menu. To show a hidden node type, select it from the drop-down menu. <p>Depending on the contents of your visualization, possible node types include:</p><ul><li>[!UICONTROL **Read segment**]</li><li>[!UICONTROL **End**]</li><li>[!UICONTROL **Dimension**]</li><li>[!UICONTROL **Metric**]</li></ul><p>**Note**: This option displays only when Journey Optimizer data is detected in the same data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</p>   | 
   | [!UICONTROL **Percentage value**] | Choose from the following options: <ul><li>[!UICONTROL **Percent of total**]: The percent of all of the people included in the data view within the panel's date range.</li><li>[!UICONTROL **Percent of start node**]: The percent of all the people included in the start node.</li></ul> | 
   | [!UICONTROL **Arrow settings**] | Choose from the following options:<ul><li>[!UICONTROL **None**]: </li><li>[!UICONTROL **Condition**]: </li><li>[!UICONTROL **All labels**]: </li></ul><p>**Note**: This option displays only when Journey Optimizer data is detected in the same data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</p>  |
   | [!UICONTROL **Show fallout**] | B3 |

1. Continue with [Add a node](#add-a-node).

### Add a node

Nodes in a Journey canvas visualization represent the events or actions of a user journey. You create nodes by dragging Workspace components from the left rail to the canvas.

To add a node to a Journey canvas visualization:

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Drag a metric, dimension, or dimension item from the left rail onto the canvas. Calculated metrics and any metrics that include segmentation are not supported.
     
   You can select multiple components by holding Shift, or by holding Command (on Mac) or Ctrl (on Windows).

   The visualization is updated as follows, depending on the component type and the area of the canvas where you place it: 
   
   |  Component type | Placement of component | Visualization updates after node is added | 
   |---------|----------|----------|
   | Metric | Blank area of the canvas | The node displays where the component was dropped, unconnected with any existing nodes. | 
   | Metric | An existing node | Components automatically combine to form a new node with the same OR/AND logic as fallout.<p>See [Combine nodes](#combine-nodes) for more information.</p> <!--what happens if you hold Shift?--> |
   | Metric | An arrow that connects 2 existing nodes | The node displays between the two existing nodes where it was dropped and is connected to both existing nodes. <p>See [Connect nodes](#connect-nodes) for more information.</p> |
   | Dimension | Blank area of the canvas | 3 nodes are created for the top 3 dimension items. The nodes display where the component was dropped, unconnected with any existing nodes.<p>Hold the Shift key when you drop the dimension onto the canvas to add it as a single node with 3 dimension items.</p> |
   | Dimension | An existing node | A breakdown is automatically applied to the node with the top 5 dimension items displayed.<!--what happens if you hold Shift?--> |
   | Dimension | An arrow that connects 2 existing nodes | Three nodes are created for the top 3 dimension items. The nodes display between the two existing nodes where they were dropped and  node is connected to both existing nodes.<p>Hold the Shift key when you drop the dimension onto the canvas to add it as a single node with 3 dimension items.</p><p>See [Connect nodes](#connect-nodes) for more information.</p> |
   | Dimension item | Blank area of the canvas | The node displays where the component was dropped, unconnected with any existing nodes. |
   | Dimension item | An existing node | A breakdown is automatically applied to the node.<!--what happens if you hold Shift?--> |
   | Dimension item | An arrow that connects 2 existing nodes | The node displays between the two existing nodes where it was dropped and is connected to both existing nodes. <p>See [Connect nodes](#connect-nodes) for more information.</p> |
   | Multiple components | A blank area of the canvas | The nodes display where the components were dropped, unconnected with any existing nodes.<p>Hold the Shift key when you drop the components onto the canvas to add them as one combined node if they are the same component type.</p><p>See [Combine nodes](#combine-nodes) for more information.</p> |
   | Multiple components | An existing node | N/A <!--???--> |
   | Multiple components | An arrow that connects 2 existing nodes | The nodes display between the two existing nodes where they were dropped and each node is connected to both existing nodes. <p>See [Connect nodes](#connect-nodes) for more information.</p><p>Hold the Shift key when you drop the components onto the canvas to add them as one combined node if they are the same component type.</p><p>See [Combine nodes](#combine-nodes) for more information.</p> |

   Nodes display as a rectangular box with the following information:

   * Component name

   * The component type (such as metric or dimension)

   * Primary metric statistics (total and percent)

   * Secondary metric statistics (total and percent) 

1. Repeat this process to continue adding nodes to build out your journey. 

1. Continue customizing the journey as described in the sections below. You can connect nodes, rename nodes, apply breakdowns, publish audiences, add time constraints, and more. 

### Add the top nodes based on existing nodes

You can automatically add the top nodes based on the nodes that are already on the canvas. 

The option to add the top nodes is available when selecting the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The line between nodes

#### Add the top next or previous nodes

To add the top 3 nodes before or after one or more existing nodes:

<!-- Previous should add top 3 previous nodes as various branch nodes before the node (only allowed on nodes with nothing coming into it); After should add top 3 next nodes as various branch nodes after the node (only allowed on nodes with nothing going out of it)
 -->

#### Add the top nodes between existing nodes

To add the top 3 nodes between 2 existing nodes:

### Change the color of a node or line between nodes

The option to change the color is available when selecting the following objects on the canvas:

* Individual nodes

* The line between nodes

### Rename one or more nodes

The option to rename is available when selecting the following objects on the canvas:

* Individual nodes

* Multiple nodes

### Apply a breakdown

The option to apply a breakdown is available when selecting the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The line between nodes

### Publish an audience

The option to apply a breakdown is available when selecting the following objects on the canvas:

* Individual nodes

* Multiple nodes

* Multiple lines between nodes

### Trend a node (what does this mean? What does the Trend option do?)

The option to trend is available when selecting the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The line between nodes

* Multiple lines between nodes

### Duplicate nodes

The option to duplicate is available when selecting the following objects on the canvas:

* Multiple nodes

### Create a segment 

The option to create a segment is available when selecting the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The line between nodes

* Multiple lines between nodes

### Create an audience

(Works only when selecting between two nodes? Is this different than publishing an audience (which you can do when selecting one or more nodes?))

The option to create an audience is available when selecting the following objects on the canvas:

* The line between nodes

### Rearrange nodes

Journeys in Journey canvas consist of a flexible graph of nodes and arrows representing any combination of events, dimension items, and filters. 

You can drag nodes on the canvas to rearrange the events and conditions of the journey. As you do, data updates accordingly. 

### Combine nodes

The option to trend is available when selecting the following objects on the canvas:

* Multiple nodes

The logic that is applied to nodes when they are combined differs depending on the component types you are combining, as follows:

* When you combine multiple filters, they are joined with AND.

* When you combine multiple dimension items or metrics, they are joined with OR.

Do either of the following to combine nodes in Journey canvas:

* Drag a node onto another node.

* Select the nodes that you want to combine, right-click one of the selected nodes, then select **Combine**.<!--Is there a limit on how many you can combine? -->

### Connect nodes

You can connect nodes that are already on the canvas, or you can connect a node when adding it to the canvas.

#### Connect existing nodes

The connection between nodes in Journey canvas determines the sequence of events in the journey. 

To connect nodes in Journey canvas:

1. On the canvas, select either of the 2 nodes that you want to connect. 

   4 blue dots appear on each side of the selected node.

1. Drag any of the 4 blue dots to any of the 4 sides of the node that you want to connect to. 

#### Connect a node when adding it

When adding a node to the canvas, you can connect it to an existing node. For more information, see [Add a node](#add-a-node).

### Add a time constraint between nodes

The option to add a time constraint is available when selecting the following objects on the canvas:

* The line between nodes

You can set a time constraint between nodes. If a user follows the defined journey but takes longer than the allotted time period to move between the nodes, they are considered to have fallen out of the journey.

Right-click the edge, then select [!UICONTROL **Add time constraint**].

...

<!-- from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon).  -->

### Delete a node

The option to delete is available when selecting the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The line between nodes

* Multiple lines between nodes

<!-- Delete this after I decide I don't want to do it this way. Will probably use sections like I hav above.

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

   -->


## Open a journey from Journey Optimizer


In Journey Optimizer, open the journey that you want to analyze in Journey canvas.

1. Select [!UICONTROL **Analyze in CJA**]. <!-- ?? -->

