---
title: Create or edit a data view
description: All settings that you can adjust to create or edit a data view.
exl-id: 02494ef6-cc32-43e8-84a4-6149e50b9d78
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Create or edit a data view

Creating a data view involves either creating metrics and dimensions from schema elements or using standard components. Most schema elements can be either a dimension or a metric depending on your business's requirements. Once you drag a schema element into a data view, options appear on the right where you can adjust how the dimension or metric operates in Customer Journey Analytics.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Create or edit a data view](https://video.tv.adobe.com/v/35110/?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


To create or edit a data view:

1. Log in to [Customer Journey Analytics](https://analytics.adobe.com) and select **[!UICONTROL Data views]**, optionally from **[!UICONTROL Data management]**, in the top menu.
1. To create a data view, select **[!UICONTROL Create new data view]**. Alternatively, you can select an existing data view from the list of data views to edit it.


## Configure {#configure}

To configure a new or existing data view:

>[!BEGINTABS]

>[!TAB Standard] 

![Configure data view](assets/dataview-configure.png)

>[!TAB B2B Edition]

![Configure data view B2B](assets/dataview-configure-b2b.png)

>[!ENDTABS]


1. Select the **[!UICONTROL Configure]** tab (if not already active).

   
1. Specify [!UICONTROL Settings], [!UICONTROL Container], and [!UICONTROL Calendar] details (see below). 
1. Select **[!UICONTROL Save and continue]** to continue configuring your new or existing data view. Select **[!UICONTROL Save]** to save the configuration for your existing data view.
   

### Settings {#configure-settings}


>[!CONTEXTUALHELP]
>id="dataview_externalid"
>title="External ID"
>abstract="Changing the External ID may impact how the data view name appears in external sources, such as business intelligence tools."


Provides overarching settings for the data view.

| Setting | Description |
| --- | --- |
| **[!UICONTROL Connection]** | This field links the data view to the connection that you established earlier, which contains one or more Adobe Experience Platform datasets. |
| **[!UICONTROL Name]** | Required. The name of the data view. This value appears in the top-right drop-down menu in Analysis Workspace. |
| **[!UICONTROL External ID]** | Required. The name of data view you can use in external sources, such as business intelligence tools. Default is `unspecified`. If you do not specify an external ID, the name will be generated from the Name of the data view, replacing spaces with underscores. |
| **[!UICONTROL Description]** | Optional. Adobe recommends a detailed description so that users understand why the data view exists and who it is designed for. |

{style="table-layout:auto"}

### Compatibility {#compatibility}


>[!CONTEXTUALHELP]
>id="dataview_dataviewsinadobejourneyoptimizer"
>title="Data views in Journey Optimizer"
>abstract="Customer Journey Analytics needs to use a connection and data view that are compatible with Adobe Journey Optimizer. By default, a connection and data view are automatically created for this purpose.<br/>Alternatively, you can enable this option to make this the default data view that is used in Adobe Journey Optimizer reporting. When enabled, all the necessary components required for Journey Optimizer are added to this data view, and all the necessary Journey Optimizer datasets are added to the connection associated with this data view."
>additional-url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/ajo#connection" text="Which components and datasets are added." 


Provides settings that are applicable when using Adobe Journey Optimizer in addition to Customer Journey Analytics.

This section is visible only for administrators who are provisioned with Journey Optimizer.

| Setting | Description |
| --- | --- |
| [!UICONTROL **Set as default data view in Adobe Journey Optimizer**] | This configuration option standardizes reporting across Journey Optimizer and Customer Journey Analytics. It also allows you to perform advanced analysis of your Adobe Journey Optimizer data in Customer Journey Analytics (by selecting ![Open](https://spectrum.adobe.com/static/icons/workflow_18/Smock_OpenInLight_18_N.svg) [!UICONTROL **Analyze in CJA**] while in Journey Optimizer).<p>To perform this type of analysis, Journey Optimizer needs access to a Customer Journey Analytics data view.<p>Enable this option to make this the default data view that is used in Journey Optimizer reporting for your sandbox.</p><p>This configuration option automatically:</p><ul><li>Configures all the required Journey Optimizer datasets in the associated connection in Customer Journey Analytics for use with Journey Optimizer.</li><li>Creates a set of Journey Optimizer metrics and dimension in the data view (including derived fields and calculated metrics). Context labels are automatically set on all of these metrics and dimensions.</li><li>Automatically enables the **[!UICONTROL Use in CJA]** option in the connection that is associated with this data view. (To learn more about this option, see [Use a Journey Optimizer connection in Customer Journey Analytics](/help/connections/manage-connections.md).)<p>If you manually disable this setting after it is enabled, the connection and any associated data views are reset to their default state. This can result in data changes in your reports.</p></li></ul><p><p>Consider the following when enabling this option: <ul><li>You can change the default data view at a later time, but doing so could alter your Journey Optimizer reporting data. If you choose to disable this option after it is enabled, you will be prompted to select a new default data view.</li><li>If you already made manual customizations to the the datasets, dimensions, or metrics in the Customer Journey Analytics data view, your manual customizations remain intact when enabling this configuration option. This option makes additional customizations that further standardize reporting across Journey Optimizer and Customer Journey Analytics. You can also make manual customizations after enabling this option.</li><li>When this option is selected, the connection associated with the data view cannot be deleted.</li></ul>See [Integrate Adobe Journey Optimizer with Adobe Customer Journey Analytics](/help/integrations/ajo.md) for more information. |

{style="table-layout:auto"}

### Containers

Designates the name of containers for the data view. Container names are frequently used in [segments](/help/components/segments/seg-overview.md#containers).

| Setting | Description |
| --- | --- |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Global Account container name]** | `Global Account` (default). The [!UICONTROL Global Account] container includes every session and event for globa accounts within the specified time frame. If your organization uses a different term, you can rename the container here. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Account container name]** | `Account` (default). The [!UICONTROL Account] container includes every session and event for accounts within the specified time frame. If your organization uses a different term, you can rename the container here. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Opportunity container name]** | `Opportunity` (default). The [!UICONTROL Opportunity] container includes every session and event for opportunities within the specified time frame. If your organization uses a different term, you can rename the container here. |
| [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL Buying group container name]** | `Buying Group` (default). The [!UICONTROL Buying group] container includes every session and event for buying groups within the specified time frame. If your organization uses a different term, you can rename the container here. |
| **[!UICONTROL Person container name]** | `Person` (default). The [!UICONTROL Person] container includes every session and event for persons within the specified time frame. If your organization uses a different term (for example, "Visitor" or "User"), you can rename the container here. |
| **[!UICONTROL Session container name]** | `Session` (default). The [!UICONTROL Session] container lets you identify page interactions, campaigns, or conversions for a specific session. You can rename this container to 'Visit' or any other term your organization prefers. |
| **[!UICONTROL Event container name]** | `Event` (default). The [!UICONTROL Event] container defines individual events in a dataset. If your organization uses a different term (for example, "Hits" or "Page Views"), you can rename the container here. |

{style="table-layout:auto"}

### AI Settings

Select **[!UICONTROL Enable for Data Insights Agent]** to enable the data view for the [Data Insights Agent](/help/data-analysis-ai.md). The Data Insights Agent is a generative AI conversation agent that is accessible from the AI Assistant in Customer Journey Analytics. It helps you quickly analyze your data with text prompts. The agent builds relevant visualizations in Analysis Workspace using components from your data view and using your actual data.
   

### Calendar

Indicates the calendar format that you want the data view to follow. You can have multiple data views based on the same [Connection](/help/connections/create-connection.md) and give them different calendar types or time zones. These data views can allow teams that use different calendar types to accommodate their respective needs with the same underlying data.

| Setting | Description |
| --- | --- |
| [!UICONTROL **Time zone**] | Choose which time zone that you want your data to be presented in. If you choose a time zone that operates on Daylight Savings Time, data is automatically adjusted to reflect that. In the spring when clocks adjust one hour ahead, a one-hour gap is present. In the fall when clocks adjust one hour behind, one hour is repeated during the DST shift. |
| [!UICONTROL **Calendar Type**] | Determine how weeks of the month are grouped.<br>**Gregorian:** Standard calendar format. Quarters are grouped by month.<br>**4-5-4 Retail:** A standardized 4-5-4 retail calendar. The first and last months of the quarter contain 4 weeks, while the second month of the quarter consists of 5 weeks.<br>**Custom (4-5-4):** Similar to the 4-5-4 calendar except you can choose the first day of the year and which year that the "extra" week occurs.<br>**Custom (4-4-5):** The first and second months of each quarter contain 4 weeks, while the last week of each quarter consists of 5 weeks.<br>**Custom (5-4-4):** The first month of each quarter consists of 5 weeks, while the second and third month of each quarter consists of 4 weeks. |
| [!UICONTROL **First month of the year**] and [!UICONTROL **First day of week**] | Visible for the Gregorian calendar type. Specify what month that you want the calendar year to start on, and what day you want each week to start on. |
| [!UICONTROL **First day of current year**] | Visible for custom calendar types. Specify what day of the year that you want the current year to start. The calendar automatically formats the first day of each week based on this value. |
| [!UICONTROL **Year in which the "extra" week occurs**] | With most 364-day calendars (52 weeks of 7 days each), each year accumulates leftover days until they add up to an extra week. This extra week is then added to the last month of that year. Specify which year that you want the extra week added to.<br><br/>**Extra weeks and leap years**<br/>When you select a custom **[!UICONTROL Calendar type]** (**[!UICONTROL Custom (4‑5‑4)]**, **[!UICONTROL Custom (4‑4‑5)]**, or **[!UICONTROL Custom (5‑4‑4)]**), leftover days accumulate each year until the days add up to a full extra week (7 days). That extra week is added to the year you select in **[!UICONTROL Year in which the "extra" week occurs]**.<br/><br/>Leap years are intentionally not shown in the **[!UICONTROL Year in which the "extra" week occurs]**. However, a leap year can still contain 53 weeks. To force a leap year to contain 53 weeks, select a non‑leap year from **[!UICONTROL Year in which the "extra" week occurs]** to ensure the cumulative date drift adds up to 7 days for your target leap year. For example: to have 53 weeks in 2024, select **[!UICONTROL 2019]**. From 2019 to 2024, the total date drift is 7 days (2020 (+2), 2021 (+1), 2022 (+1), 2023 (+1) and 2024 (+2)), which results in a 53rd week in 2024.<br/><br/>The selection for **[!UICONTROL First day of current year]** affects where the extra week lands. Confirm your configuration using the calendar preview. |

{style="table-layout:auto"}

## Components

Next, you can set a data view's components, which means you can create metrics and dimensions from schema elements. You can also use standard components.

>[!IMPORTANT]
>
>Up to 5,000 metrics and 5,000 dimensions can be added to a single data view.

1. Select the **[!UICONTROL Components]** tab.

   ![Components tab](assets/dataview-components.png)

   You can see the [!UICONTROL Connection] at the top left, which contains the datasets, and its [!UICONTROL Schema fields] below.  The components already included are standard components (system generated) required for all data views (like Events, People, Sessions metrics, and Minute, Quarter, Week dimensions). Adobe also applies the filter **[!UICONTROL Contains data]** and **[!UICONTROL is not deprecated]** by default, so that only Schema fields appear that contain data and which are not deprecated.

1. Search for a schema field using ![Search icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) **[!UICONTROL Search schema fields]** or find a field by moving into any of the dataset collections, like ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL Event datasets]** or ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL Lookup datasets]**. For event datasets, separate collections for ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL XDM fields]** and ![Folder](/help/assets/icons/Folder.svg) **[!UICONTROL Adhoc and relational fields]** are available.<br/>Alternatively, you can create a derived field using ![Data icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) **Create derived field** . See [Derived fields](./derived-fields/derived-fields.md) for more information.

1. When you found your specific schema field or defined your derived field, drag that field, such as ![Handle icon](https://spectrum.adobe.com/static/icons/workflow_22/Smock_DragHandle_22_N.svg) **[!UICONTROL Page Name]**, from the left rail into the **[!UICONTROL Metrics]** or **[!UICONTROL Dimensions]** section underneath **[!UICONTROL Included components]**.
   You can drag the same schema field into the dimensions or metrics sections multiple times and configure the same dimension or metric in different ways. For example, from the  pageName field, you can create a dimension titled `Product Pages`, and another one titled `Error pages`, by using different [Component settings](component-settings/overview.md) on the right.
   If you drag a schema field folder from the left rail, the fields in the folder are automatically sorted into the appropriate section. String fields end up in the [!UICONTROL Dimensions] section and numeric schema types end up in the [!UICONTROL Metrics] section. You can also click **[!UICONTROL Add all]** and all schema fields are added to their respective section.

1. Once you select a component, settings appear on the right.

   ![Dataview component selected](assets/dataview-component-pagename.png)

   Configure the component using [Component settings](component-settings/overview.md). Available component settings depend on if the component is a dimension/metric and the schema data type. Settings include:

   * [[!UICONTROL Attribution]](component-settings/attribution.md)
   * [[!UICONTROL Behavior]](component-settings/behavior.md)
   * [[!UICONTROL Format]](component-settings/format.md)
   * [[!UICONTROL Include exclude values]](component-settings/include-exclude-values.md)
   * [[!UICONTROL Metric deduplication]](component-settings/metric-deduplication.md)
   * [[!UICONTROL No value options]](component-settings/no-value-options.md)
   * [[!UICONTROL Persistence]](component-settings/persistence.md)
   * [[!UICONTROL Value bucketing]](component-settings/value-bucketing.md)

1. Select **[!UICONTROL Save and continue]** to continue configuring your new or existing data view. Select **[!UICONTROL Save]** to save the configuration for your existing data view.

### Duplicate metrics or dimensions

Duplicating metrics or dimensions and then modifying specific settings is an easy way to create multiple metrics or dimensions from a single schema field. Select the [!UICONTROL Duplicate] setting underneath the metric's or dimensions's name at the top right. Modify the new dimension or metric and save it under a more descriptive name.

### Filter schema fields or datasets

You can filter ![Filter icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) schema fields in the left rail by [!UICONTROL data type], [!UICONTROL datasets], [!UICONTROL data governance], and [!UICONTROL other] criteria ([!UICONTROL contains data], [!UICONTROL is identity], and [!UICONTROL is not deprecated]):

![Filter fields](assets/dataview-components-filter.png)

>[!TIP]
>
>If the components do not load properly in your data view and you see an error message instead, please refer to [Lack of permissions](../troubleshooting/lack-of-permissions.md) for a resolution.


### Included components {#included-components}

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_custom"
>title="Custom labels"
>abstract="In addition to the labels provided by Adobe, you can also define your own custom labels for your organization."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview" text="Data usage labels overview"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_contract"
>title="Contract labels"
>abstract="Contract (C) labels are used to categorize data that has contractual obligations or is related to your organization's data governance policies."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview" text="Data usage labels overview"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_identity"
>title="Identity labels"
>abstract="Identity (I) labels are used to categorize data that can identify or contact a specific person."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview" text="Data usage labels overview"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_sensitive"
>title="Sensitive labels"
>abstract="Sensitive (S) labels are used to categorize data that you, and your organization, consider sensitive."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview" text="Data usage labels overview"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_partnerecosystem"
>title="Partner ecosystem"
>abstract="Partner Ecosystem (P) labels are used to categorize data that is shared with third-party partners."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview" text="Data usage labels overview"

>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_policies"
>title="Policies"
>abstract="In order for data usage labels to effectively support data compliance, data usage policies must be implemented. Data usage policies are rules that describe the kinds of marketing actions that you are allowed to, or restricted from, performing on data within Experience Platform. The Policies filters apply the enabled policy to the Data View."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview" text="Data usage labels overview"


>[!CONTEXTUALHELP]
>id="dataview_includedcomponents_filter_datagovernance_responsibleengagement"
>title="Responsible engagement labels"
>abstract="Responsible engagement labels are used to support responsible engagement."
>additional-url="https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/overview" text="Data usage labels overview"


The **[!UICONTROL Included components]** contains the list of **[!UICONTROL Metrics]** and **[!UICONTROL Dimensions]** you configure for the data view. 

* To search for components, use ![Search](/help/assets/icons/Search.svg) **[!UICONTROL _Search components_]**.
* To filter the listed included components, select ![Filter](/help/assets/icons/Filter.svg).

  ![Includec components filter dialog](assets/dataview_includedcomponents_filter.png)

  In the **[!UICONTROL Filter field by]** dialog, you can filter on the following categories:

  * **[!UICONTROL Data type]** - You can select one or more of the following data types: [!UICONTROL String], [!UICONTROL Integer], [!UICONTROL Short], [!UICONTROL Boolean], [!UICONTROL Double], [!UICONTROL Byte], [!UICONTROL Long], [!UICONTROL Date], or [!UICONTROL Date-time].
  * **[!UICONTROL Datasets]** - Select one or more datasets.
  * **[!UICONTROL Data governance]**: Select one or more labels from the [!UICONTROL Custom labels], [!UICONTROL Contract labels], [!UICONTROL Identity labels], [!UICONTROL Sensitivity labels], P[!UICONTROL artner ecosystem] or [!UICONTROL Policies] subcategories.
  * **[!UICONTROL Other]** - Select one or more of the options [!UICONTROL Contains data], [!UICONTROL Is identity], or [!UICONTROL Is not deprecated].

  Select **[!UICONTROL Apply]** to apply the filters.



## Settings {#dataview-settings}

1. Select the **[!UICONTROL Settings]** tab.
   
   ![Data view settings](assets/dataview-settings.png)

1. Configure segments to apply to your entire data view. See [Settings (segments)](#settings-filters) below.
1. Configure session timeout and metrics. See [Session settings](#session-settings) below.

1. Select **[!UICONTROL Save and continue]** to continue configuring your new or existing data view. Select **[!UICONTROL Save]** to save the configuration for your existing data view.

### Settings (segments) {#segment-settings}

You can add segments that apply to an entire data view. This segment is applied to any report that you run in Workspace. Drag a segment from the components in the left rail to the **[!UICONTROL Add segments]** field.

### Session settings

Determine the time period of inactivity between events before a session expires and a new one is started. A time period is required. You can optionally also force a new session to start when an event contains a certain metric. See [Session settings](session-settings.md) for more details.

### Data preview

The data preview compares (for the various containers) the data of this data view with data of the connection. The preview percentage is based on the total number in the connection from the last 90 days.

If the preview is not loading, your connection could still be backfilling.

Once all desired settings are specified, click **[!UICONTROL Save and finish]**.
