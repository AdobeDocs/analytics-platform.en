---
description: Use the map visualization to plot data on a geographic map visualization.
title: Map
feature: Visualizations
role: User, Admin
exl-id: 6656b34a-ae1e-4f9f-9c6d-13c54e49625c
---
# Map {#map}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_button"
>title="Map"
>abstract="This visualization represents metrics by overlaying them on a map. This is useful for identifying data across different geographic regions."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_bubbles"
>title="Bubbles"
>abstract="Plot events using bubbles."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_heatmap"
>title="Heatmap"
>abstract="Plot events using a heat map."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_This article documents the Map visualization in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._<br/>_See [Map](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/map-visualization) for the_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics** version of this article._

>[!ENDSHADEBOX]

The ![Globe](/help/assets/icons/Globe.svg) **[!UICONTROL Map]** visualization in Analysis Workspace allows you to build a visual map of any metric (including calculated metrics). It is useful for identifying and comparing metric data across different geographic regions.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Map visualization](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/visualizations/configure-and-use-the-map-visualization){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

## Prerequisites

### Add context labels in data views

In Customer Journey Analytics data views settings, administrators can add [context labels](/help/data-views/component-settings/overview.md) to a dimension or metric and Customer Journey Analytics services like the [!UICONTROL map] visualization can use these labels for their purposes. 

#### Required context labels for latitude and longitude in the map visualization

Context labels are required for the map visualization to function. Without the following context labels present, the map visualization does not work, because there is no latitude and longitude data to work with.

* [!UICONTROL Geo: Latitude]
* [!UICONTROL Geo: Longitude]

To add these context labels:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. On the Data views page, select the data view that contains data that you want to analyze in the map visualization.

1. Select the **[!UICONTROL Components]** tab.

1. (Conditional) If you are using the Web SDK and you have configured latitude and longitude to be populated in your data stream, or if you are using the Analytics Source Connector to populate event data, then latitude and longitude fields should already be available in your schema and populated with the correct context labels.

    Locate these **[!UICONTROL Latitude]** and **[!UICONTROL Longitude]** schema fields (in **[!UICONTROL Event datasets]** > **[!UICONTROL placeContext]** > **[!UICONTROL geo]** > **[!UICONTROL _schema]**) and drag them into your data view as dimensions if they aren't already present. 

   When these schema fields exist as dimensions in your data view, their context labels are automatically applied, and the map visualization uses them without any additional configuration.

   ![Add latitude and longitude schema fields to data view](assets/dataview-lat-long-default.png)

1. (Conditional) If you have custom dimensions that you want to use for latitude and longitude data, you can configure the context labels on the custom fields:

   1. In the **[!UICONTROL Dimensions]** section, select the dimension that contains the longitude data. 

   1. In the **[!UICONTROL Component settings]** section in the right rail, in the **[!UICONTROL Context labels]** field, begin typing `Longitude`, then select it from the drop-down menu.

      ![Latitude and longitude context labels](assets/map-context-labels-lat-long.png)

   1. Repeat this process to add the **[!UICONTROL Latitude]** context label to the dimension that contains the latitude data.

   1. (Optional) By default, these dimensions are precise to the town or zip code level in the map visualization, and they show 2 decimal places in Workspace reports. You can adjust them to be precise within a single meter in the map visualization and to show 5 decimal places in Workspace reports. For more information about how to adjust the precision level, see [Configure precise locations for dimensions](#configure-precise-locations-for-dimensions).

1. Select **[!UICONTROL Save and continue]** > **[!UICONTROL Save and finish]**.

#### Required context labels for geo templates

Adobe provides several [pre-built templates](/help/analysis-workspace/templates/use-templates.md#web-audience) that use the map visualization. To use each template, you must add the corresponding context label to a dimension in your data view.

Following are the templates and the required context label. Without these labels present, the templates do not work, because there is no geo data to work with.

| Template name | Required context label |
|---------|----------|
| Geo countries | [!UICONTROL Geo: Geo Country] |
| Geo regions | [!UICONTROL Geo: Geo Region] |
| Geo cities | [!UICONTROL Geo: Geo City] |
| Geo US states | [!UICONTROL Geo: Geo State] |
| Geo US DMA | [!UICONTROL Geo: Geo Dma] |

To add these context labels:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. On the Data views page, select the data view that contains data that you want to analyze with pre-built templates that use the map visualization. In this data view, pick five dimensions: one with the country data, one with the region data, one with the city data, one with the state data, and one with the DMA data. Then, label those dimensions with the corresponding context label.

1. Select the **[!UICONTROL Components]** tab.

1. (Conditional)  If you are using the Web SDK and you have configured geo fields to be populated in your data stream, or if you are using the Analytics Source Connector to populate event data, then geo fields should already be available in your schema and populated with the correct context labels.

   Locate the appropriate schema fields, such as **[!UICONTROL City]**, **[!UICONTROL Postal code]**, **[!UICONTROL State or province]** (in **[!UICONTROL Event datasets]** > **[!UICONTROL placeContext]** > **[!UICONTROL geo]**), then drag them into your data view as dimensions if they aren't already present. 

   When these schema fields exist as dimensions in your data view, their context labels are automatically applied, and the geo templates use them without any additional configuration.

   ![Add geo schema fields to data view](assets/dataview-geo-default.png)

1. (Conditional) If you have custom dimensions that you want to use for geo data, you can configure the context labels on the custom fields:

   1. Select the dimension that contains the country data. 

   1. In the **[!UICONTROL Component settings]** section in the right rail, in the **[!UICONTROL Context labels]** field, begin typing `Geo Country`, then select it from the drop-down menu.

      ![Templates context labels](assets/map-context-labels-templates.png)

   1. Repeat this process to add the **[!UICONTROL Geo: Geo Region]**, **[!UICONTROL Geo: Geo City]**, **[!UICONTROL Geo: Geo State]**, and **[!UICONTROL Geo: Dma]** context label to each dimension that contains the corresponding data.

1. Select **[!UICONTROL Save and continue]** > **[!UICONTROL Save and finish]**.

### Graphics drivers must support WebGL rendering

The map visualization uses WebGL for graphics display. If your graphics drivers do not support WebGL rendering, you might need to update your drivers.

## Map visualization in Customer Journey Analytics vs. Adobe Analytics

The map visualization in Customer Journey Analytics differs from the map visualization in Adobe Analytics in the following ways:

| Feature | Customer Journey Analytics | Adobe Analytics |
|---------|----------|---------|
| Data source | Use any segment available in your data view as your data source.  | Provides the following options: <ul><li>Mobile lat/long</li><li>Geographic Dimension<br/>Represents geo segmentation data about visitor location based on the visitor's IP address. </li></ul> |
| Precision | For datasets with deep precision, you can configure the dimensions in your data view to show up to 5 decimal places. This allows the map visualization to be accurate within a single meter. <p>For more information, see [Configure precise locations for dimensions](#configure-precise-locations-for-dimensions).</p> | Data is accurate to the [!UICONTROL Country], [!UICONTROL Region], and [!UICONTROL City] level. (It does not go to the DMA or Zip Code level.) |
| Create a segment from a selection | Create a segment based on a specific area that you select in the map visualization. <p>For more information, see [Create a segment from the map visualization](#create-a-segment-from-the-map-visualization).</p> | Create a segment based on the data that is being reported in the map visualization in general.|
| Create an audience from a selection | Create an audience based on a specific area that you select in the map visualization. <p>For more information, see [Create an audience from the map visualization](#create-an-audience-from-the-map-visualization). | Cannot create an audience from the map visualization. |
| Create a trend from a selection | Create a trended line chart visualization based on a specific area that you select in the map visualization. <p>For more information, see [Create a trended line chart from the map visualization](#create-a-trended-line-chart-from-the-map-visualization). <!-- is this correct? --> | Cannot create a trend from the map visualization. |
| Add a breakdown from a selection | Break down a specific dimension item, metric, segment, or date range within a specific area that you select in the map visualization. <p>For more information, see [Add a breakdown from the map visualization](#add-a-breakdown-from-the-map-visualization). | Cannot add a breakdown from the map visualization. |

## Build a map visualization {#begin-building-map}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_map_panel"
>title="Configure the map visualization"
>abstract="Choose the metric or calculated metric that is used as the basis for your map visualization. You can also add a segment if you want to focus on a specific subset of the data.<p>You can update this information any time after the visualization renders.</p>"

<!-- markdownlint-enable MD034 -->

1. Select the [!UICONTROL **Visualizations**] icon in the left rail, then drag the **[!UICONTROL Map]** visualization ![Map](/help/assets/icons/Globe.svg) into a panel that contains a freeform table. 

   Or

   Add a map visualization in any of the ways described in the [Add visualizations to a panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) section in [Visualizations overview](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   ![Map configuration](assets/map-configuration.png){width="50%"}

1. Specify the following basic information to configure the map visualization:

   * **[!UICONTROL Add metric]**: In the metric drop-down list, select a metric or calculated metric. (You can also drag a metric from the left rail.)

     >[!IMPORTANT]
     >
     >If you choose a metric that has [attribution applied](/help/data-views/component-settings/attribution.md#attribution-models), the same attribution is applied to the latitude and longitude pairs within the map visualization's current viewport.  
     >
     
     <!-- Only choose metrics that use Last Touch as the [attribution model](/help/data-views/component-settings/attribution.md#attribution-models) (this is the default attribution model for all metrics). Choosing a metric that has an attribution model other than Last Touch results in inaccurate map data, because attribution is applied to the latitude and longitude pairs. -->

   * **[!UICONTROL Add segment]**: (Optional) In the segment drop-down list, select a segment. Or drag in a segment from the list of segments.

   You can update this information after the visualization is built by selecting the Edit icon ![Edit](/help/assets/icons/Edit.svg) in the visualization header.

1. Select **[!UICONTROL Build]**.

   A world map visualization with bubbles is generated.

   ![](assets/map-visualization.png)

1. Continue with [View a map visualization](#view-a-map-visualization) and [Configure visualization settings](#configure-visualization-settings).

## View a map visualization

1. If you haven't already, build a map visualization as described in [Build a map visualization](#begin-building-a-map-visualization).

1. In the map visualization in Analysis Workspace, do any of the following:

    * **Zoom in**: You can zoom in on the map to magnify certain areas in any of the following ways:
    
      * Double-click the map with your mouse.
      
      * Use your mouse scroll wheel or similar action on your trackpad.  
      
      * Select the plus icon ![zoom-in icon](assets/map-zoomin-icon.png) on the map visualization. 
      
      The map zooms accordingly. The required dimension (country > state > city) is automatically updated, based on the zoom level.

    * **Zoom out**: You can zoom out on the map to view larger areas in any of the following ways:
    
      * Hold the Shift key and double-click the map with your mouse.
      
      * Use your mouse scroll wheel or similar action on your trackpad.  
      
      * Select the minus icon ![zoom-out icon](assets/map-zoomout-icon.png) on the map visualization. 
      
      The map zooms accordingly. The required dimension (country > state > city) is automatically updated, based on the zoom level.

    * **Rotate**: You can rotate the map in 2D or 3D by holding the [!UICONTROL Ctrl] key while dragging the map with your mouse.

      To reset the map to its original north alignment, select the compass icon ![compass icon](assets/map-compass-icon.png).

    * **Selection tool**: You can select an area of the map to [create a segment](#create-a-segment-from-the-map-visualization), [create a trend](#create-a-trended-line-chart-from-the-map-visualization), or [add a breakdown](#add-a-breakdown-from-the-map-visualization). 
    
      Click the selection tool ![map selection icon](assets/map-selection-icon.png), then drag your mouse to select the desired area.

    * **Compare**: You can compare two or more map visualizations in the same project by placing them side by side.

    * **Show period-over-period comparisons (such as year-over-year)**:

        * Show negative numbers. 
        
          For example, if you are plotting a year-over-year metric, the map can show -33% over New York.

        * With metrics that are of type *percent*, clustering averages the percentages together.

        * A green and red color scheme indicates positive and negative.

    * **Additional visualization settings**: Select the Settings icon ![Setting](/help/assets/icons/Setting.svg) in the visualization header to view additional settings for the map visualization. For more information, see [Configure visualization settings](#configure-visualization-settings).

1. **Save** the project to save all map settings (coordinates, zoom, rotation).
1. (Optional) The freeform table below the visualization can be populated by dragging in location dimensions and metrics from the left rail.

## Configure visualization settings

To configure settings for the map visualization:

1. In Analysis Workspace, open an existing map visualization, or [build a new one](#begin-building-a-map-visualization).

1. Hover over the map visualization, then select the Settings icon ![Setting](/help/assets/icons/Setting.svg) in the visualization header.

   The following options are available:

   | Section | Setting | Description |
   | --- |--- |--- |
   | **[!UICONTROL Map type]** | | |
   | |**[!UICONTROL Bubbles]**|Plots events using bubbles. A bubble chart is a multi-variable graph that is a cross between a scatterplot and a proportional area chart. This view is the default.|
   | |**[!UICONTROL Heatmap]**|Plots events using a heatmap. A heatmap is a graphical representation of data where the individual values contained in a matrix are represented as colors.|
   | **[!UICONTROL Styles]** | | |
   | |**[!UICONTROL Color theme]**|Shows the color scheme for the heat map and bubbles. You can choose among Coral, Reds, Greens or Blues. The default is Coral.|
   | |**[!UICONTROL Map style]**|You can choose from Basic, Streets, Bright, Light, Dark, and Satellite.|
   | | **[!UICONTROL Cluster radius]**|Groups data points together that are within the specified number of pixels. The default is 50.<p>This option is available only when **[!UICONTROL Bubbles]** is selected as the **[!UICONTROL Map type]**.</p>|
   | | **[!UICONTROL Custom max value]**|Lets you alter the threshold for the max value for the map. Adjusting this value adjusts the scale for the bubbles or heatmap values (color and size) relative to the custom max value that you set.|
   | | **[!UICONTROL Show annotations]** | Shows the annotations made for this visualization. |
   | | **[!UICONTROL Hide title]** | Hides the title of the visualization.  |

## Configure precise locations for dimensions

If you have custom datasets with deep precision, you can configure the map visualization to achieve location accuracy within a single meter. 

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. Select the data view that contains the dimensions that you want to configure to use more precise locations.

1. In the data view, select the **[!UICONTROL Components]** tab.

1. Select the dimensions that you are using for latitude and longitude that you want to configure. For more information about which dimensions you're using, see [Required context labels for latitude and longitude in the map visualization](#required-context-labels-for-latitude-and-longitude-in-the-map-visualization).

1. Configure the level of precision for the dimension:

   1. With the dimension that you want to configure still selected, expand the **[!UICONTROL Format]** section in the right rail.

      ![dimension item selected with format section expanded](assets/map-dimension-format.png)

   1. In the **[!UICONTROL Decimal places]** field, change the number of decimals to reflect the desired level of precision: 

      * **0:** Precise to the large region or country level in the map visualization. Shows 0 decimal places in Workspace reports. 

      * **1:** Precise to the region or large city level in the map visualization.  Shows 1 decimal place in Workspace reports. 
   
      * **2:** Precise to the town or zip code level in the map visualization. Shows 2 decimal places in Workspace reports. 

        This is the default selection.

      * **3:** Precise to the very small town or neighborhood level in the map visualization. Shows 3 decimal places in Workspace reports. 

      * **4:** Precise to a specific parcel of land or building level in the map visualization. Shows 4 decimal places in Workspace reports. 

      * **5:** Precise to a single meter in the map visualization. Shows 5 decimal places in Workspace reports. 

1. Select **[!UICONTROL Save and continue]** > **[!UICONTROL Save and finish]**.

## Create a segment from the map visualization {#map-create-segment}

You can create a segment based on a specific area that you select in the map visualization. When you create a segment based on a selected area, any data that is within the latitude and longitude of your selection is included in the segment. 

To create a segment from the map visualization:

1. Zoom or pan to the area of the map that contains the data that you want to use for your segment. 

1. Do either of the following:

   * **To create a segment from everything currently shown in the map:** Right-click anywhere on the map, then select **[!UICONTROL Create segment from current view]**.

   * **To create a segment for a more specific area of the map:** Click the selection tool ![map selection icon](assets/map-selection-icon.png), drag your mouse to select the desired area, then select **[!UICONTROL Create segment from selection]**.

1. Use the Segment builder to define the new segment. For more information, see [Segment builder](/help/components/segments/seg-builder.md).

## Create an audience from the map visualization

You can create an audience based on a specific area that you select in the map visualization.

To create an audience from the map visualization:

1. Zoom or pan to the area of the map that contains the data that you want to use for your audience.

1. Do either of the following:

   * **To create an audience from everything currently shown in the map:** Right-click anywhere on the map, then select **[!UICONTROL Create audience from current view]**.

   * **To create an audience for a more specific area of the map:** Click the selection tool ![map selection icon](assets/map-selection-icon.png), drag your mouse to select the desired area, then select **[!UICONTROL Create audience from selection]**.

1. Use the Audience builder to define the new audience. For more information, see [Audience builder](/help/components/audiences/publish.md#audience-builder) in [Create and publish audiences](/help/components/audiences/publish.md)

## Create a trended line chart from the map visualization

You can create a trended line chart visualization for the data within a specific area that you select in the map visualization.

To create a trended line chart from the map visualization:

1. Zoom or pan to the area of the map that contains the data that you want to use for the trended line chart. 

1. Do either of the following:

   * **To create a trended line chart from everything currently shown in the map:** Right-click anywhere on the map, then select **[!UICONTROL Trend from current view]**.

   * **To create a trended line chart for a more specific area of the map:** Click the selection tool ![map selection icon](assets/map-selection-icon.png), drag your mouse to select the desired area, then select **[!UICONTROL Trend]**.

   A line visualization is built that includes a trendline. For more information about this visualization, see [Line](/help/analysis-workspace/visualizations/line.md).

<!--

Can you do this?

## Add a breakdown from the map visualization

You can break down a specific dimension item, metric, segment, or date range for the data within a designated area that you select in the map visualization.

To add a breakdown from the map visualization:

1. (Optional) Zoom in on the specific area of the map that contains the data where you want to add the breakdown.

1. Click the selection tool ![map selection icon](assets/map-selection-icon.png), then drag your mouse to select the desired area.

1. Select **[!UICONTROL Add breakdown]**. 

-->

<!--

Can you do this?

## Export the map visualization as a PDF

To export the map visualization in PDF format:

1. how...

-->

