---
description: Configure a Journey canvas visualization
title: Journey canvas
feature: Visualizations
role: User
hide: yes
hidefromtoc: yes
exl-id: 53984934-6fba-4f15-aeeb-d91039260553
---
# Configure a Journey canvas visualization

{{release-limited-testing}}

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
   | [!UICONTROL **Primary metric**] | The primary metric affects the following aspects of the Journey canvas visualization:  <ul><li>Defines how people move through the journey.</li><li>The total number shown on each node.<p>For example, if People is the primary metric, each node shows the number of people who reached that node in the journey.</p></li><li>The percentage shown on each node. (After the visualization is built, you can choose to show either the percentage of the total or of the starting node.)</li><p>For example, if People is the primary metric, each node shows the percentage of people who reached that node in the journey (either the percentage of the total or of the starting node).</p></li><li>When a dimension is added to the visualization, the top 3 nodes of the visualization are added, based on the primary metric.</li></ul>  | 
   | [!UICONTROL **Secondary metric**] | The secondary metric is optional. When one is selected, the following information is shown on each node below the primary metric: <ul><li>The total number<p>For example, if Sessions is the secondary metric, each node shows the number of sessions that reached that node in the journey.</p></li><li>The percentage (After the visualization is built, you can choose to show either the percentage of the total or of the starting node.)</li><p>For example, if Sessions is the secondary metric, each node shows the percentage of sessions that reached that node in the journey (either the percentage of the total or of the starting node).</p></li></ul> |
   | [!UICONTROL **Journey Optimizer journey**]<!-- name? --> |  Select the Journey Optimizer journey that you want to use as the basis for your analysis in Journey canvas. (Alternatively, you can leave this option blank if you want a blank canvas from which to build your analysis within Analysis Workspace.)</p> <p>When you analyze a Journey Optimizer journey in Journey canvas, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer. For more information, see [Analyze Journey Optimizer journeys](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#analyze-journey-optimizer-journeys) in [Journey canvas overview](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md).</p><p>**Note**: This option displays only when Journey Optimizer data is detected in the data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</p> |

1. (Optional) Select [!UICONTROL **Show advanced settings**], then specify the following information:

   | Field | Function | 
   |---------|----------|
   | [!UICONTROL **Journey canvas container**] | Choose the container that you want to focus on throughout the journey. The container that you choose determines the statistics that are displayed in the visualization. (If your container names differ from the default names shown below, they were customized in your data view.)<ul><li>**Sessions:** Constrains the statistics of the visualization to fall within a single defined session for a given person. This means that the numbers and percentages that appear on each node (that are based on the primary and secondary metrics) must occur within a single session for each person.</li><li>**People:** Allows the statistics of the visualization to span multiple sessions for a given person. This means that the numbers and percentages that appear on each node (that are based on the primary and secondary metrics) can occur across any number of sessions, as long as the sessions belong to the same person. This is the default setting.</li></ul> | 

1. Select [!UICONTROL **Build**].

   If you have Journey Optimizer and you selected a Journey Optimizer journey, the journey is displayed with the same order, sequence, and structure as it has in Journey Optimizer. 

   <!-- add screen shot -->

   If you do not have Journey Optimizer or if you didn't select a Journey Optimizer journey, a blank canvas displays where you can begin populating the journey.

   <!-- add screen shot -->

1. Whether you are creating a new analysis from a blank canvas or you are are analyzing a Journey Optimizer journey, you can configure the journey as described in [Configure a Journey canvas visualization](#begin-building-a-journey-canvas-visualization). 


## Configure a Journey canvas visualization

You need to [begin building a Journey canvas visualization](#begin-building-a-journey-canvas-visualization) before you can configure it as described in the following sections. 

### Configure settings

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Configure any of the following settings that are displayed across the top of the visualization:

   | Setting | Function | 
   |---------|----------|
   | [!UICONTROL **Node type**] | Allows you to configure which node types are shown in the visualization. To hide a node type from the visualization, select the (x) next to the node type, or deselect it from the drop-down menu. To show a hidden node type, select it from the drop-down menu. <p>Depending on the contents of your visualization, possible node types include:</p><ul><li>[!UICONTROL **Read segment**]</li><li>[!UICONTROL **End**]</li><li>[!UICONTROL **Dimension**]</li><li>[!UICONTROL **Metric**]</li></ul><p>**Note**: Consider the following when using this field:</p><ul><li>This option displays only when Journey Optimizer data is detected in the data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</li><li>After you modify a Journey Optimizer journey in Journey Canvas, this option is no longer available. For more information, see [Visual differences after modifying a journey in Journey canvas](/help/analysis-workspace/visualizations/journey-canvas/journey-canvas.md#visual-differences-after-modifying-a-journey-in-journey-canvas)</li></ul></p>   | 
   | [!UICONTROL **Percentage value**] | Choose from the following options: <ul><li>[!UICONTROL **Percent of total**]: The percent of all of the people included in the data view within the panel's date range.</li><li>[!UICONTROL **Percent of start node**]: The percent of all the people included in the data view within the panel's date range who also meet the criteria of the journey's starting node. (This option is available only in journeys with a single start node; it is disabled in journeys with multiple start nodes. A start node is defined as any node that doesn't have a connection coming into it.)</li></ul> | 
   | [!UICONTROL **Arrow settings**] | Choose from the following options:<ul><li>[!UICONTROL **None**]: </li><li>[!UICONTROL **Condition**]: </li><li>[!UICONTROL **All labels**]: </li></ul><p>**Note**: This option displays only when Journey Optimizer data is detected in the data view that is selected in the Analysis Workspace panel where you are adding the visualization. For information about changing the data view on a panel in Analysis Workspace, see [Analysis Workspace overview](/help/analysis-workspace/home.md).</p>  |
   | [!UICONTROL **Show fallout**] | Display fallout data for each node. This shows the number and percentage of people who left the journey at a given node. <p>People who fell out of the journey might have performed other actions on the site, but they never met the criteria defined by the next node in the journey.</p> |

1. Continue with [Add a node](#add-a-node). 

### Add a node

Nodes in a Journey canvas visualization represent the events or actions of a user journey. You create nodes by dragging Workspace components from the left rail to the canvas.

To add a node to a Journey canvas visualization:

1. In Analysis Workspace, open an existing Journey canvas visualization, or [begin building a new one](#begin-building-a-journey-canvas-visualization).

1. Drag metrics, dimensions, dimension items, filters, or date ranges from the left rail onto the canvas. Metrics that are based on a [derived field](/help/data-views/derived-fields/derived-fields.md) are supported. However, calculated metrics, as well as any metrics or dimensions that are based on a [summary dataset](/help/data-views/summary-data.md) are not supported.
     
   You can select multiple components in the left rail by holding Shift, or by holding Command (on Mac) or Ctrl (on Windows).

   The visualization is updated as follows, depending on the component type and the area of the canvas where you place it: 
   
   |  Component type | Placement of component | Visualization updates after node is added | 
   |---------|----------|----------|
   | Metric | Blank area of the canvas | The node displays where the component was dropped, unconnected with any existing nodes. | 
   | Metric | An existing node | The component is automatically combined with the existing node. (See [Combine nodes](#combine-nodes) for more information.)</p> |
   | Metric | An arrow between 2 existing nodes | The node displays between the two existing nodes where the component was dropped and is connected to both existing nodes. (See [Connect nodes](#connect-nodes) for more information.)</p> |
   | Dimension | Blank area of the canvas | 3 nodes are created for the top 3 dimension items where the component was dropped, unconnected with any existing nodes. (**Note:** If only 1 or 2 nodes display, it means that data is available for only 1 or 2 of the dimension items. If no nodes display, it means that data is not available for any of the dimension items. In this case, try adding it to a different point of the journey, adjust the visualization's date range, or choose a different dimension.)<p>Hold the Shift key when you drop the dimension onto the canvas to add it as a single node with 3 dimension items.</p><p></p> |
   | Dimension | An existing node | A breakdown is automatically applied to the node with the top 5 dimension items displayed.<!--what happens if you hold Shift?--> |
   | Dimension | An arrow that connects 2 existing nodes | 3 nodes are created for the top 3 dimension items that follow the first event after the first node (of people/sessions who eventually reach the second node). The nodes display between the two existing nodes where the component was dropped and each node is connected to both existing nodes. (**Note:** If only 1 or 2 nodes display, it means that data is available for only 1 or 2 of the dimension items. If no nodes display, it means that data is not available for any of the dimension items. In this case, try adding it to a different point of the journey, adjust the visualization's date range, or choose a different dimension.)<p>Hold the Shift key when you drop the dimension onto the canvas to add it as a single node with 3 dimension items. (See [Connect nodes](#connect-nodes) for more information.)</p> |
   | Dimension item | Blank area of the canvas | The node displays where the component was dropped, unconnected with any existing nodes. |
   | Dimension item | An existing node | The component is automatically combined with the existing node. |
   | Dimension item | An arrow that connects 2 existing nodes | The node displays between the two existing nodes where the component was dropped and is connected to both existing nodes. (See [Connect nodes](#connect-nodes) for more information.)</p> |
   | Filter | Blank area of the canvas  | The node displays where the component was dropped unconnected with any other nodes.<p>The number and percentage that appear on the node include the total of the primary metric, filtered by the filter you selected.</p> <p>For example, if People is selected as the primary metric for the journey, then adding a filter of Today to a blank area of the canvas shows all of the people who had an event today.</p> |
   | Filter | An existing node | Applies the filter to the existing node. |
   | Filter | An arrow that connects 2 nodes | The node displays between the two existing nodes where the component was dropped and is connected to both existing nodes. (See [Connect nodes](#connect-nodes) for more information.)</p><p>Applies the filter to the point on the path where the component was dropped.</p> |
   | Date range | Blank area of the canvas | The node displays where the component was dropped, unconnected with any other nodes.<p>The number and percentage that appear on the node include the total of the primary metric, filtered by the date range you selected.</p> <p>For example, if People is selected as the primary metric for the journey, then adding a date range of This month to a blank area of the canvas shows all of the people who had an event during the current month.</p> |
   | Date range | An existing node | Applies the date range to the existing node. |
   | Date range | An arrow that connects 2 nodes | The node displays between the two existing nodes where the component was dropped and is connected to both existing nodes. (See [Connect nodes](#connect-nodes) for more information.)</p><p>Applies the date range to the point on the path where the component was dropped.</p> |
   | Multiple components | A blank area of the canvas | **If none of the components are dimensions:**<p>Each component displays as a separate node where the components were dropped, unconnected with any existing nodes.</p><p>Hold the Shift key when you drop the components onto the canvas to add them as one combined node. </p><p>**If any of the components you are adding are dimensions:**</p><p>Each component displays as a separate node where the components were dropped, unconnected with any existing nodes.</p><p>Only one dimension can be added at a time, and 3 nodes are created for the top 3 dimension items where the component was dropped.</p><p>Hold the Shift key when you drop the components onto the canvas to add them as one combined node. The top 3 dimension items are combined with each node. (See [Combine nodes](#combine-nodes) for more information.)</p> |
   | Multiple components | An existing node | All components are combined with the existing node.<p>If any of the components you are adding are dimensions, then the top 3 dimension items are combined with the node.</p> <p>Only one dimension can be added at a time.</p> |
   | Multiple components | An arrow that connects 2 existing nodes | **If none of the components are dimensions:**<p>Each component displays as a separate node where the components were dropped and each node is connected to both existing nodes. (See [Connect nodes](#connect-nodes) for more information.)</p><p>Hold the Shift key when you drop the components onto the canvas to add them as one combined node. (Components must be of the same type to be combined into a single node.) (See [Combine nodes](#combine-nodes) for more information.)</p><p>**If any of the components you are adding are dimensions:**</p><p>Each component displays as a separate node where the components were dropped and each node is connected to both existing nodes.</p><p>Only one dimension can be added at a time, and 3 nodes are created for the dimension's top 3 items that follow the first event after the first node (of people/sessions who eventually reach the second node). Each node is connected to both existing nodes. (See [Connect nodes](#connect-nodes) for more information.)</p><p>Hold the Shift key when you drop the components onto the canvas to add them as one combined node. The top 3 dimension items are combined with each node, and each node is connected to both existing nodes. (See [Combine nodes](#combine-nodes) for more information.)</p>|

   Nodes display as a rectangular box with the following information:

   * Component name

   * The component type (such as metric or dimension)

   * Primary metric statistics (total and percent)

   * Secondary metric statistics (total and percent) 

1. Repeat this process to continue adding nodes to build out your journey. 

1. Continue customizing the journey as described in the sections below. You can connect nodes, rename nodes, apply breakdowns, create audiences, add time constraints, and more. 

### Add the top nodes based on existing nodes

You can automatically add the top nodes based on the nodes that are already on the canvas. 

This option is available for the following objects on the canvas:

* Individual nodes 

* The arrow between nodes

#### Add top nodes after an existing node

You can select a node and add the top 3 nodes that come after it in the journey.

1. Right-click the node where you want to add the top 3 nodes that come after it in the journey.

   This node cannot have any existing nodes going out of it in the journey.

1. Select [!UICONTROL **Add top nodes after this node**].

   The top 3 nodes that come after this node in the journey are added, and each are connected to the node you selected as a separate branch.

#### Add top nodes before an existing node

You can add the top 3 nodes that come before an existing node in the journey.

1. Right-click the node where you want to add the top 3 nodes that come before it in the journey.

   This node cannot have any existing nodes coming into it in the journey.

1. Select [!UICONTROL **Add top nodes before this node**].

   The top 3 nodes that come before this node in the journey are added, and each are connected to the node you selected as a separate branch.

#### Add top nodes between existing nodes

You can add the top 3 nodes that come between 2 existing nodes:

1. Right-click the arrow between the 2 nodes where you want to add the top 3 nodes in the journey.

1. Select [!UICONTROL **Add top nodes**].<!-- I don't think this should have the word "next" in the UI option, because it's both next and previous. It's in between. Just "Get top nodes" sounds better to me.-->

   The top 3 nodes are added between the 2 existing nodes, and each are connected as a separate branch. 

### Rearrange nodes

Journeys in Journey canvas consist of a flexible graph of nodes and arrows representing any combination of events, dimension items, and filters. 

You can drag nodes on the canvas to rearrange the events and conditions of the journey. As you do, data updates accordingly. 

### Combine nodes

A combined node in Journey canvas is a single point in the user journey (node) that contains 2 or more components that are joined together through logic. 

#### Create combined nodes

You can do any of the following to create a combined nodes in Journey canvas:

* From the left rail, drag a single component onto a node on the canvas.

* From the left rail, drag multiple components simultaneously onto a node on the canvas.

* From the left rail, drag multiple components simultaneously onto a blank area of the canvas while holding the Shift key.

* On the canvas, select the nodes that you want to combine, right-click one of the selected nodes, then select **Combine**.<!--Is there a limit on how many you can combine? -->

#### Logic when combining nodes

The logic that is applied to nodes when they are combined differs depending on which component types you are combining, as follows:

>[!TIP]
>
>You can view the logic of a combined node by right-clicking the node, then selecting [!UICONTROL **Create filter from node**]. The logic is shown in the [!UICONTROL **Definition**] section.


| Component types to combine | Logic (operator) used |
|---------|----------|
| Metric + Metric | Joined with OR | 
| Dimension + Dimension | Joined with OR |
| Filter + Filter | Joined with AND | 
| Dimension + Metric, Date range, or Filter | Joined with AND | 
| Date range + Metric, Filter, or Dimension | Joined with AND | 
| Filter + Metric, Date range, or Dimension | Joined with AND | 

### Connect nodes

You can connect nodes that are already on the canvas, or you can connect a node when adding it to the canvas.

#### Arrows between nodes

Nodes are connected by an arrow. Both the arrow direction and width have significance:

* **Direction**: Indicates the sequence of events of the journey

* **Width**: Indicates percentage volume from one node to another

#### Logic when connecting nodes

When you connect nodes in Journey canvas, they are connected using the THEN operator. This is also known as [sequential filtering](/help/components/filters/seg-sequential-build.md). 

Nodes are connected as an "eventual path," which means that visitors are counted as long as they eventually move from one node to the other, regardless of any events occurring between the 2 nodes.

You can view the logic of connected nodes by right-clicking the node, then selecting [!UICONTROL **Create filter from node**]. The logic is shown in the [!UICONTROL **Definition**] section.

#### Connect existing nodes

Journeys cannot be circular, looping back to previously connected nodes.

To connect nodes in Journey canvas:

1. On the canvas, hover over the node that comes first in the journey sequence that you want to connect to another node. 

   4 blue dots appear on each side of the selected node.

1. Drag any of the 4 blue dots to any of the 4 sides of the node that you want to connect to.

   An arrow appears, connecting the 2 nodes. See [Arrows between nodes](#arrows-between-nodes) for more information.

#### Connect nodes when adding a node

When adding a node to the canvas, you can place it between two connected nodes. The node is added to the journey's flow between the 2 existing nodes. 

For more information, see [Add a node](#add-a-node).

### Change the color of a node or arrow

You can visually customize a journey by changing the color of any node or arrow on the canvas. For example, you could adjust a colors to indicate a desirable or undesirable event.

The option to change the color is available for the following objects on the canvas:

* Individual nodes

* The arrow between nodes

To change the color of a node or arrow:

1. Right-click the node or arrow whose color you want to change.

1. Select [!UICONTROL **Change color**]. <!--make sure "color" isn't capitalized. It is in the req doc-->

1. Select the desired color. 

   The following colors are available: <!--look into this interaction and color list-->

### Rename a node or arrow

When you drag a component to a Journey canvas visualization, it creates a node with the same name as the component name. You can rename the node to better match the step of the journey that the node represents.

The option to rename is available for the following objects on the canvas:

* Individual nodes

* The arrow between nodes 

To rename a node:

1. Right-click the node that you want to rename.

1. Select [!UICONTROL **Rename**]. 

1. Specify a new name, then press Enter.<!--is that right?-->

### Apply a breakdown

The option to apply a breakdown to your data is available for the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The arrow between nodes

* Multiple arrows between nodes

### Apply a breakdown to one or more nodes or arrows

1. Select one or more nodes where you want to apply a breakdown, then right-click one of the selected nodes.

   Or

   Select one or more arrows between 2 nodes where you want to apply the breakdown, then right-click one of the selected arrows.

1. Select [!UICONTROL **Breakdown**].

### Apply a breakdown to an individual node

You can drag a dimension from the left rail onto the node on the canvas where you want to apply the breakdown. 

For more information, see [Add a node](#add-a-node).

### Create an audience

The option to create an audience is available for the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The arrow between nodes

* Multiple arrows between nodes 

To create an audience:

1. Select one or more nodes where you want to create an audience, then right-click one of the selected nodes.

   Or

   Select one or more arrows between 2 nodes where you want to create an audience, then right-click one of the selected arrows.

1. Select [!UICONTROL **Create audience**].

1. Continue creating and publishing the audience as described in [Create and publish audiences](/help/components/audiences/publish.md).

### View trend data

You can view the trend data in a line graph for objects in Journey canvas. <!--, with some prebuilt anomaly detection data (this is the definition in Fallout) -->

The option to trend is available for the following objects on the canvas:

* Individual nodes

* Multiple nodes

* The arrows between nodes

* Multiple arrows between nodes

To view trend data:

1. Select one or more nodes for which you want to view trend data, then right-click one of the selected nodes.

   Or

   Select one or more arrows between 2 nodes for which you want to view trend data, then right-click one of the selected arrows.

1. Select [!UICONTROL **Trend**].

### Duplicate nodes

The option to duplicate is available for the following objects on the canvas:

* Multiple nodes

To duplicate nodes:

1. Select multiple nodes that you want to duplicate.

1. Right-click one of the selected nodes, then select [!UICONTROL **Duplicate**].


### Add a time constraint between nodes

You can set a time constraint between nodes. When a time constraint is in place, if a person follows the defined journey but takes longer than the allotted time period to move between the nodes, they are considered to have fallen out of the journey.

The option to add a time constraint is available for the following objects on the canvas:

* The arrow between nodes

To add a time constraint:

1. Right-click the the arrow between 2 nodes, then select [!UICONTROL **Add time constraint**].

<!-- 

from Travis: You can set time to be within X amount of time or after X amount of time (those are the only two options I think, but we can check with Brandon). 
1. Choose from the following options: 

--> 

### Create a filter based on a node or arrow

You can create a new filter based on a node or arrow within a journey. After the filter is created, you can use it anywhere in Analysis Workspace. 

Filters created from Journey canvas use [sequential filtering](/help/components/filters/seg-sequential-build.md). This means that the filter uses the THEN operator to link together the sequence of events (i.e., the journey) that people flowed through, leading up to the selected node or arrow. All events that match the selected node or arrow are included in the filter.

If you create a filter based on a node that has multiple paths flowing into it, all paths are included in the filter. Separate paths are joined with the OR operator.

To create a filter:

1. On the canvas, right-click the node or arrow that you want to use to create the filter.

1. Select [!UICONTROL **Create filter from node**] or [!UICONTROL **Create filter from arrow**].

   The Filter builder displays. In the [!UICONTROL **Definition**] section, the filter definition is created based on the node or arrow you selected and its context within the journey. 

1. Specify a title for the filter and make any other changes. For more information about creating a filter, see [Filter builder](/help/components/filters/filter-builder.md).

1. Select [!UICONTROL **Save**] to save the filter.

### Delete nodes

You can delete one or more nodes at a time within a journey. When you delete a node that is connected between 2 nodes within the journey, the 2 remaining nodes become directly connected.

To delete nodes in Journey canvas:

1. Select one or more nodes that you want to delete, then right-click one of the selected nodes.

1. Select [!UICONTROL **Delete**].

### Delete arrows between nodes

You can delete one or more arrows at a time within a journey. When you delete an arrow between 2 nodes, the nodes are no longer connected. If the arrow was part of a longer path, the path is disconnected.

To delete arrows between nodes in Journey canvas:

1. Select one or more arrows between 2 nodes that you want to delete, then right-click one of the selected arrows.

1. Select [!UICONTROL **Delete**].


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
