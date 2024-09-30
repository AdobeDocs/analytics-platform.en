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

>[!NOTE]
>
>This video demonstrates the functionality using Adobe Analytics. However, the functionality is similarly available in Customer Journey Analytics. Be aware of the following differences in terminlogy.
>
>
>| Adobe Analytics | Customer Journey Analytics |
>|:---:|:---:|
>| Segments | Filters |
>| Visitor | Person |
>| Visit | Session |
>| Hit | Event |
>

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


## Attribution models {#attribution-models-details}

An attribution model determines which dimension items get credit for a metric when multiple values are seen within a metric's lookback window. Attribution models only apply when there are multiple dimension items set within the lookback window. If only a single dimension item is set, that dimension item gets 100% credit regardless of attribution model used.

| Icon | Attribution model | Definition |
| :---: | :--- | --- |
| ![Last Touch](/help/assets/icons/AttributeLastTouch.svg) | Last Touch | Gives 100% credit to the touch point occurring most recently before conversion. This attribution model is typically the default value for any metric where an attribution model is not otherwise specified. Organizations typically use this model where the time to conversion is relatively short, such as with analyzing internal search keywords. |
| ![First Touch](/help/assets/icons/AttributeFirstTouch.svg) | First Touch | Gives 100% credit to the touch point first seen within the attribution lookback window. Organizations typically use this model to understand brand awareness or customer acquisition. |
| ![Linear](/help/assets/icons/AttributeLinear.svg) | Linear | Gives equal credit to every touch point seen leading up to a conversion. It is useful where conversion cycles are longer or require more frequent customer engagement. Organizations typically use this attribution model measuring mobile app notification effectiveness or with subscription-based products. |
| ![Participation](/help/assets/icons/AttributeParticipation.svg) | Participation | Gives 100% credit to all unique touch points. Since every touch point receives 100% credit, metric data typically adds up to more than 100%. If a dimension item appears multiple separate times leading up to a conversion, values are deduplicated to 100%. This attribution model is ideal in situations where you want to understand which touch points customers are exposed to the most. Media organizations typically use this model to calculate content velocity. Retail organizations typically use this model to understand which parts of their site are critical to conversion. |
| ![Same Touch](/help/assets/icons/AttributeSameTouch.svg) | Same Touch | Gives 100% credit to the same event where the conversion occurred. If a touch point does not happen on the same event as a conversion, It is bucketed under "None". This attribution model is sometimes equated to having no attribution model at all. It is valuable in scenarios where you do not want values from other events affecting how a metric gives credit to dimension items. Product or design teams can use this model to assess the effectiveness of a page where conversion happens. |
| ![U Shaped](/help/assets/icons/AttributeUShaped.svg) | U Shaped | Gives 40% credit to the first interaction, 40% credit to the last interaction, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 50% credit is given to both. This attribution model is best used in scenarios where you value the first and last interactions the most, but don't want to entirely dismiss additional interactions in between. |
| ![J Curve](/help/assets/icons/AttributeJCurve.svg) | J Curve | Gives 60% credit to the last interaction, 20% credit to the first interaction, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 75% credit is given to the last interaction, and 25% credit is given to the first. Similar to U-Shaped, this attribution model favors the first and last interactions, but more heavily favors the last interaction. |
| ![Inverse J](/help/assets/icons/AttributeInverseJ.svg) | Inverse J | Gives 60% credit to the first touch point, 20% credit to the last touch point, and divides the remaining 20% to any touch points in between. For conversions with a single touch point, 100% credit is given. For conversions with two touch points, 75% credit is given to the first interaction, and 25% credit is given to the last. Similar to J-Shaped, this attribution model favors the first and last interactions, but more heavily favors the first interaction. |
| ![Time Decay](/help/assets/icons/AttributeTimeDecay.svg) | Time Decay | Follows an exponential decay with a custom half-life parameter, where the default is 7 days. The weight of each channel depends on the amount of time that passed between the touch point initiation and the eventual conversion. The formula used to determine credit is `2^(-t/halflife)`, where `t` is the amount of time between a touch point and a conversion. All touch points are then normalized to 100%. Ideal for scenarios where you want to measure attribution against a specific and significant event. The longer a conversion happens after this event, the less credit is given. |
| ![Custom](/help/assets/icons/AttributeCustom.svg) | Custom | Allows you to specify the weights that you want to give to first touch point, last touch point, and any touch points in between. Values specified are normalized to 100% even if the custom numbers entered do not add to 100. For conversions with a single touch point, 100% credit is given. For interactions with two touch points, the middle parameter is ignored. The first and last touch points are then normalized to 100%, and credit is assigned accordingly. This model is ideal for analysts who want full control over their attribution model and have specific needs that other attribution models do not fulfill. |
| ![Algorithmic](/help/assets/icons/AttributeAlgorithmic.svg) | Algorithmic | Uses statistical techniques to dynamically determine the optimal allocation of credit for the selected metric. The algorithm used for attribution is based on the Harsanyi Dividend from cooperative game theory. The Harsanyi dividend is a generalization of the Shapley value solution (named after Lloyd Shapley, a Nobel Laureate economist) to distributing credit among players in a game with unequal contributions to the outcome.<br>At a high level, attribution is calculated as a coalition of players to which a surplus must be equitably distributed. Each coalition's surplus distribution is determined according to the surplus that was previously created by each subcoalition (or previously participating dimension items) recursively. For more details, see John Harsanyi's and Lloyd Shapley's original papers:<br>Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.<br>Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220. |

{style="table-layout:auto"}

## Atribution lookback window {#attribution-lookback-window}

A lookback window is the amount of time a conversion should look back to include touch points. If a dimension item is set outside of the lookback window, the value is not included in any attribution calculations.

* **14 Days**: Looks back up to 14 days from when the conversion happened.
* **30 Days**: Looks back up to 30 days from when the conversion happened.
* **60 Days**: Looks back up to 60 days from when the conversion happened.
* **90 Days**: Looks back up to 90 days from when the conversion happened.
* **Session**: Looks back up to the beginning of the session where a conversion happened. Session lookback windows respect the modified [Session timeout](/help/data-views/create-dataview.md#session-settings) in a data view.
* **Person (Reporting Window)**: Looks at all visits back up to the first of the month of the current date range. For example, if the report date range is September 15 - September 30, the person lookback date range includes September 1 - September 30. If you use this lookback window, you can occasionally see that dimension items are attributed to dates outside of your reporting window.
* **Custom Time:** Allows you to set a custom lookback window from when a conversion happened. You can specify the number of minutes, hours, days, weeks, months, or quarters. For example, if a conversion happened on February 20, a lookback window of five days would evaluate all dimension touchpoints from February 15 to February 20 in the attribution model.

## Attribution example {#attribution-example}

Consider the following example:

1. On September 15, a person arrives to your site through a paid search advertisement, then leaves.
2. On September 18, the person arrives to your site again through a social media link they got from a friend. They add several items to their cart, but do not purchase anything.
3. On September 24, your marketing team sends them an email with a coupon for some of the items in their cart. They apply the coupon, but visit several other sites to see if any other coupons are available. They find another through a display ad, then ultimately make a purchase for $50.

Depending on your lookback window and attribution model, channels receive different credit. The following are some notable examples:

* Using **first touch** and a **session lookback window**, attribution looks at only the third visit. Between email and display, email was first, so email gets 100% credit for the $50 purchase.
* Using **first touch** and a **person lookback window**, attribution looks at all three visits. Paid search was first, so it gets 100% credit for the $50 purchase.
* Using **linear** and a **session lookback window**, credit is divided between email and display. Both of these channels each get $25 credit.
* Using **linear** and a **person lookback window**, credit is divided between paid search, social, email, and display. Each channel gets $12.50 credit for this purchase.
* Using **J-shaped** and a **person lookback window**, credit is divided between paid search, social, email, and display.
  * 60% credit is given to display, for $30.
  * 20% credit is given to paid search, for $10.
  * The remaining 20% is divided between social and email, giving $5 to each.
* Using **Time Decay** and a **person lookback window**, credit is divided between paid search, social, email, and display. Using the default 7-day half-life:
  * Gap of zero days between display touch point and conversion. `2^(-0/7) = 1`
  * Gap of zero days between email touch point and conversion. `2^(-0/7) = 1`
  * Gap of six days between social touch point and conversion. `2^(-6/7) = 0.552`
  * Gap of nine days between paid search touch point and conversion. `2^(-9/7) = 0.41`
  * Normalizing these values results in the following:
    * Display: 33.8%, getting $16.88
    * Email: 33.8% getting $16.88
    * Social: 18.6%, getting $9.32
    * Paid Search: 13.8%, getting $6.92

Conversion events that typically have whole numbers are divided if credit belongs to more than one channel. For example, if two channels contribute to an order using a Linear attribution model, both channels get 0.5 of that order. These partial metrics are summed across all people then rounded to the nearest integer for reporting.

