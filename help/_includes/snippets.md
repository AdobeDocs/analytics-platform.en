# Snippets

## Release phase Limited Testing {#release-limited-testing}

>[!AVAILABILITY]
>
>The functionality described in this article is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Customer Journey Analytics release process, see [Customer Journey Analytics feature releases](/help/release-notes/releases.md).

## Release phase Limited Testing section {#release-limited-testing-section}

>[!AVAILABILITY]
>
>The functionality described in this section is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Customer Journey Analytics release process, see [Customer Journey Analytics feature releases](/help/release-notes/releases.md).

## Select package {#select-package}

>[!NOTE]
>
>You must have the **Select** package or higher in order to use the functionality described in this section. Contact your administrator if you're unsure which Customer Journey Analytics package you have.

## Prime package {#prime-package}

>[!NOTE]
>
>You must have the **Prime** package or higher in order to use the functionality described in this section. Contact your administrator if you're unsure which Customer Journey Analytics package you have.

## Ultimate package {#ultimate-package}

>[!NOTE]
>
>You must have the **Ultimate** package in order to use the functionality described in this section. Contact your administrator if you're unsure which Customer Journey Analytics package you have.


## Data Dictionary filter criteria {#dd-filter-criteria}

1. (Optional) Select the **Filter** icon ![Data Dictionary Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg), then select any of the following filter options to filter the list of components:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | Show only components that are marked as Approved by an administrator. |
   | [!UICONTROL **Favorites**] | Show only components that are in your list of Favorites. For information about adding components to your list of favorites, see [Components overview](/help/components/overview.md). |
   | [!UICONTROL **Dimensions**] | Show only components that are Dimensions. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Metrics**] | Show only components that are Metrics. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Filters**] | Show only components that are Filters. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) <!--this is Filters in Customer Journey Analytics--> |
   | [!UICONTROL **Date ranges**] | Show only components that are Date Ranges. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Show all**] | Show all components. This option is available only for administrators. |
   | [!UICONTROL **Unapproved**] | Show only components that are not yet marked as Approved by an administrator. As an administrator, this is helpful when identifying components that require your review and approval. This option is available only for administrators. |
   | [!UICONTROL **Missing Description**] | Show only components that do not yet have a description in the Description field. This option is available only for administrators. |
   | [!UICONTROL **Show duplicates**] | Show only components that have either the same name or the same description as that of another component in the selected data view. This includes components you create as well as those provided by Adobe. Names or descriptions must be exact matches in order to show as duplicates. This option is available only for administrators. |
   | [!UICONTROL **No recent data**] | Show only components that have not collected any data in the past 90 days. This option is available only for administrators. |
   | [!UICONTROL **Created by Adobe**] <!-- I don't see this option-->| Show only components that were created by Adobe. Components that were created by an administrator or another user in your organization are not shown. |

   {style="table-layout:auto"}

## Data Dictionary component information {#dd-component-information}

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | <p>Indicates that the component has been reviewed and approved by the administrator.</p><p>Administrators see an option to [!UICONTROL **Unapprove**]. Selecting this option marks the component as "Not approved" to users.</p> |
   | [!UICONTROL **Not approved**] | <p>Indicates that the component has not yet been reviewed and approved by the administrator.</p><p>Administrators see an option to [!UICONTROL **Approve**]. Selecting this option marks the component as "Approved" to users.</p> |
   | [!UICONTROL **Description**] | Describes the intended function of the component. (This information is added by the Analytics administrator, as described in [Add component descriptions](/help/components/add-component-descriptions.md).) |
   | [!UICONTROL **Frequently used with**] | <p>Shows components that are most commonly used with the component you are viewing.</p><p>Up to 5 components are shown across the 5 primary component types: Metric, Calculated Metric, Dimension, Filter, and Date Range.</p><p>This list is based on data from the past 90 days. Only components that you have access to view are shown.</p><p>Administrators can curate the components that users see in this section by selecting the desired components in the [!UICONTROL **Always Include**] and [!UICONTROL **Always Exclude**] drop-down fields. Before you curate the components that users see, first apply the **Show all** filter to ensure you are seeing any components that are not shared with you that might have been added by another administrator.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p>  |
   | [!UICONTROL **Similar to**] | <p>Shows components with similar names to the component you are viewing.</p><p>Up to 5 components are shown across the 5 primary component types: Metric, Calculated Metric, Dimension, Filter, and Date Range.</p><p>Only components that you have access to view are shown.</p><p>Any duplicate components in your data view will display here. Analytics administrators should identify and remove all duplicate components, as described in [Monitor Data Dictionary health](/help/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Administrators can curate the components that users see in this section by selecting the desired components in the [!UICONTROL **Always Include**] and [!UICONTROL **Always Exclude**] drop-down fields. Before you curate the components that users see, first apply the **Show all** filter to ensure you are seeing any components that are not shared with you that might have been added by another administrator.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTE:** Currently, the **Similar to** section includes only components you create and not those provided by Adobe. Adobe-provided components will be added in a future release.</p> |
   | [!UICONTROL **Product compatibility**] | Indicates where in Customer Journey Analytics this calculated metric can be used. <p>The possible values are:</p><ul><li>[!UICONTROL **Everywhere in Customer Journey Analytics**]: The calculated metric can be used throughout all of Customer Journey Analytics, including in Analysis Workspace, Report Builder, and so forth.</li><li>[!UICONTROL **Everywhere in Customer Journey Analytics (excluding experimentation)**]: The calculated metric can be used throughout all of Customer Journey Analytics, except in the Experimentation panel.</li> <p>For information about the criteria that determine whether a calculated metric can be used with experimentation, see [Use calculated metrics in the Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md#use-calculated-metrics-in-the-experimentation-panel) in  [Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md).</p></ul> |
   | [!UICONTROL **Tags**] | Shows all tags that are applied to the component. Users with administrator access can add tags when editing the component. |
   | [!UICONTROL **Component type**] | Lists the type of component it is, whether a Dimension, Metric, Filter, or Date Range. |
   | [!UICONTROL **Created by**] | Displays the name of the user who created the component. |
   | [!UICONTROL **Preview**] | Shows a preview of how the component looks in Analysis Workspace. |
   | [!UICONTROL **Date last modified**] | Displays the day the component was last modified. This section is displayed when viewing Filters, Metrics, Calculated metrics, and Date ranges. |

   {style="table-layout:auto"}

## Components sort options {#components-sort-options}

| Option | Function |
|---------|----------|
| **[!UICONTROL Recommended]** | Sort components for each type (dimension, metric, filter and date range) based on their recommendation. Components that are used most frequently and most recently by you or by others in your organization are shown higher in each list. |
| **[!UICONTROL Last modified]** | Sort components for each type (dimension, metric, filter and date range) based on their last modified date. Components that are modified most recently are shown highter in each list. | 
| **[!UICONTROL Alphabetical]** | Sort components for each type (dimension, metric, filter and date range) in ascending alphabetic order. |
| **[!UICONTROL Categorical]** | Sort components for each type (dimension, metric, filter and date range) based on their category. For example Curated versus Non-curated data view components. |

{style="table-layout:auto"}

## Time comparison {#apply-time-comparison}

You can compare the current time period to a previous time period. If you select an option in this menu, every data point receives a similarly colored dotted-lined counterpart. This counterpart represents that same metric in the selected previous date range. Setting this option doubles the number of items on the chart and rows in the table.

Available time comparison options include the previous period, 13 weeks prior, 52 weeks prior, and a Customized date range. If you select Customized date range, additional options appear to let you select the number and granularity. If you select None, the date comparison is removed.


## Video demonstration Adobe Analytics {#videoaa}

This video demonstrates the functionality using Adobe Analytics. However, the functionality is similarly available in Customer Journey Analytics. Be aware of the following differences in terminlogy.

| Adobe Analytics | Customer Journey Analytics |
|---|---|
| Segments | Filters |
| Visitor | Person |
| Visit | Session |
| Hit | Event |

{style="table-layout:fixed"}

## Filters panel {#filterspanel}

1. Select ![Filter](/help/assets/icons/Filter.svg) to open the Filters panel. If you need more space for the Filters list, you can select ![Filter](/help/assets/icons/Filter.svg) once more to close the panel.
1. Select filters from any of the available filter sections. 

## Tag filter section {#tagfiltersection}

| Tags   | Description |
|---|---|
| ![Tags](/help/assets/filter-tag.png){width="300"} | The **[!UICONTROL Tags]** section lets you filter on tags. <ul><li>You can ![Search](/help/assets/icons/Search.svg) *Search Tags* to search for tags you can use to filter.</li><li>You can select more than one tag. The tags available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(1)**: The number of selected tags (if one or more tags are selected).</li><li>**2︎⃣**: The number of tags available for the items resulting from the current filter.</li><li>7︎⃣: The number of items associated with the specific tag.</li></ul></li></ul> |


## Data view filter section {#dataviewfiltersection}

| Data view | Description |
|---|---|
| ![Data views](/help/assets/filter-dataview.png){width="300"} | The **[!UICONTROL Data view]** section lets you filter on data views. <ul><li>You can ![Search](/help/assets/icons/Search.svg) *Search Data views* to search for data views you can use to filter.</li><li>You can select more than one data view. The data views available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(2)**: The number of selected data views (if one or more data views are selected).</li><li>**3︎⃣**: The number of data views available for the items resulting from the current filter.</li><li>4︎⃣: The number of items associated with the specific data view.</li></ul></li></ul> |


## Owner filter section {#ownerfiltersection}

| Owner | Description |
|---|---|
| ![Owners](/help/assets/filter-owners.png){width="300"} | The **[!UICONTROL Owner]** section lets you filter on owners. <ul><li>You can ![Search](/help/assets/icons/Search.svg) *Search Owners* to search for owners you can use to filter.</li><li>You can select more than one owner. The owners available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(2)**: The number of selected owners (if one or more owners are selected).</li><li>**3︎⃣**: The number of owners available for the items resulting from the current filter.</li><li>4︎⃣: The number of items associated with the specific owner.</li></ul></li></ul> |


## Other filters filter section {#otherfiltersfiltersection} 

| Other filters | Description |
|---|---|
| ![Other filters](/help/assets/filter-other.png){width="300"} | The **[!UICONTROL Other filters]** section lets you filter on other predefined filter.<ul><li>You can select one or more of the following options:<ul><li> **[!UICONTROL Show all]**</li><li>**[!UICONTROL Shared with me]**</li><li>**[!UICONTROL Mine]**</li><li>**[!UICONTROL Approved]**</li><li>**[!UICONTROL Favorites]**</li></ul> What you can select depends on your role and permissions.</li><li>You can select more than one other filter. The other filters available depend on selections made in other sections in the filter panel.</li><li>The numbers indicate:<ul><li>**(1)**: The number of selected other filters (if one or more other filters are selected).</li><li>**5︎⃣**: The number of other filters available for the items resulting from the current filter.</li><li>4︎⃣: The number of items associated with the specific other filter.</li></ul></li></ul> |

## Date range filter section  {#daterangefiltersection} 

| Applied date range | Description |
|---|---|
| ![Date range](/help/assets/filter-daterange.png){width="300"} | The Applied date range section let you filter on a date range applicable to the items.<ol><li>Select a date range.</li><li>In the calendar popup define a date range, or select one of the available presets.<br>Alternatively, you can also specify a date range directly in the Date range section of the Filter panel.</li></ol><ul><li>The numbers indicate:<ul><li>**(1)**: The number of modified date ranges modified from default presets.</li><li>**5︎⃣**: The number of date ranges available for the items resulting from the current filter.</li></ul> |
