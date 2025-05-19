---
description: Use the map visualization in a Workspace project.
title: Map
feature: Visualizations
role: User, Admin
hide: yes
hidefromtoc: yes
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

>[!NOTE]
>
>The map visualization uses WebGL for graphics display. If your graphics drivers do not support WebGL rendering, you might need to update your drivers.

## Map visualization in Customer Journey Analytics vs. Adobe Analytics

The map visualization in Customer Journey Analytics differs from the map visualization in Adobe Analytics in the following ways:

| Feature | Customer Journey Analytics | Adobe Analytics |
|---------|----------|---------|
| Data source | Use any segment available in your data view as your data source.  | Provides the following options: <ul><li>Mobile lat/long</li><li>Geographic Dimension<br/>Represents geo segmentation data about visitor location based on the visitor's IP address. This data gets transformed into [!UICONTROL Country], [!UICONTROL Region], and [!UICONTROL City]. Note that it does not go to the DMA or Zip Code level.</li></ul> |
| Precision | For datasets with deep precision, you can configure the dimensions in your data view to show up to 5 decimal places. This allows the map visualization to be accurate within a single meter. <p>For more information, see [Configure precise locations for dimensions](#configure-precise-locations-for-dimensions).</p> | C2 |
| A3 | B3 | C3 |


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Map visualization in Analysis Workspace](https://video.tv.adobe.com/v/23559/?quality=12){target=&#34;_blank&#34;} for a demo video.

>[!ENDSHADEBOX]

## Begin building a map visualization

1. Add a blank panel to your project, select the [!UICONTROL **Visualizations**] icon in the left rail, then drag the ![Map](/help/assets/icons/Globe.svg) [!UICONTROL Map] visualization into the panel. 

   Or

   Add a map visualization in any of the ways described in the [Add visualizations to a panel](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) section in [Visualizations overview](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md).

   ![Map configuration](assets/map-configuration.png){width="50%"}

1. Specify the following basic information to configure the map visualization:

   * Metric: In the metric drop-down list, select a metric. Or drag in a metric from the list of metrics (including calculated metrics).

   * Segment: In the segment drop-down list, select a segment. Or drag in a segment from the list of segments.

   You can update this information after the visualization is built by selecting the edit icon ![Edit](/help/assets/icons/Edit.svg) in the visualization header.

1. Select **[!UICONTROL Build]**.

   A world map visualization with bubbles is generated.

   ![](assets/map-visualization.png)

1. (Optional) Continue with [Configure visualization settings](#configure-visualization-settings).

## View a map visualization



## Configure visualization settings

To configure settings for the map visualization:

1. In Analysis Workspace, open an existing map visualization, or [begin building a new one](#begin-building-a-map-visualization).

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
   | | **[!UICONTROL Cluster radius]**|Groups data points together that are within the specified number of pixels. The default is 50.|
   | | **[!UICONTROL Custom max value]**|Lets you alter the threshold for the max value for the map. Adjusting this value adjusts the scale for the bubbles or heatmap values (color and size) relative to the custom max value that you set.|
   | | **[!UICONTROL Show annotations]** | Show the annotations made for this visualization. |
   | | **[!UICONTROL Hide title]** | Hide the title of the visualization.  |

## Configure precise locations for dimensions

If you have custom datasets with deep precision, you can configure the map visualization to achieve location accuracy within a single meter. 

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. Select the data view that contains the dimensions that you want to configure to use more precise locations.

1. In the data view, select the **[!UICONTROL Components]** tab.

1. Select the dimension that you want to configure.

1. Configure the level of precision for the dimension:

   1. With the dimension that you want to configure still selected, expand the **[!UICONTROL Format]** section in the right rail.

      ![dimension item selected with format section expanded](assets/map-dimension-format.png)

   1. In the **[!UICONTROL Decimal places]** field, change the number of decimals to reflect the desired level of precision: 

      * **0:** Precise to the large region or country level in the map visualization. Shows 0 decimal places in Worspace reports. 

      * **1:** Precise to the region or large city level in the map visualization.  Shows 1 decimal place in Worspace reports. 
   
      * **2:** Precise to the town or zip code level in the map visualization. Shows 2 decimal places in Worspace reports. 

        This is the default selection.

      * **3:** Precise to the very small town or neighborhood level in the map visualization. Shows 3 decimal places in Worspace reports. 

      * **4:** Precise to a specific parcel of land or building level in the map visualization. Shows 4 decimal places in Worspace reports. 

      * **5:** Precise to a single meter in the map visualization. Shows 5 decimal places in Worspace reports. 

1. Configure latitude and longitude context labels for the dimension:

   1. With the dimension that you want to configure still selected, expand the **[!UICONTROL Component settings]** section in the right rail.

   1. In the **[!UICONTROL Context labels]** field, begin typing `Latitude`, then select it when it appears in the drop-down menu.

      ![Latitude context label](assets/map-dimension-latitude.png)

   1. In the **[!UICONTROL Context labels]** field, begin typing `Longitude`, then select it when it appears in the drop-down menu. 

## Export the map visualization as a PDF

To export the map visualization in PDF format:

1. 

