---
title: Create hyperlinks in a freeform table in Analysis Workspace
description: Learn how to add hyperlinks to dimension items in a freeform table in Analysis Workspace
feature: Visualizations
role: User
---
# Create hyperlinks for dimensions in a freeform table

You can add hyperlinks to dimension items to make them clickable within a freeform table in Analysis Workspace. 

This functionality is particularly helpful in the following circumstances:

* When dimension items represent URLs (for example, a Page URL dimension)

* When dimension items contain breakdowns that represent URLs (for example, a Page Name dimension that has a breakdown of a Page URL dimension)

* When dimension items or breakdowns represent part of a URL.

To add hyperlinks to one or more dimension items:

1. In a freeform table in Analysis Workspace, do any of the following:

   * Right-click a dimension name in the column header.

   * Right-click a single dimension item within the table.

   * Select multiple dimension items within the table (hold the Shift or Ctrl key to select mutliple items), then right-click one of the selected items.

1. Select [!UICONTROL **Create hyperlink**] from the right-click menu.

   <!-- add screenshot of "Create hyperlinks for dimension items" dialog -->

1. Choose from the following options:

   * [!UICONTROL **Use the value of the dimension as the URL**]: Choose this option for dimension items that represent URL values, such as a Page URL dimension. 
   
     For example, if you are using a Page URL dimension where the value of each dimension item is a URL, then selecting this option creates a hyperlink to the URL.

   * [!UICONTROL **Create a custom URL**]: Specify a static or dynamic custom URL. This option allows you to add a hyperlink to dimension items whose values are not URLs. 
   
     For example, if you are using a Page Name dimension where the value of each dimension item is the name of a page (and not a full URL), then selecting this option allows you to specify a hyperlink to use as the link for the dimension item.
   
     You can use the `$value` and `$breakdown` variables when creating a custom URL. See the table below for more information.

      To create a custom URL, specify the following information:

      |Field | Description | 
      |---------|----------|
      | [!UICONTROL **Custom URL**] | Specify a custom URL that you want to use for the hyperlink. The custom URL that you add can be static or dynamic: <ul><li>**Static URLs:** If you are adding a hyperlink to an individual dimension item, a static URL might be sufficient. <p>For example, if you have a Page Name dimension item, you can add a static URL that links users to a specific web page that you want to associate with the page name.</p></li><li>**Dynamic URLs:** If you are adding a hyperlink to multiple dimension items or to all dimension items in a dimension column, then a dynamic URL is probably more practical. <p>To make custom URLs dynamic, you include variables within the URL that allow the URL to dynamically change based on the value of the dimension itself, or the value of the breakdown dimension.</p><p>The following variables are available:</p> <ul><li>**`$value`:** Allows you to insert the value of the dimension item into the URL that you specify. <p>Consider the following scenario as an example:</p><p>Suppose that you want to add hyperlinks to multiple Page Name dimension items, where each item's value corresponds to a webpage name that's also part of the webpage's URL. In this case, you can construct a single custom URL that dynamically adjusts for each dimension item. </p><p>You can accomplish this by adding the `$value` variable to the end of the custom URL that you specify, like this: https://company-name.com/browse/product#$value</p><p>When the custom URL is applied to your Page Name dimension items that contain values of "ProductY" and "ProductZ", the generated hyperlinks would look something like this: https://company-name.com/browse/product#ProductY and https://company-name.com/browse/product#ProductZ. </p></li><li>**`$breakdown`:** Allows you to insert the value of the breakdown dimension item into the URL that you specify. The breakdown dimension is the dimension that you specify in the [!UICONTROL **Breakdown dimension**] field below. <p>For example, </p></li></ul>   | 
      | [!UICONTROL **Breakdown dimension (optional)**] | B2 | 

   




