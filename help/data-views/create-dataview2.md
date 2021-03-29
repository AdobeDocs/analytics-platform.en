---
title: How to create a new data view in Customer Journey Analytics.
description: Describes all the settings needed to create new data views.
---

# Create a new data view

Creating a data view involves either creating metrics and dimensions from schema elements or utilizing standard components. Creating metrics or dimensions gives you an enormous amount of flexibility. Previously, the assumption was that if you had datasets in Adobe Experience Platform, string fields were dimensions and numeric fields were metrics. In order to change any of these fields, you had to edit your schema in Platform. The data views UI now allows a more freeform definition of metrics and dimensions.

## Configure Data Views settings and containers

1. In Customer Journey Analytics, go to the  **Data Views**  tab.
2. Click  **Add**  to create a new data view and configure its settings.

![](assets/new-data-view.png)

| Setting | Description/Use case |
| --- | --- |
| Connection | This field links the data view to the connection that you established earlier, which contains one or more Adobe Experience Platform dataset/s.|
| Name | Giving the data view a name is mandatory. |
| Description | A detailed description is not mandatory but is recommended. |
| Time zone | Choose which time zone you want your data to be presented in. |
| Tags | Tags let you organize your data views into categories. |
| Containers | You can rename your containers here and this is how they will appear in any Workspace project that is based on this data view. Containers are used in filters and fallout/flow to define how broad or narrow the scope or context is. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/cja-filters/filters-overview.html?lang=en#filter-containers) |
|Person container name is… | Person (default). The Person container includes every visit and page view for visitors within a specified time frame. You can rename this to 'User' or any other term you prefer. |
| Session container name is… | Session (default). The Session container lets you identify page interactions, campaigns, or conversions for a specific session. You can rename this to 'Visit' or any other term you prefer. |
| Event container name is… | Event (default). The Event container defines which page events you would like to include or exclude from a filter. |

Next, you are going to create metrics and dimensions from schema elements.

## Create metrics and dimensions from schema elements

1. In [!UICONTROL Customer Journey Aalytics] > [!UICONTROL Data Views], click the [!UICONTROL Components] tab.

![](assets/components-tab.png)

You can see the [!UICONTROL Connection] at the top left, which contains the datasets, and its [!UICONTROL Schema fields] below.

1. Now drag a schema field, such as [!UICONTROL pageTitle], from the left rail into the Metrics or Dimensions section. 

   You can drag the same schema field into the dimensions or metrics well multiple times and configure the same dimension or metric in different ways. For example, from the **[!UICONTROL pageTitle]** field, you can create a dimension called "Product Pages", and another one "Error pages", etc. From the **[!UICONTROL pageTitle]**; field, you can also create metrics from a string value. For example,you could create one or more **[!UICONTROL Orders]** metrics with different attribution settings and different include/exclude values.

   ![](assets/components-tab-3.png)

1. Once you select the component, you see a number of settings appear on the right. Configure the component using the settings described below.

### Configure Component Settings

![](assets/component-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Component type] | Required. Allows you to change a component from Metric to Dimension or vice versa. |
| [!UICONTROL Component Name] | Required. Lets you specify the friendly name that will appear in Analysis Workspace. You can rename a component to give it a data-view-specific name. |
| [!UICONTROL Description] | Optional, but recommended, to provide information on the component for other users. |
| [!UICONTROL Tags] | Optional. Lets you tag the component with custom or out-of-the-box tags for easier searching/filtering in the Analysis Workspace UI. |
| [!UICONTROL Field Name] | The name of the schema field. |
| [!UICONTROL Dataset type] | Required. A non-editable field showing which dataset type (event, lookup, or profile) the component came from. |
| [!UICONTROL Dataset] | Required. A non-editable field showing which type of field the component came from (e.g. String, Integer, etc.). This field can contain multiple datasets, such as when you are combining multiple report suites. |
| [!UICONTROL Schema type] | Refers to whether the component is a string, integer, etc. |
| [!UICONTROL Component ID] | Required. The [CJA API](https://adobe.io/cja-apis/docs) uses this field to reference the component. You can click the edit icon and modify this component ID. However, changing this component ID breaks all existing Workspace projects that contain this component.<br>If you ever create another data view that uses a different field for a pageTitle dimension, you can rename it and make the dimension cross-data view compatible. |
| Path | Required. A non-editable field showing the schema path that the component came from. |
| Hide component in reporting | Default = off. Lets you curate the component out of the Data View when used in reporting. This does not impact permissions, just component curation. In other words, you can hide the component from non-Admins in reporting. Admins can still access it by clicking [!UICONTROL Show All Components] in an Analysis Workspace project. |

### Configure Format settings

Format settings are for metrics only.

![](assets/format-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Format] | Lets you specify the formatting of a metric, as Decimal, Time, Percent, or Currency. |
| [!UICONTROL Decimal Places] | Lets you specify the number of decimal places a metric should display. |
| [!UICONTROL Show upward trend as] | Lets you specify whether an upward trend on this metric should be considered good (green) or bad (red). |
| [!UICONTROL Currency] | This setting appears only if the selected metric format is [!UICONTROL Currency]. A list of currency options are available. Defaults to no currency. This allows you to represent revenue in the currency of your choice in reporting. This is not a currency conversion, just a UI formatting option. |

### Configure Attribution settings

![](assets/attribution-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Set attribution] | Lets you specify the attribution settings you want to apply to this metric by default when it is used. This default can be overridden in a Freeform Table or in a Calculated Metric. |
| [!UICONTROL Attribution model] | Lets you specify a default attribution model - only active when you turn on the [!UICONTROL Use Non-default attribution model] setting. Defaults to [!UICONTROL Last Touch]. Options are: Last Touch, First Touch, Linear, Participation, Same Touch, U-Shaped, J Curve, Inverse J, Time Decay, Custom, Algorithmic. Some of these options create additional fields that need to be filled out - like Custom or Time Decay. You can create multiple metrics using the same field - this means you can have one [!UICONTROL Last touch] revenue metric and one [!UICONTROL First Touch] revenue metric, but based on the same revenue field in the schema. |
| [!UICONTROL Lookback window] | Lets you specify a default lookback window to a metric - only active when you turn on the [!UICONTROL Use Non-default attribution model] setting. Options are: Person (Reporting Window), Session, Custom. When Custom is selected, we also give you the option to select any number of days/weeks/months/etc. (up to 90 days), just like Attribution IQ. You can have multiple metrics using the same schema field, but each with a separate lookback window. |

### Configure Include/Exclude Values settings

This setting allows you to modify the underlying data that you are reporting on, at query time. It is not the same as a filter (formerly called segment.) But filters will respect this new dimension, as will pathing and attribution.

For example, you could create a dimension out of the pageTitle field, but call it "error pages" and include any page that [!UICONTROL contains the phrase] "error".

![](assets/include-exclude.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Case sensitive] | Default = On. This setting is slightly different for Dimensions vs. Metrics.<ul><li>**Metric**: This setting applies only to the [!UICONTROL Include/Exclude Values] section. It allows you to say whether the filter you are applying should be case sensitive.</li><li>**Dimension** : This setting determines whether the data in this dimension should be aggregated in a case sensitive or case insensitive way. This changes the way reports/filters/attribution settings are run for a string field.</li></ul> |
| [!UICONTROL Match] | Lets you specify which values you would like to consider for reporting prior to attribution and segmentation (e.g., only use values containing the phrase "error"). You can specify: **[!UICONTROL If all criteria are met]**, or **[!UICONTROL If any criteria are met]**. |
| [!UICONTROL Criteria] | Lets you specify the match logic that should be applied to a specific filter rule.<ul><li>**String**: Contains the phrase, Contains any term, Contains all terms, Does not contain any term, Does not contain the phrase, Equals, Does not equal, Starts with, Ends wit</li><li>**Double/Integer**: equals, does not equal, is greater than, is less than, is greater than or equal to, is less than or equal to</li><li>**Date**: equals, does not equal, is later than, is before, occurs within</li></ul> |
| [!UICONTROL Match operand] | Lets you specify the match operand that the match operator should be applied to.<ul><li>**String**: Text field</li><li>**Double/Integer**: Text Field with up/down arrows for numeric values</li><li>**Date**: Day granularity selector (calendar)</li><li>**Date Time**: Date and time granularity selector</li></ul> |
| [!UICONTROL Add rule] | Lets you specify an additional match operator and operand. |

### Configure Behavior settings

![](assets/behavior-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Count values] | This lets you create a count of the number of times a Boolean field was set to `true`; as a metric. For example, the number of [!UICONTROL Page Views] where a Boolean field named `isPage` is set to `true`. |
| [!UICONTROL Count instances] | Lets you specify whether a numeric or date type field used as a metric should count the times it was set rather than the value itself.<br> If you want to add up the instances of a numeric field and want to simply add up the number of times a field was *set* rather than the actual value inside.<br>This is useful for creating an [!UICONTROL Orders] metric from a [!UICONTROL Revenue] field, for example. If revenue was set, then we want to count 1 single order rather than the numeric revenue amount. |

### Configure [!UICONTROL No Value Options] settings

[!UICONTROL No Value Options] settings are analogous to [!UICONTROL Unspecified] or [!UICONTROL None] values in reporting. In the data views UI, on a component-by-component basis, you can decide how you want these values to be treated in reporting. You can also rename [!UICONTROL No value] to something that better suits your environment, such as [!UICONTROL Null], [!UICONTROL Not set], or others.

Important: When you change this field to a custom value, the custom value will be treated as a legitimate string value. Therefore, if you enter the value &quot;Red&quot; into this field, any instances of the string &quot;Red&quot; appearing in the data itself will also roll under the same line item that you have specified.

Also note that whatever you specify in this field can be used for special UI treatment of the &quot;No Value&quot; line item in reporting as stated in the &quot;No Value Options&quot; setting. (Not sure what this means.)

![](assets/no-value-options.png)

| Setting | Description/Use case |
| --- | --- |
| If shown, call [!UICONTROL No value]… | This is where you can rename **[!UICONTROL No value]** to something else. |
| Don't show **[!UICONTROL No value]** by default | Does not show this value in reporting. |
| Show **[!UICONTROL No value]** by default | Does show this value in reporting. |
| Treat **[!UICONTROL No value]** as a value | For example, if you had Mobile device types as the dimension, you could rename the **[!UICONTROL No value]** item to "Desktop". |

### Configure Persistence settings

![](assets/persistence.png)

These settings are similar to eVar settings in traditional Adobe Analytics.

| Setting | Description/Use case |
| --- | --- |
| Set persistence | Toggle key |
| Allocation | Lets you specify the allocation model used on a dimension for persistence. Options are: Most recent, Original, Instance, All. If you want a value to persist (similar to eVars in traditional Analytics), this is where you'd set it. The only key difference is that the maximum persistence you can set is 90 days. Also, [!UICONTROL Never expire] is not an option. |
| Expiration | Lets you specify the persistence window for a dimension. Options are: Session (default), Person, Time, Metric.You might need to be able to expire the dimension on a purchase (such as internal search terms or other merchandising use cases). &quot;Metric&quot; lets you specify any of the defined metrics as the expiration for this dimension (e.g., a &quot;Purchase&quot; metric). |

### Configure Value Bucketing settings

 ![](assets/value-bucketing.png)

| Setting | Description/Use case |
| --- | --- |
| Bucket value | Allows you to create a bucketed version of a numeric dimension. This lets you report on buckets of revenue or other numeric values as a dimension in reporting. You can create up to 5 buckets. |
| Up to | Lets you specify the boundaries of the first numeric dimension bucket. This applies to numeric dimensions only. |
| Between and up to | Lets you specify the boundaries of subsequent numeric dimension buckets. |
| Add bucket | Lets you add another bucket to numeric dimension bucketing. |

## Use Standard components

Besides creating metrics and dimensions from schema elements, you can also use standard components in your data views.

Standard components are components that are not generated from dataset schema fields but are instead system generated. Some system components are required in any Data View to facilitate reporting capabilities in Analysis Workspace while other system components are optional.

![](RackMultipart20210326-4-374d6q_html_1100d8d54f8c09ac.png)

Required standard components

| Component Name | Dimension or Metric | Notes |
| --- | --- | --- |
| People | Metric | Formerly known as [!UICONTROL Unique Visitors] in traditional Analytics. This metric is based on the person ID specified in a Connection. |
| Sessions | Metric | Formerly known as [!UICONTROL Visits] in traditional Analytics. This metric is based on the sessionization settings specified below. |
| Events | Metric | Formerly known as [!UICONTROL Occurrences] in traditional Analytics. This metric represents the number of rows from all event datasets in a Connection. |
| Day | Dimension | |
| Week | Dimension | |
| Month | Dimension | |
| Quarter | Dimension | |
| Year | Dimension | |
| Hour | Dimension | |
| Minute | Dimension | |

## Optional Standard components

Some system components are required in any Data View to facilitate reporting capabilities in Analysis Workspace while the ones below are optional.

| Component Name | Dimension or Metric | Notes |
| --- | --- | --- |
| [!UICONTROL Session Starts] | Metric | This metric counts the number of events that were the first event of a session. When used in a filter definition (e.g. '[!UICONTROL Session Starts] exists'), it filters down to just the first event of every session. Note that this is different behavior from [!UICONTROL Entries] in that it always counts the first event of a session - not the first value present for a dimension in a session. |
| [!UICONTROL Session Ends] | Metric | This metric counts the number of events that were the last event of a session. Similar to [!UICONTROL Session Starts], it can also be used in a filter definition to filter things down to the last event of every session. Note that this is different behavior from [!UICONTROL Exits] in that it always counts the last event of a session - not the last value present for a dimension in a session. |
| [!UICONTROL Time Spent (seconds)] | Metric | The [!UICONTROL Time Spent] metric works similarly as in traditional Adobe Analytics - adding up the time between two different values for a dimension. However, using the Session Starts and Session Ends metric, customers can construct the [!UICONTROL Time Spent per Person] and [!UICONTROL Time Spent per Session] calculated metrics themselves (see OOTB filters and calc metrics below).  |
| [!UICONTROL Time Spent per Event] | Dimension | Functionally, this is actually just a bucketing of the above metric. We supply default buckets, but allow you to change the buckets to whatever you like. |
| Time Spent per Session | Dimension | |
| Time Spent per Person | Dimension | |
| Batch ID | Dimension | |
| Dataset ID | Dimension | |
