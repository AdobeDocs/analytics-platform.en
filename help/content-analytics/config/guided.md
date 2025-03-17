---
title: Content Analytics guided configuration
description: How to configure Content Analytics using an onboarding guided configuration
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: yes
hidefromtoc: yes
exl-id: 4aff664c-3cd9-4591-8122-6ebff10e4a76
---
# Content Analytics guided configuration

>[!WARNING]
>
>This article is a preliminary unofficial draft version of a forthcoming final version and is part of the Content Analytics documentation. All content is subject to change and no legal obligations whatsoever can be derived from the current version of this article.  
>

{{release-limited-testing}}

The guided configuration helps you to configure Content Analytics quickly and easily. The guided configuration uses a wizard to set up the requirements to configure Content Analytics automatically for your organization. In the **[!UICONTROL Configuration]** screen, you can either create a new configuration or edit an existing configuration. 

>[!IMPORTANT]
>
>You can only have one Content Analytics configuration per sandbox in your organization.


To access the Content Analytics configuration

* Select **[!UICONTROL Data Management]** > **[!UICONTROL Content Analytics]** from the main menu in Customer Journey Analytics.

In the Content Analytics Configuration screen, you see a table of existing Content Analytics configurations. 

![Content Analytics configurations](../assets/aca-configuration-table.png)
For each configuration, the following details are available:

| Column | Description |
|---|---|
| **[!UICONTROL Name]** | The name of the configuration. |
| **[!UICONTROL Created by]** | The technical account that created the configuration. |
| **[!UICONTROL Created on]** | The timestamp when the configuration was created. |
| **[!UICONTROL Modified on]** | The timestamp when the configuration was last modified. |
| **[!UICONTROL Sandbox]** | The sandbox within the organization in which Content Analytics is (planned to be) configured and implemented. |
| **[!UICONTROL Status]** | The status of the configuration. The status can be:<br/>![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Draft]**: The configuration is Saved for later, and not deployed.<br/>![StatusRed](/help/assets/icons/StatusRed.svg) **[!UICONTROL Failed]**: The configuration has failed. You need to edit the configuration and make the necessary changes.<br/>![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Complete]**: the configuration has been completed and implemented successfully. |

You can use ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) to customize the table. Select which columns to display in the **[!UICONTROL Customize table]** dialog and select **[!UICONTROL Apply]** to apply the changes.

From the Content Analytics **[!UICONTROL Configuration]** screen, you can create a new configuration or edit an existing configuration. 

To create a new configuration:

* Select **[!UICONTROL Create configuration]**. This action opens the guided configuration wizard.

To edit an existing configuration:

* Select ![More](/help/assets/icons/More.svg) and then ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** for an existing Content Analytics configuration. This action opens the guided configuration wizard.

## Guided configuration wizard

The guided configuration wizard consists of four sections ([Details](#details), [Data view](#data-view), [Experience capture & definition](#experience-capture-and-definition), and [Data collection](#data-collection)), each prompting you for details that are required to set up properly and configure Content Analytics. Complete each section before moving to the next section, as some settings in a section might depend on configuration values in earlier sections.

### Details {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Details"
>abstract="Provide a name for the connection. In the **[!UICONTROL Data view]**, **[!UICONTROL Experience capture and definition]**, and **[!UICONTROL Data collection]** sections you provide more details to ensure that Content Analytics can be configured correctly."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Details"
>abstract="This guide will set up the requirements needed to configure Content Analytics. Please provide a name for this configuration"    

<!-- markdownlint-enable MD034 -->

Each configuration requires a unique name. For example, `Example Content Analytics configuration`. The name is required to save or implement a configuration.

![Content Analytics configuration details](../assets/aca-configuration-details.png)


### Data view {#onboarding-data-view}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="ac_onboarding_dataview_button"
>title="Data view"
>abstract="For the configuration of Content Analytics you need to select an existing data view. So, you can merge your content analytics data with other data."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header"
>title="Data view"
>abstract="Select an existing data view from Customer Journey Analytics that you would like to merge your content analytics data with." 

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_header_alt"
>title="Data view"
>abstract="Select an existing data view from Customer Journey Analytics that you would like to merge your content analytics data with.<br/>"

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_change_dialog"
>title="New Data view"
>abstract="The selection of a new data view will result in an update to that data view to include Content Analytics metrics and dimensions. If necessary, the associated connection is also updated to include Content Analytics datasets. The connection and data view that are currently configured for Content Analytics are not modified."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_cleanup_labels_dialog"
>title="Cleanup current data view"
>abstract="When you select a new data view, all Content Analytics configuration for the current data view is removed."

<!-- markdownlint-enable MD034 -->

Your configuration requires the selection of a [Data view](/help/data-views/data-views.md). 

1. Select a Data view

   * To select a new Data view for a configuration, use ![Data](/help/assets/icons/Data.svg) **[!UICONTROL Select Data view]**. 

     ![Content Analytics configuration of a Data view](../assets/aca-configuration-dataview.png)

   * To modify a Data view for a configuration, select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]**.

     ![Content Analytics configuration of a Data view](../assets/aca-configuration-dataview-edit.png)
  

   In both scenarios, you see a **[!UICONTROL Data view]** dialog, where you can select a Data view for your configuration. 

   ![Content Analytics configuration of a Data view - Data views table](../assets/aca-configuration-dataview-dialog.png)
   
   For a new configuration, the list only shows Data views that are associated with sandboxes that do not have an active configuration.
  
   If you edit an existing configuration, the list only shows Data views available within the sandbox already associated with the existing configuration.

   * To search for a specific Data view, use the ![Search](/help/assets/icons/Search.svg) field.
   * To filter the list of available Data views, select ![Show filters](/help/assets/icons/Filter.svg). You can filter the list on Connection, Owner and Sandbox.<br/>Use ![Hide](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** to hide the filter pane.
   * To define which columns to show in the table, select ![Column Settings](/help/assets/icons/ColumnSetting.svg). Select which columns to display in the **[!UICONTROL Customize table]** dialog and select **[!UICONTROL Apply]** to apply the changes.
  
1. Select **[!UICONTROL Save]** to confirm the selected Data view. Select **[!UICONTROL Cancel]** to cancel.


A Data view is tied to a Customer Journey Analytics [Connection](/help/connections/overview.md). And a Connection is based on a sandbox within your organization. Once you save the configuration, **[!UICONTROL Sandbox]** is auto populated with the proper name of the sandbox, based on the selected Data view.


### Experience capture and definition {#onboarding-experiences} 

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_button"
>title="Experience capture and definition"
>abstract="You can select to include Experiences in the data you collect with Content Analytics. When selected, you have to define one or more combinations of a regex and query parameters to define for which URLs you want to include experiences."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_header"
>title="Experience capture and definition"
>abstract="Collect Experiences in Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiences_parameters_header"
>title="Experience capture and definition"
>abstract="Specify the parameters that determin how content is rendered on your website."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Experience capture and definition"
>abstract="You can edit the settings in the Adobe Content Analytics extension in the Tags property that is associated with the current configuration."

<!-- markdownlint-enable MD034 -->

In this section, you can select to include Experiences in the data you collect with Content Analytics.  An experience is all text on a web page that is reproducible using the URL used by the initial user visiting that web page. 

By default, **[!UICONTROL Include experiences]** is turned off. When selected, you have to define for which URLs you want to include experiences.

You should only consider to include experiences when the following is applicable:

* The content on the site is driven by a URL only.
* The pages on the site must be reproducible using the page URL.

To include Experiences in a new or not implemented configuration:

![Content Analytics configuration Experience capture and definition](../assets/aca-configuration-experience.png)

1. Enable **[!UICONTROL Include experiences]**.
1. Optionally. specify the parameters that determine how content is rendered on your website. The parameters are zero or more combinations of a **[!UICONTROL Domain regular expression]** and **[!UICONTROL Query parameters]**.
   1. Enter a **[!UICONTROL Domain regular expression]**, for example `/^(?!.*\b(store|help|admin)\b)/`. Ensure you escape regular expressions, using `/`.
   1. Specify a comma separated list of **[!UICONTROL Query parameters,]** for example `outdoors, patio, kitchen`.
1. Select **[!UICONTROL Remove]** if you want to remove a combination of domain regular expression and query parameters.
1. Select **[!UICONTROL Add Regex]** if you want to add another combination of a regular expression and query parameters.

To edit existing or include new Experiences in an implemented configuration:

![Content Analytics configuration Experience capture and definition](../assets/aca-configuration-experience-edit.png)

* Select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** to edit the configuration of collecting Experiences in Content Analytics. You are redirected to the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) in the Tags property that is associated with the current configuration.




### Data collection {#onboarding-data-collection}

In thia section, you configure how to collect your content analytics data.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_button"
>title="Data collection"
>abstract="Define which Tags property you want to use, or create a new one. And define the pages and assets that you want to include or exclude, using regular expressions."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_tag_header"
>title="Data collection"
>abstract="**Provide a Tags property**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_boldheader"
>title="Data collection"
>abstract="**Pages to include / exclude**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_pages_excluded_header"
>title="Data collection"
>abstract="Indicate which pages should be **included** or **excluded** when collecting data for Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_boldheader"
>title="Data collection"
>abstract="**Assets to include / exclude**"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_excluded_header"
>title="Data collection"
>abstract="Indicate which assets should be **included** or **excluded** when collecting data for Content Analytics"

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_experiences_edit_button"
>title="Data collection"
>abstract="You can edit the settings for pages in the Adobe Content Analytics extension in the Tags property that is  associated with the current configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Data collection"
>abstract="You can edit the settings for assets in the Adobe Content Analytics extension in the Tags property that is associated with the current configuration."

<!-- markdownlint-enable MD034 -->

#### New configuration {#new-configuration}

In a new configuration, you need to define whether you want to use an existing Tags property or create a new Tags property. And you need to define the pages and assets you want to include or exclude, using regular expressions.

* To use an existing Tags property:

    ![Content Analytics Data Collection Existing Tag](../assets/aca-configuration-datacollection-existingtag.png)

    1. Select **[!UICONTROL Existing]**.
    2. Select an existing property from the **[!UICONTROL Tags property]** dropdown menu. You can start typing to search for and limit the available options.

* To create a new Tags property:

    ![Content Analytics Data Collection New Tag](../assets/aca-configuration-datacollection-newtag.png)

    1. Select **[!UICONTROL Create new]**.
    2. Specify a **[!UICONTROL Tags name]**, for example `ACA Test`.
    3. Specify **[!UICONTROL Domains]**, for example, `example.com`. 

* If you have selected to include experiences, indicate which pages should be included or excluded when collecting data for Content Analytics.

  * Specify a regular expression for **[!UICONTROL Experience]**. For example: `/^(?!.*documentation).*/` to exclude all documentation pages from Content Analytics. Ensure you escape regular expressions, using `/`.

* Indicate which assets should be included or excluded when collecting data for Content Analytics.

  * Specify a regular expression for **[!UICONTROL Asset]**. For example: `/^(?!.*(logo\.jpg|\.svg)).*$/` to exclude all logo JPEG and SVG images from Content Analytics. Ensure you escape regular expressions, using `/`.


#### Existing configuration {#existing-configuration}

For an existing configuration, you cannot edit the Tags property. You can, however, edit the pages and assets to include or exclude.

* To edit which pages should be included or excluded when collecting data for Content Analytics, select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** underneath **[!UICONTROL Experience]**. You are redirected to the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) associated with the Tags property for the current Content Analytics configuration. You can edit the regular expression to include or exclude pages. Ensure you [publish](manual.md#publish) you changes.

* To edit which assets should be included or excluded when collecting data for Content Analytics, select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** underneath **[!UICONTROL Asset]**. You are redirected to the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) associated with the Tags property for the current Content Analytics configuration. You can edit the regular expression to include or exclude assets. Ensure you [publish](manual.md#publish) your changes.

### Summary {#summary}

Once you have provided all necessary details, a summary provides details on the artefacts that are created or modified.

* You see a **[!UICONTROL You're almost ready to implement _configuration name_ for Content Analytics]** summary when you implement a new configuration. 

* For existing implemented configurations, you see a **[!UICONTROL You have implemented _configuration name_ for Content Analytics]** summary.

![Content Analytics Configuration Summary](../assets/aca-configuration-summary.png)

### Actions {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmation of implementation"
>abstract="If you select **[!UICONTROL Implement]**, you will configure Content Analytics based on the input you have provided in this workflow. Several settings are chosen by default based on what is generally useful for Content Analytics, but you (as the data controller) must review the settings of each artefact to confirm the settings are implemented in accordance with your privacy policy, contractual rights and obligations, and consent requirements under applicable law.<br/><br/>Note that no data will be collected until the Tags library associated with this configuration is published manually.<br/><br/>In order to derive attributes of images and text, Adobe will retrieve the attributes using:<ol><li>The URL captured at the time of the users site visit, per the data collection settings you have configured, and</li><li>The URL where the image is hosted.</li></ol>You must not tag images that are hosted on third-party sites."

<!-- markdownlint-enable MD034 -->

When you have created or edited a configuration, the following actions are available.

* **[!UICONTROL Discard]**: All changes made as part of creating a new configuration or editing an existing configuration are discarded.
* **[!UICONTROL Save for later]**: Changes made to a new configuration or an existing, not yet implemented configuration are saved. You can revisit the configuration at a later stage to make further changes, or implement the configuration.
* **[!UICONTROL Implement]**: Settings for or changes made to a new configuration or existing, not yet implemented configuration are saved and implemented. The implementation consists of:
  * **[!UICONTROL Adobe Experience Platform]** configuration:
    * The creation of schemas to model Content Analytics events, asset attributes, and (if configured) experience attributes.
    * The creation of datasets to collect Content Analytics events, asset attributes and (if configured) experience attributes.
    * The creation of a dataflow that uses the featurization service to generate and update content attributes from Content Analytics events.
  * **[!UICONTROL Data collection]** configuration:
    * The new or existing Tags property is configured to support Content Analytics data collection. This configuration implies the inclusion of the Adobe Content Analytics extension for Tags.
    * A datastream is created for Content Analytics events.
    * The Adobe Content Analytics extension is configured to ensure that Content Analytics events are sent to the datastream for Content Analytics. 
    * If the Web SDK is not configured for the Tags property, a new Web SDK configuration is created to send only Content Analytics events.
    * If the Web SDK is configured for this Tags property, no changes are made to the existing Web SDK configuration.
  * **[!UICONTROL Customer Journey Analytics]** configuration:
    * The selected Data view is updated to include Content Analytics dimension and metrics.
    * The Connection tied to the selected Data view is modified to include Content Analytics event and attribute datasets.
    * A Content Analytics reporting template is added to Workspace. 
* **[!UICONTROL Save]**: Changes made to an implemented configuration are saved and the implementation is updated.
* **[!UICONTROL Exit]**. Exits the guided configuration. All changes made to an implemented configuration are discarded.


## Publish {#publish}

To activate your Content Analytics configuration you need to [manually](manual.md) publish the Tags property that is created after you selected **[!UICONTROL Implement]**, as part of the guided configuration wizard.

>[!MORELIKETHIS]
>
>[Manual configuration](manual.md)
>
