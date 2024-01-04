---
description: Learn how to use the flow visualization in a Workspace project.
title: How to configure a flow visualization
feature: Visualizations
exl-id: 7055cbc9-19b3-40f0-b8d4-52d241224827
role: User
---
# Configure a flow visualization

Flow visualizations help you understand the journey stemming from or leading up to a specific conversion event on your website or your app. It traces a path through your dimensions (and dimension items) or metrics. 

Flow visualizations let you configure the start or end of the path you are interested in, or analyze all paths that flow through a dimension or dimension item.

![The Flow configuration screen showing the Starts with, Contains, and Ends with fields.](assets/new-flow.png)

## Create a flow visualization {#configure}

1. Add a blank panel to your project, select the Visualizations icon in the left rail, then drag the [!UICONTROL **Flow**] visualization into the panel.

   Or

   Add a visualization in any of the ways described in the "Add visualizations to a panel" section in [Visualizations overview](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

1. Anchor your Flow visualization using one of the following options:

   * [!UICONTROL **Starts with**] (metrics, dimensions, or items), or
   * [!UICONTROL **Contains**] (dimensions, or items), or
   * [!UICONTROL **Ends with**] (metrics, dimensions, or items)

   Each of these categories is shown onscreen as a "drop zone." You can populate the drop zone in 3 ways:

   * Use the drop-down menu to select metrics or dimensions.
   * Drag dimensions or metrics from the left rail.
   * Begin typing the name of a dimension or metric, then select it when it appears in the drop-down list.

   >[!IMPORTANT]
   >
   >Calculated metrics cannot be used in the  **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** fields.

1. If you choose a metric, you also need to provide a [!UICONTROL **Pathing Dimension**] to use as your path leading to or going from your selected component, as shown here. The default is [!UICONTROL **Page**].

   ![The Pathing dimension.](assets/pathing-dim.png) 

1. (Optional) Select **[!UICONTROL Show advanced settings]** to configure any of the following options:

   ![Advanced settings with Disiplay options, Number of columns and Flow container.](assets/adv-settings.png)

   | Setting | Description |
   | --- | --- |
   | **[!UICONTROL Wrap labels]** | Normally, the labels on the Flow elements are truncated to save screen real estate, but you can make the entire label visible by checking this box.  Default = unchecked. |
   | **[!UICONTROL Include repeat instances]** | Flow visualizations are based on instances of a dimension. This setting gives you the option to include or exclude repeated instances, e.g. Page reloads. However, repeats cannot be removed from Flow visualizations that include multi-valued dimensions, such as listVars, listProps, s.product, merchandising eVars, etc. <p>This option is disabled by default.</p> |
   | **[!UICONTROL Limit to first/last occurrence]** | Limit paths to those that start/end with the first/last occurrence of a dimension/item/metric. See the section below, [Example scenario for 'limit to first/last occurrence'](#example-scenario-for-limit-to-firstlast-occurrence), for a more detailed explanation. |
   | **[!UICONTROL Number of columns]** | The number of columns you want in your Flow diagram. You can specify a maximum of 5 columns. |
   | **[!UICONTROL Items expanded per column]** | The number of items you want in each column. You can specify a maximum of 10 items expanded per column. |
   | **[!UICONTROL Flow container]** | <ul><li>Visit</li><li>Visitor</li></ul> Lets you switch between Visit and Visitor to analyze visitor pathing. These settings help you understand visitor engagement at the visitor level (across visits), or constrain the analysis to a single visit.  |

   >[!IMPORTANT]
   >
   >The combination of **[!UICONTROL Number of columns]** and **[!UICONTROL Items expanded per column]** determine the number of underlying requests required to create the flow visualization. The higher those numbers, the longer it takes to render a visualization.


1. Select **[!UICONTROL Build]**.

>[!INFO]
>
>**Example:** Suppose that you want to trace the path that users took both to and from the most popular pages on your site.
>
>To do this, you would
>
>1. Begin creating a flow visualization as described above.
>1. Drag the [!UICONTROL **Page**] dimension into the **[!UICONTROL Contains]** field, then select [!UICONTROL **Build**].
>1. The Flow visualization builds with the most-viewed page visible in the focus node in the center of the visualization. You also see the top pages leading into that page (to the left of the focus node) as well as the top pages leading out of that focus page (to the right of the focus node).
>1. Analyze data in the flow, as described in [View and change the Flow output](#view-and-change-the-flow-output).

## View and change the Flow output {#output}

![Flow output example showing Ends with Visits, Pathing dimension: Page, and Flow container: Vistors.](assets/flow-output.png)

A summary of the Flow configuration appears at the top of the diagram. The paths in the diagram are proportional. Paths with more activity appear thicker. 

To drill down further into the data, you have several options:

* The flow diagram is interactive. Mouse over the diagram to change the details that are shown.

* When you click on a node in the diagram, the details for that node appear. Click on the node again to collapse it.

   ![Example interactive flow diagram showing node-details.](assets/node-details.png)

* You can filter a column to display only certain results, such as including and excluding, specifying criteria, etc.

* Click the plus sign (+) on the left to expand a column.

* Use the right-click options explained below to further customize the output.

* Click the pencil icon next to the configuration summary to further edit the flow or rebuild it with different options.

* You can also export and further analyze your Flow diagram as part of a project's .CSV file by going to **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**.

## Filtering

Above each column, a filter appears when you hover over it. By clicking the filter, you get the same filter dialog that exists in the Freeform table today. This filter works the same as it does in the Freeform table.

* Use advanced settings to include or exclude certain criteria with our list of operators. 
* Once you have filtered an item from the list, that specific column will reflect the filtering. (The filter either reduces it to only show the item allowed in the filter, or it removes all items except for the one item you want in the filter.
* All downstream and upstream columns should persist, as long as there is data flowing into the remaining nodes. 
* Once applied, the filter icon appears in blue above the column it is filtering. 
* To remove a filter, click on the filter icon to open the filter menu. Remove any filters applied and then click **[!UICONTROL Save]**. The flow should return to its previous, unfiltered state.

## Right-click options {#right-click}

| Option | Description |
|--- |--- |
| [!UICONTROL Focus on this node] | Change the focus to the selected node. The focus node appears at the center of the Flow diagram. |
| [!UICONTROL Start over] | Returns you to the Freeform diagram builder, where you can build a new Flow diagram. |
| [!UICONTROL Create filter for this path] | Create a filter. This takes you into the Filter Builder, where you can configure the new filter. |
| [!UICONTROL Breakdown] | Break the node down by available Dimensions, Metrics, or Time. |
| [!UICONTROL Filter column] | The same filter options appear as are available in the Freeform table. For more information about the available options, see the section "Apply a simple or advanced filter to a table" in [Filter and sort tables](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md).|
| [!UICONTROL Exclude item]/[!UICONTROL Restore excluded items] | Removes a specific node from the column and automatically creates it as a filter at the top of the column. To restore the excluded item, right-click again and select **[!UICONTROL Restore Excluded Item]**. you can also open the filter at the top of the column and remove the pillbox with the item you just excluded. |
| [!UICONTROL Trend] | Create a trended diagram for the node. |
| Show next column / Show previous column | Reveals the next (right) or previous (left) column of the visualization. |
| Hide column | Hides the selected column from the visualization. | 
| [!UICONTROL Expand entire column] | Expand a column to show all nodes. By default, only the top five nodes display. |
| Create audience from selection | Creates an audience based on the column that is selected. |
| [!UICONTROL Collapse entire column] | Hide all nodes in a column. |

## Example scenario for 'limit to first/last occurrence'

When using this option, keep in mind that:

* **[!UICONTROL Limit to first/last occurrence]** counts only the first/last occurrence in the series. All other occurrences of the **[!UICONTROL Starts with]** or **[!UICONTROL Ends with]** criteria are discarded. 
* If used with a **[!UICONTROL Starts with]** flow, only the first occurrence that matches the start criteria is included. 
* If used with an **[!UICONTROL Ends with]** flow, only the last occurrence that matches the end criteria will be included. 
* The series used differs based on the container. If using the **[!UICONTROL Visit]** container, the series of events will be the session. If using the **[!UICONTROL Visitor]** container, the series of events will be all the events for a given user in the provided date range. 
* The **[!UICONTROL Limit to first/last occurrence]** option can be configured in the advanced settings when using a Metric or Dimension Item in the "Starts with" or "Ends with" fields.
 
Example series of events:

Home > Products > Add to cart > Products > Add to Cart > Billing > Order Confirmation
 
### Consider a flow analysis using the following settings:

* Start with[!UICONTROL  Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container
 
If "Limit to first/last occurrence" is disabled, then this single series of events would count 2 occurrences of "Add to Cart".
Expected Flow Output:
"Add to Cart" (2) —> "Products" (1)
                  -> "Billing" (1)
 
However, if "Limit to first/last occurrence" is enabled, only the first occurrence of "Add to cart" would be included in the analysis.
Expected Flow Output:
"Add to Cart" (1) —> "Products" (1)
 
### Consider the same series of events but using the following settings:

* Ends with [!UICONTROL Add to cart] (Dimension Item)
* [!UICONTROL Page] pathing dimension
* [!UICONTROL Visit] container
 
If **[!UICONTROL Limit to first/last occurrence]** is *disabled*, then this single series of events would count 2 occurrences of "Add to Cart".
Expected Flow Output:
"Products" (2) <— "Add to cart" (2)
 
However, if **[!UICONTROL Limit to first/last occurrence]** is *enabled*, only the last occurrence of [!UICONTROL Add to cart] would be included in the analysis.
Expected Flow Output:
"Products" (1) <— "Add to cart" (1)
