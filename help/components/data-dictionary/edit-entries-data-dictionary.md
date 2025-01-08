---
description: The Data Dictionary in Analysis Workspace allows users to catalogue and keep track of the various components in Analysis Workspace, including their intended use, which are approved, which are duplicates, and so forth.
title: Edit component entries
feature: Components
role: Admin
exl-id: 2d232811-e34a-4667-819c-cbe2a3e72702
---
# Edit component entries

Customer Journey Analytics administrators can edit component entries in the Data Dictionary for a given data view. Any changes made are visible to all users of the data view.

To edit a component in the Data Dictionary:

1. Go to the Analysis Workspace project that contains the component that you want to edit.

1. Select the **Data Dictionary** icon in the button panel of Analysis Workspace. (Alternate ways of accessing the Data Dictionary are described in "Access the Data Dictionary" in [Data Dictionary overview](/help/components/data-dictionary/data-dictionary-overview.md).)

   The Data Dictionary window displays.

   ![Data Dictionary administrator view showing Dictionary Health](assets/data-dictionary-admin.png)

1. Ensure that the correct data view is selected in the drop-down menu. By default, the data view that you are already in is displayed. 

1. (Optional) In the search field, begin typing the name of the component you want to edit.

   The type of component can be identified by both color and icon. **Dimensions** ![Dimension icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) are orange, **Filters** ![Segment icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) are blue, **Date ranges** ![Date range icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) are purple, and **Metrics** ![Metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) are green. The Adobe icon indicates either a calculated metric template or a filter template, and the calculator icon ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicated a calculated metric that was created by an Analytics administrator in your organization. 

   {{dd-filter-criteria}}

1. (Optional) Select the **Sort** icon ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), then select any of the following filter options to sort the list of components:

{{components-sort-options}}

1. From the list of components, select the component you want to edit.

1. Select the **Edit** icon ![Data Dictionary Edit icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) next to the component name. 

1. Edit any of the following information about the component:

{{dd-component-information}}

1. Click the **Save** icon ![Data Dictionary Save icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) to save your changes.
