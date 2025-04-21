---
description: The Data Dictionary in Analysis Workspace allows users to catalogue and keep track of the various components in Analysis Workspace, including their intended use, which are approved, which are duplicates, and so forth.
title: View component information
feature: Components
role: User, Admin
exl-id: 1e538679-12e0-487c-917f-2ff2f1cc8436
---
# View component information

The Data Dictionary allows you to view information about a component, including the component description, similar components, other components a component is frequently used with, and more.

To view information about a component in the Data Dictionary:

1. Go to the Analysis Workspace project that contains the component that you want to view.

1. Select the [!UICONTROL **Data Dictionary**] icon in the left panel of Analysis Workspace. (Alternate ways of accessing the Data Dictionary are described in "Access the Data Dictionary" in [Data Dictionary overview](/help/components/data-dictionary/data-dictionary-overview.md).)

   The Data Dictionary window displays.

   ![Data Dictionary window showing Quick segments for Dimensions, Metrics, Segments, and Date ranges](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Ensure that the data view that contains the component you want to view is selected in the drop-down menu. By default, the data view that you are already in is displayed.

1. (Optional) In the search field, begin typing the name of the component you want to view.

   The type of component can be identified by both color and icon. **Dimensions** ![Dimension icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) are orange, **Segments** ![Segment icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) are blue, **Date ranges** ![Date range icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) are purple, and **Metrics** ![Metric icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) are green. The Adobe icon ![Adobe icon](assets/default-calc-metric-icon.png) indicates either a calculated metric template or a segment template, and the calculator icon ![Calculator icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indicated a calculated metric that was created by an Analytics administrator in your organization. 

1. (Optional) Select the **Filter** icon ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), then select any of the following segment options to segment the list of components:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | Show only components that are marked as Approved by an administrator. |
   | [!UICONTROL **Favorites**] | Show only components that are in your list of Favorites. For information about adding components to your list of favorites, see [Components overview](/help/components/overview.md). |
   | [!UICONTROL **Dimensions**] | Show only components that are Dimensions. (This option is also available in the [!UICONTROL **Quick segments**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Metrics**] | Show only components that are Metrics. (This option is also available in the [!UICONTROL **Quick segments**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Segments**] | Show only components that are Segments. (This option is also available in the [!UICONTROL **Quick segments**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Date ranges**] | Show only components that are Date Ranges. (This option is also available in the [!UICONTROL **Quick segments**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Show all**] | Show all components. This option is available only for administrators. |
   | [!UICONTROL **Unapproved**] | Show only components that are not yet marked as Approved by an administrator. As an administrator, this is helpful when identifying components that require your review and approval. This option is available only for administrators. |
   | [!UICONTROL **Missing Description**] | Show only components that do not yet have a description in the Description field. This option is available only for administrators. |
   | [!UICONTROL **Show duplicates**] | Show only components that have either the same name or the same description as that of another component in the selected data view. This includes components you create as well as those provided by Adobe. Names or descriptions must be exact matches in order to show as duplicates. This option is available only for administrators. |
   | [!UICONTROL **No recent data**] | Show only components that have not collected any data in the past 90 days. This option is available only for administrators. |
   | [!UICONTROL **Created by Adobe**] <!-- I don't see this option-->| Show only components that were created by Adobe. Components that were created by an administrator or another user in your organization are not shown. |

   {style="table-layout:auto"}

1. (Optional) Select the **Sort** icon ![Sort components icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), then select any of the following segment options to sort the list of components:
   
   {{components-sort-options}}

1. From the list of components, select the component you want to view.

   The following information about the component is displayed:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | <p>Indicates that the component has been reviewed and approved by the administrator.</p><p>Administrators see an option to [!UICONTROL **Unapprove**]. Selecting this option marks the component as "Not approved" to users.</p> |
   | [!UICONTROL **Not approved**] | <p>Indicates that the component has not yet been reviewed and approved by the administrator.</p><p>Administrators see an option to [!UICONTROL **Approve**]. Selecting this option marks the component as "Approved" to users.</p> |
   | [!UICONTROL **Context label**] | This field appears only if the component's context label has been updated in the data view. <p>For more information, see [Component settings](/help/data-views/component-settings/overview.md). </p> |
   | [!UICONTROL **Description**] | Describes the intended function of the component. (This information is added by the Analytics administrator, as described in [Add component descriptions](/help/components/add-component-descriptions.md).) |
   | [!UICONTROL **Frequently used with**] | <p>Shows components that are most commonly used with the component you are viewing.</p><p>Up to 5 components are shown across the 5 primary component types: Metric, Calculated Metric, Dimension, Segment, and Date Range.</p><p>This list is based on data from the past 90 days. Only components that you have access to view are shown.</p><p>Administrators can curate the components that users see in this section by selecting the desired components in the [!UICONTROL **Always Include**] and [!UICONTROL **Always Exclude**] drop-down fields. Before you curate the components that users see, first apply the **Show all** segment to ensure you are seeing any components that are not shared with you that might have been added by another administrator.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p>  |
   | [!UICONTROL **Similar to**] | <p>Shows components with similar names to the component you are viewing.</p><p>Up to 5 components are shown across the 5 primary component types: Metric, Calculated Metric, Dimension, Segment, and Date Range.</p><p>Only components that you have access to view are shown.</p><p>Any duplicate components in your data view will display here. Analytics administrators should identify and remove all duplicate components, as described in [Monitor Data Dictionary health](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administrators can curate the components that users see in this section by selecting the desired components in the [!UICONTROL **Always Include**] and [!UICONTROL **Always Exclude**] drop-down fields. Before you curate the components that users see, first apply the **Show all** segment to ensure you are seeing any components that are not shared with you that might have been added by another administrator.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all segment to make it editable. --></p><p>**NOTE:** Currently, the **Similar to** section includes only components you create and not those provided by Adobe. Adobe-provided components will be added in a future release.</p> |
   | [!UICONTROL **Product compatibility**] | Indicates where in Customer Journey Analytics this calculated metric can be used. <p>The possible values are:</p><ul><li>[!UICONTROL **Everywhere in Customer Journey Analytics**]: The calculated metric can be used throughout all of Customer Journey Analytics, including in Analysis Workspace, Report Builder, and so forth.</li><li>[!UICONTROL **Everywhere in Customer Journey Analytics (excluding experimentation)**]: The calculated metric can be used throughout all of Customer Journey Analytics, except in the Experimentation panel.</li> <p>For information about the criteria that determine whether a calculated metric can be used with experimentation, see [Use calculated metrics in the Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) in  [Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | [!UICONTROL **Tags**] | Shows all tags that are applied to the component. Users with administrator access can add tags when editing the component. |
   | [!UICONTROL **Component type**] | Lists the type of component it is, whether a Dimension, Metric, Segment, or Date Range. |
   | [!UICONTROL **Created by**] | Displays the name of the user who created the component. |
   | [!UICONTROL **Preview**] | Shows a preview of how the component looks in Analysis Workspace. |
   | [!UICONTROL **Date last modified**] | Displays the day the component was last modified. This section is displayed when viewing Segments, Metrics, Calculated metrics, and Date ranges. |

   {style="table-layout:auto"}

1. (Optional) Drag a component from the Data Dictionary into Analysis Workspace.
