---
title: Add hyperlinks in a freeform table in Analysis Workspace
description: Learn how to add hyperlinks to dimension items in a freeform table in Analysis Workspace
feature: Visualizations
role: User
---
# Add hyperlinks to dimensions in a freeform table

You can add hyperlinks to dimension items to make them clickable within a freeform table in Analysis Workspace. 

This functionality is particularly useful when adding hyperlinks to the following types of dimension items:

* Dimension items that have URL values that you want to link to (for example, a Page URL dimension)

* Dimension items that contain breakdowns that have URL values that you want to link to (for example, a Page Name dimension that has a breakdown of a Page URL dimension)

* Dimension items or breakdowns that have values that are part of a URL that you want to link to (for example, a Page Name dimension that is part of a URL)

To add hyperlinks to one or more dimension items:

1. In a freeform table in Analysis Workspace, do one of the following:

   * **Add a hyperlink to a single dimension item:** Right-click the dimension item within the table where you want to add the hyperlink.

   <!-- add screenshot -->
   
   * **Add hyperlinks to multiple dimension items:** Select the dimension items within the table where you want to add the hyperlinks (hold the Shift or Ctrl key to select multiple items), then right-click one of the selected items.

   <!-- add screenshot -->

   * **Add hyperlinks to all dimension items in a column:** Right-click the dimension name in the column header.

   <!-- add screenshot -->

1. Select [!UICONTROL **Add hyperlink**] from the right-click menu.

   The [!UICONTROL **Create hyperlinks for dimension items**] dialog is displayed.

   ![Add hyperlinks dialog](assets/table-hyperlinks-default.png)

1. Choose from the following options:

   * [!UICONTROL **Use the value of the dimension as the URL**]: Choose this option for dimension items that have URL values, such as a Page URL dimension. 
   
     For example, if you are using a Page URL dimension where the value of each dimension item is a URL, then selecting this option creates a hyperlink to the URL.

   * [!UICONTROL **Create a custom URL**]: Specify either a static or dynamic custom URL. Choose this option to add a hyperlink to dimension items that do not have URL values. 
   
     For example, if you are using a Page Name dimension where the value of each dimension item is the name of a page (and not a full URL), then selecting this option allows you to specify a hyperlink to use as the link for the dimension item.
   
     If you want to create dynamic URLs for multiple dimension items, you can use the `$value` and `$breakdown` variables within your custom URL. See the table below for more information.

      To create a custom URL, specify the following information:

      |Field | Description | 
      |---------|----------|
      | [!UICONTROL **Custom URL**] | Specify a custom URL that you want to use for the hyperlink. The custom URL that you add can be static or dynamic: <ul><li>**Static URLs:** If you are adding a hyperlink to an individual dimension item, a static URL might be sufficient. <p>For example, if you have a Page Name dimension item, you can add a static URL that links users to the specific web page that you want to associate with the page name.</p></li><li>**Dynamic URLs:** If you are adding a hyperlink to multiple dimension items or to all dimension items in a dimension column, then a dynamic URL is probably more practical. <p>To make custom URLs dynamic, you include variables within the URL that allow the URL to dynamically change based on the value of the dimension itself, or the value of the breakdown dimension.</p><p>The following variables are available:</p> <ul><li>**`$value`:** Allows you to insert the value of the dimension item into the URL that you specify. <p>Consider the following scenario as an example:</p><p>Suppose that you want to add hyperlinks to multiple Page Name dimension items, where the value of each dimension item is part of a webpage's URL. In this case, you can construct a single custom URL that dynamically adjusts for each dimension item. </p><p>You can accomplish this by adding the `$value` variable to the end of the custom URL that you specify. For example:</p> <p>https://company-name.com/browse/product#$value</p><p>When this custom URL is applied to your Page Name dimension items whose values are "ProductY" and "ProductZ", the generated hyperlinks would look something like this: </p><p>https://company-name.com/browse/product#ProductY</p><p>and</p><p> https://company-name.com/browse/product#ProductZ. </p><p>![use values in hyperlinks](assets/table-hyperlinks-vaule.png)</p></li><li>**`$breakdown`:** Allows you to insert the value of the breakdown dimension item into the URL that you specify. The breakdown dimension is the dimension that you specify in the [!UICONTROL **Breakdown dimension**] field below. <p>Consider the example scenario described for the [!UICONTROL **Breakdown dimension**] field below.</p></li></ul>   | 
      | [!UICONTROL **Breakdown dimension (optional)**] | Begin typing the name of the breakdown dimension that you want to use, then select it in the drop-down list. <p>If you select a breakdown dimension in this field, you must reference it by using the `$breakdown` variable in the URL that you specify in the [!UICONTROL **Custom URL**] field.</p><p>Consider the following scenario as an example:</p><p>Suppose that you want to add hyperlinks to multiple Page Name dimension items, and each dimension item contains a breakdown of a Page URL dimension. In this case, you can create hyperlinks on the value of the Page Name dimensions by referencing the Page URL breakdown dimension</p><p>You can accomplish this by specifying `$breakdown` in the [!UICONTROL **Custom URL**] field, and then selecting the Page URL dimension in the [!UICONTROL **Breakdown dimension**] field. </p><p>![use breakdowns in hyperlinks](assets/table-hyperlinks-breakdown.png)</p> | 

1. Select [!UICONTROL **Create**].

   Users who view the freeform table can click dimension items to be taken to the hyperlinks that you added. Hyperlinked pages are launched in a separate browser tab. <!--true?-->
 
   <!-- add screenshot of a table with hyperlinks.>


