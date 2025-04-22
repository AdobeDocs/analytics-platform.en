---
title: Content Analytics reporting
description: How to report on Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 6e756ae8-b969-46f1-95b8-d8fbb0d058ed
---
# Content Analytics reporting overview

You report, perform analysis and gain insights on Content Analytics within [Analysis Workspace](/help/analysis-workspace/home.md). A specific Workspace [template](#template) is available, so you can immediately access a pre-populated Workspace project with relevant content insights.

To start reporting on Content Analytics from scratch:

1. [Create a new](/help/analysis-workspace/build-workspace-project/create-projects.md) or [open an existing](/help/analysis-workspace/build-workspace-project/open-projects.md) project in Workspace.
1. Ensure you [select a data view](/help/analysis-workspace/c-panels/panels.md#data-view) for Content Analytics reporting. Content Analytics reporting is only available for data views that are [configured](/help/content-analytics/config/configuration.md) for Content Analytics. 
1. Drag a ![Table](/help/assets/icons/Table.svg) [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualization on the canvas.
1. Use [specific Content Analytics components](components.md) and other generic [components](/help/components/overview.md) (like segments, date ranges, annotations) to build your content analytics insights.

## Thumbnails

Based on the Content Analytics specific dimensions that you use in your project, thumbnails are displayed for assets and dimensions.

![Content Analytics thumbnails](../assets/aca-thumbnails.png)

By default, thumbnails are shown for relevant Content Analytics dimensions. To configure the display of thumbnails for a Content Analytics dimension:

* Hover over a header row for a Content Analytics dimension. For example, **[!UICONTROL Asset Name]** or **[!UICONTROL Experience IDs]**.
* Select ![Setting](/help/assets/icons/Setting.svg).
* In the **[!UICONTROL Row setting]** popup, underneath **[!UICONTROL Settings]**, check or uncheck **[!UICONTROL Show Thumbnails]**.


## Previews

For rows of a Content Analytics dimension that show thumbnails, you can open a preview popup window. 

To open the preview with the following details:

* Select ![InfoOutline](/help/assets/icons/InfoOutline.svg). You see the following details. 
  
  | Experience preview | Asset preview |
  |---|---|
  | ![Content Analytics Experience preview](../assets/aca-experience-preview.png) | ![Content Analytics Asset preview](../assets/aca-asset-preview.png) |
  | Name of the dimension (for example, **[!UICONTROL Experience ID])** | Name of the asset dimension (for example, **[!UICONTROL Asset ID])** |
  | **[!UICONTROL Impressions (all time)]**: Number of impressions for the experience. | **[!UICONTROL Impressions (all times)]**: Number of impressions for the asset. |
  | **[!UICONTROL Assets]**: Number of assets this experience contains. <br/>Select ![Breakdown](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** to inspect the assets. |**[!UICONTROL Experiences]**: Number of experiences where this asset is shown in. <br/>Select ![Breakdown](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** to inspect the assets. | 
  | **[!UICONTROL First impression]**: Date of first impression of the experience. | **[!UICONTROL First impression]**: Date of first impression of the asset. |
  |**[!UICONTROL  Most recent impression]**: Date of most recent impression of the experience. | **[!UICONTROL Most recent impression]**: Date of most recent impression of the asset. |
  | **[!UICONTROL Experience attributes]**: The [attributes](/help/content-analytics/report/components.md#experience-attributes) of the experience. | **[!UICONTROL Asset attributes]**: The [attributes](/help/content-analytics/report/components.md#asset-attributes) of the asset. |


## Template

A Content analytics [template](/help/analysis-workspace/templates/use-templates.md) is available to help you to learn what content and content attributes are performing best. The template is part of the [Web channel and Engagement use case](/help/analysis-workspace/templates/use-templates.md#web-engagement) and details how your content performs at a granular level. You can look at the performance of individual assets, or specific attributes. 

Based on what you learn, you might do a number of things. Like promote high performing assets on your home page, personalize content for specific segments to include high performing attributes, or rotate out content that has started to get stale.

To use the template:

1. Select **[!UICONTROL Workspace]** from the main menu.
1. Ensure you have selected a Data view that is configured for Content Analytics.
1. Search for, or use segments (**[!UICONTROL Web]** for **[!UICONTROL Channel]** and **[!UICONTROL Engagement]** for **[!UICONTROL Use Case]**s) to find and select the **[!UICONTROL Content analytics]** template.
1. Select **[!UICONTROL Use template]**.
1. In the **[!UICONTROL Set up your template]** dialog, select a metric from the **[!UICONTROL Select a conversion metric]** dialog. For example, **[!UICONTROL Asset CTR]**.
1. Select **[!UICONTROL Continue]**.

A **[!UICONTROL Content Analytics Overview]** project opens in [Analysis Workspace](/help/analysis-workspace/home.md). The project consists of four [panels](/help/analysis-workspace/c-panels/panels.md), where each panel provides [freeform tables](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) and [visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to answer a specific question:

* **What content performs the best?** 
  This panel helps you to understand which experiences and which assets in those experiences are driving engagement and conversion. Experiences are a full webpage, captured at a specific time. An experience can contain both text and multiple individual image assets. An asset is an individual image. 

  The panel consists of the following visualizations:

  * **Experiences**. 
   
    >[!NOTE]
    >
    >These visualizations only show when you have [included experiences](/help/content-analytics/config/guided.md#experience-capture-and-definition) in your Content Analytics configuration.
    > 

    * **Experience CTR**: a [summary change](/help/analysis-workspace/visualizations/summary-number-change.md) visualization, showing Experience CTR.
    * **Top converting experiences**: A [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) visualization showing top converting experiences based on the selected conversion metric.
    * **Top performing experiences**: A [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md)(including [thumbnails](#thumbnails) and [previews](#previews)) for the top performing experiences.

  * **Assets**

    * **Asset CTR**
      A [summary change](/help/analysis-workspace/visualizations/summary-number-change.md) visualization that shows Asset CTR.
    * **Top converting assets**
      A [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) visualization that shows top converting assets based on the selected conversion metric.
    * **Top performing assets**
      A [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (including [thumbnails](#thumbnails) and [previews](#previews)) for the top performing assets.
    * **Assets - views vs. conversion.**
      A [scatterplot](/help/analysis-workspace/visualizations/scatterplot.md) visualization that shows a scatter plot of asset views versus assets conversions. 

* **Which asset attributes contribute to conversions?** 
  Content Analytics uses AI and GenAI to assign every asset metadata automatically, like subjects, scenes, foreground colors, etc. An attribute is an AI assigned metadata tag describing what is in an asset or experience. For example: <code>foreground color: red</code> is an automatically assigned attribute. The visualizations help you identify which attributes of your assets contribute most to conversion.

  The panel consists of the following visualizations:

  * **Top converting asset attributes** 
    A [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) that shows the top converting asset attributes based on the selected conversion metric.
  * **Top converting assets attributes vs prior 30 days**
    A [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) visualization that shows the top converting asset attributes, compared to the prior 30 days, based on the selected conversion metric.
  * **Top converting assets attribute data**
    A [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) that shows the top converting attributes based on the selected conversion metric. Select a row in the table to update the Attribute trend visualization.
  * **Attribute trend**
    A [line](/help/analysis-workspace/visualizations/line.md) visualization showing the attribute trend for the selected top converting assets attribute.
  * **Asset foreground color**
    An example [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) that compares the performance of items from a single asset attribute category: Foreground Colors. You can replace this asset attribute with other asset attribute category dimensions. 

* **Which experience attributes contribute to conversions?** 

  >[!NOTE]
  >
  >This panel only shows when you have [included experiences](/help/content-analytics/config/guided.md#experience-capture-and-definition) in your Content Analytics configuration.
  > 
  
  While asset attributes focus on the visual qualities of images, experience attributes focus on the text of your page. The visualizations below let you explore which experience attributes contribute to conversion. These attributes are also automatically assigned using AI and GenAI models.

  The panel consists of the following visualizations:

  * **Top converting experience attributes** 
    A [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) visualization that shows the top converting experience attributes based on the selected conversion metric.
  * **Top converting experience attributes vs prior 30 days** 
    A [horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md) visualization that shows the top converting experience attributes, compared to the prior 30 days, based on the selected conversion metric.
  * **Top converting experience attribute data** 
    A [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) that shows the top converting experiences based on the selected conversion metric. Select a row in the table to update the Line visualization.
  * **Line** 
    A [line](/help/analysis-workspace/visualizations/line.md) visualization showing the trend for the selected top converting experience attribute.
  * **Experience keywords**
    A [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) showing the top experience keywords based on the selected conversion metric.

* **Where do assets appear on my site?** 
  A panel that consists of one freeform table that details where the most viewed assets appear on your site.

  The panel consists of one visualization:

  * **Where do the most viewed assets appear?**
    You can break down any asset by dimensions to help you better understand where that image appears. 
    
    In the example [freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) (including [thumbnails](#thumbnails) and [previews](#previews)), **[!UICONTROL Asset Perception ID]** is used instead of [!UICONTROL Asset Id]. Sometimes, the exact same image can get duplicated on your site with a different image URL. The [!UICONTROL Asset Perception ID] attribute helps to group these duplicates under a single ID. 
    
    Because assets can change on a page, each asset is broken down by **[!UICONTROL Experience Id]**, to identify which version of that page the asset appeared on. You can replace [!UICONTROL Experience Id] with other dimensions that help you understand the location of an asset on your site. For example, [!UICONTROL Page name], [!UICONTROL Page URL], or [!UICONTROL Site section]. 
    
    You can also swap out [!UICONTROL Asset Perception ID] with [!UICONTROL Asset Id] to get a record of where specific image URLs are being referenced. 


>[!MORELIKETHIS]
>
>[Content Analytics components](components.md)
>[Use templates](/help/analysis-workspace/templates/use-templates.md#web-engagement)
>
