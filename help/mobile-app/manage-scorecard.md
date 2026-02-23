---
description: How to view and manage Analytics dashboards scorecards
title: Manage scorecards
feature: Analytics Dashboards
role: User, Admin
solution: Customer Journey Analytics
exl-id: 6a0de7db-689d-448d-b8e0-90af4a5ee325
---
# Manage scorecards

This topic instructs curators of Customer Journey Analytics data on how to view and manage scorecard elements.

## View and configure tile properties {#tiles}

When you click a tile in the scorecard builder, the right-hand rail displays the properties and characteristics associated with that tile and its detail slide. In this rail, you can provide a new **Title** for the tile and alternatively configure the tile by applying segments.

![Properties tile](assets/properties-tile-new.png)

## View detail slides {#view-detail-slides}

When you click on tiles, a dynamic pop-up window displays how the detail slide appears to the executive user in the app. You can add dimensions to break down your data for your specific needs. If a dimension hasn't been applied, the breakdown dimension will be **hour** or **days**, depending on the default date range.

Breakdowns refine your analysis by breaking down metrics by dimension items such as the following:

* Unique Visitors metric broken down by Ad Platform (AMO ID)
* Visits broken down by Product Category (Retail)
* Total Revenue broken down by Product Name

![Breakdown_view](assets/break_view.png)

Each dimension added to the tile will show up in a drop-down menu in the detailed view of the app. The executive user can then choose among the options listed in the drop-down menu.

## Customize detail slides {#customize-detail-slide}

Custom detail slides allow you to be even more targeted about what information you share with your audience.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Custom detail views](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/visitor-id/stitching-enablement-and-validation){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


You can modify the layout for each detail slide and add text to better explain what the end user may see in the data. You can also change the chart type using the drop-down menu.

![Custom detail slide](assets/custom-detail-slide.png)

### Change the slide layout

Change the slide layout to focus on the most important information. For example, you can change the layout to show just a chart or just a table. To change the slide layout, select one of the pre-designed formats.

![Slide layout](assets/layout.png)

You can also change the slide layout by dragging and dropping visualization components from the left-hand rail onto the canvas. Each detail slide may only accommodate two visualizations at a time.

![Slide layout change](assets/slide-layout-change.png)

### Add descriptive text to a slide

You can add text to provide meaningful information about what is contained in the charts or nuances about the data.

To add text to a detail slide, select a layout that shows the `T` symbol, or drag and drop the Text visualization component over from the left rail. The text editor will automatically open when adding a new text visualization or choosing a slide layout with text. The Text editor provides all standard options for formatting your text. You can apply text styles such as paragraph, headings, and subheadings, and apply bold and italicized font. You can justify text, add bulleted and numbered lists, and add links. When you're finished editing, select the minimize button in the upper-right corner of the text editor to close it. To edit text you already added, select the pencil icon to open the text editor again.

![Slide layout change](assets/add-descriptive-text.png)

## Remove components {#remove}

Similarly, to remove a component that is applied to the entire scorecard, click anywhere on the scorecard outside of the tiles and then remove it by clicking the **x** that appears when you hover over the component, as shown below for the **First Time Visits**:

![Remove_components](assets/new_remove.png)

## Create data stories {#create-data-story}

A data story is a collection of supporting data points, business context, and related metrics built around a central theme or metric. 

For example, if you focus on web traffic, your most important metric may be visits, but you may also be interested in new persons, unique persons, and you may want to see data broken down by web page or by what device type the traffic is coming from. Data stories in mobile scorecard projects let you put your most important metrics front and center while telling the whole story behind the metrics with multiple detail slides. 

Watch the video to learn more about creating data stories in mobile scorecard projects in Analysis Workspace.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data stories for Mobile scorecard projects](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/dashboards/create-a-mobile-scorecard){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


**To create a data story** {#data-story-create}

Build your data story by adding multiple detail slides to a tile.

1. Start with a mobile scorecard project. 
1. Select a tile that you want to create a story from. 
   ![Create a data story](assets/data-story1.png)
   ![Create data story icons](assets/create-data-story.png){width=".50%"}
1. Add slides to build your data story. Your first slide is generated by default.
   To add new slides, either hover over or click on a slide, then select from the available options: 
   * Tap the + sign to create a new slide. 
   * Tap the duplicate icon to duplicate the existing slide.
1. If you create a blank slide, drag and drop components from the left rail, or choose a layout to automatically populate the slide with the data from the tile. 
   ![Create a data story](assets/data-story2.png)
To delete a slide, tap the trash icon. 

### Customize a data story {#customize-data-story}

Data stories allow you to customize everything so you can share information that you want to share and exclude everything that you don't need. You can customize tiles and individual slides to add segments, show breakdowns, change the layout, and change the visualizations. 

**To customize tiles**

1. Tap a tile. The selected tile is outlined in blue, and the right panel shows the Tile properties.
1. Change the title, chart type, and other tile options.
1. Drag a component onto the tile.
   ![Create a data story](assets/data-story3.png)
    When you drag and drop a component such as a visualization onto a tile, the component is applied to all data story slides.
1. To apply a change only to the title, hold the Shift key to apply the change.
    ![Create a data story](assets/data-story4.png)

>[!NOTE]
>Slides inherit components from the tile, but tiles don't inherit components from slides.

**To customize individual slides**

You can change the visualization for individual slides in a data story. For example, you can change a horizontal bar to a doughnut graph for a specific slide. You can also change the layout. See [Customize detail slides](#customize-detail-slide).

### Preview a data story {#preview-data-story}

After you create a data story, use the **Preview** button to view and interact with a data story as if you were an app user. For information about previewing your data story, see [Preview a scorecard](#preview)

### Navigate between tiles and slides {#navigate-tiles-slides}

The navigation bar displays icons that represent what's on each slide. The navigation bar makes it easy to navigate to a specific slide if you have a lot of slides. 

To move between the tile and slides, tap the navigation bar.
![Create a data story](assets/data-story5.png)
![Create a data story](assets/data-story-nav.png){width="45%"}

You can also navigate back and forth by using the arrows on your keyboard or by selecting a component and holding it to the left or right of your screen to scroll.

## Preview scorecards {#preview}

You can preview how the scorecard will look and function once it is published in the Adobe Analytics dashboards app.

1. Click **[!UICONTROL Preview]** in the upper right hand corner of the screen.

    ![Preview_scorecards](assets/preview.png)

1. To view what the scorecard will look like on different devices, select a device from the [!UICONTROL Device preview] drop-down menu.

    ![Device_preview](assets/device-preview.png)

1. To interact with the preview, you can:

    * Left click to simulate tapping on the phone screen.

    * Use your computer's scroll function to simulate scrolling the phone screen with your finger.

    * Click and hold to simulate pressing and holding your finger on the phone screen. This is useful for interacting with the visualizations in the detailed view.

## Share scorecards {#share}

To share the scorecard with an executive user:

1. Click the **[!UICONTROL Share]** menu and select **[!UICONTROL Share scorecard]**.

1. In the **[!UICONTROL Share Mobile Scorecard]** form, complete the fields by:

    * Providing the name of the scorecard
    * Providing a description of the scorecard
    * Adding relevant tags
    * Specifying the recipients for the scorecard

1. Click **[!UICONTROL Share]**.

![Share_Scorecards](assets/new_share.png)

After you have shared a scorecard, your recipients can access it on their Analytics dashboards. If you make subsequent changes to the scorecard in the scorecard builder, they will be automatically updated in the shared scorecard. Executive users will then see the changes after refreshing the scorecard on their app.

If you update the scorecard by adding new components, you may want to share the scorecard again (and check the **[!UICONTROL Share embedded components]** option) in order to make sure that your executive users have access to these changes.

### Share scorecards using a shareable link

Using a shareable link makes it easy to share a scorecard in an email, document, or text message app. The shareable link lets recipients open the scorecard on their desktop or on the dashboards mobile app. Shareable deep linking makes it even easier to share projects and boost engagement with your stakeholders.

To share a scorecard using a shareable link

1. Click the **[!UICONTROL Share]** menu and select **[!UICONTROL Share scorecard]**.

   ![Share_Scorecards](assets/share-scorecard.png)

1. Copy the link and paste it into an email, document, or IM app.

   When a recipient uses a desktop app or browser to open the link, the mobile scorecard project will open in Workspace.

   When a recipient opens the link on a mobile device, the scorecard will open directly in the Adobe Analytics dashboards app.

   If a recipient hasn't downloaded the mobile app, they'll be directed to the app listing in the App Store or Google Play Store where they can download it.


## Remove [!UICONTROL Unspecified] dimension item {#remove-dims}

If you want to remove [!UICONTROL Unspecified] dimension items from your data, do the following:

1. Select the correct tile.
1. In the right rail, under **[!UICONTROL Drill ins]**, select the right-arrow next to the dimension item whose **[!UICONTROL Unspecified]** items you want to remove.

    ![Properties with arrow pointing to the right-arrow next to the dimention name.](assets/unspecified.png)

1. Click the icon next to **[!UICONTROL Unspecified]** to remove unspecified data from your reporting. (You can also remove any other dimension item.)

## View intelligent captions in scorecards {#captions}

Intelligent captions can help non-analysts better make sense of their data without the help of analysts. Intelligent captions use advanced Machine Learning and Generative AI to provide valuable natural-language insights for visualizations.

These captions pick out key statistical insights in the data and phrase them in natural language, thereby helping the non-analyst develop their data literacy.

Intelligent caption are available for all visualizations in the mobile app, include Line, Donut, Bar Chart, and Summary Number.

To view intelligent captions in a mobile scorecard:

1. In a scorecard, click into a tile. For example, in this scorecard, click into the line graph at the bottom.

    ![Scorecard with line visualization](assets/caption1.png)

1. Tap the blue icon  at the top right to generate the captions. The captions will appear below the line graph.

    ![Intelligent caption in line visualization](assets/caption2.png)

1. Swipe right to view all intelligent captions.

    Intelligent captions can point to data spikes, anomalies, trends, declines, correlations, and other phenomena.

1. Tap the black flag inside a caption to report a problem, such as harmful or illegal content.

    ![Report problem with caption](assets/caption-report.png)

1. Click the X to exit out of the **[!UICONTROL Report results]** dialog.
