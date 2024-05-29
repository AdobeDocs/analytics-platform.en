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

To add hyperlinks to one or more dimension items:

1. In a freeform table in Analysis Workspace, do any of the following:

   * Right-click a dimension name in the column header.

   * Right-click a single dimension item within the table.

   * Select multiple dimension items within the table (hold the Shift or Ctrl key to select mutliple items), then right-click one of the selected items.

1. Select [!UICONTROL **Create hyperlink**] from the right-click menu.

   <!-- add screenshot of "Create hyperlinks for dimension items" dialog -->

1. Choose from the following options:

   * [!UICONTROL **Use the value of the dimension as the URL**]: Choose this option for dimension items that have URL values, such as a Page URL dimension.

   * [!UICONTROL **Create a custom URL**]: Specify a static custom URL. Or, to create dynamic custom URLs for multiple dimension items, include '$value' or '$breakdown' within your custom URL.  '$breakdown' requires that you specify a breakdown dimension below.

      To create a custom URL, specify the following information:

      |Field | Description | 
      |---------|----------|
      | [!UICONTROL **Custom URL**] | B1 | 
      | [!UICONTROL **Breakdown dimension (optional)**] | B2 | 

   




