# Snippets

## Release phase Limited Testing {#release-limited-testing}

>[!AVAILABILITY]
>
>The functionality described in this article is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Customer Journey Analytics release process, see [Customer Journey Analytics feature releases](/help/release-notes/releases.md).

## Release phase Limited Testing section {#release-limited-testing-section}

>[!AVAILABILITY]
>
>The functionality described in this section is in the Limited Testing phase of release and might not be available yet in your environment. This note will be removed when the functionality is generally available. For information about the Customer Journey Analytics release process, see [Customer Journey Analytics feature releases](/help/release-notes/releases.md).

## Data Dictionary filter criteria {#dd-filter-criteria}

1. (Optional) Select the **Filter** icon ![Data Dictionary Filter icon](/help/components/data-dictionary/assets/data-dictionary-filter-icon.png), then select any of the following filter options to filter the list of components:

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Approved**] | Show only components that are marked as Approved by an administrator. |
   | [!UICONTROL **Favorites**] | Show only components that are in your list of Favorites. For information about adding components to your list of favorites, see [Components overview](/help/components/overview.md). |
   | [!UICONTROL **Dimensions**] | Show only components that are Dimensions. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Metrics**] | Show only components that are Metrics. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) |
   | [!UICONTROL **Filters**] | Show only components that are Filters. (This option is also available in the [!UICONTROL **Quick filters**] tab when you first access the Data Dictionary.) <!--this is Filters in CJA--> |
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
   | [!UICONTROL **Tags**] | Shows all tags that are applied to the component. Users with administrator access can add tags when editing the component. |
   | [!UICONTROL **Component type**] | Lists the type of component it is, whether a Dimension, Metric, Filter, or Date Range. |
   | [!UICONTROL **Created by**] | Displays the name of the user who created the component. |
   | [!UICONTROL **Preview**] | Shows a preview of how the component looks in Analysis Workspace. |
   | [!UICONTROL **Date last modified**] | Displays the day the component was last modified. This section is displayed when viewing Filters, Metrics, Calculated metrics, and Date ranges. |

   {style="table-layout:auto"}

   ## Components sort options {#components-sort-options}

   |Option | Function |
   |---------|----------|
   | [!UICONTROL **Recommended**] | Sorts components with those that are recommended at the top of the list. Components that are used most frequently and most recently by you or by others in your organization are shown higher in the list. |
   | [!UICONTROL **Alphabetical**] | Sorts components alphabetically. |
   | [!UICONTROL **Categorical**] | Sorts components according to component type (dimension, metric, segment, date range). |

   {style="table-layout:auto"}

   