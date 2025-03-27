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

{{draft-aca}}

{{release-limited-testing}}

The guided configuration helps you to configure Content Analytics quickly and easily. The guided configuration uses a wizard to set up the requirements to configure Content Analytics automatically for your organization. In the **[!UICONTROL Configuration]** screen, you can either create a new configuration or edit an existing configuration. 

>[!IMPORTANT]
>
>You can only have one Content Analytics configuration per sandbox in your organization.

To access the Content Analytics configuration

* Select **[!UICONTROL Data Management]** > **[!UICONTROL Content Analytics]** from the main menu in Customer Journey Analytics.

In the **[!UICONTROL Content Analytics Configurations]** screen, you see a table of existing Content Analytics configurations. 

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

* Select **[!UICONTROL Create configuration]**. This action opens the [guided configuration wizard](#guided-configuration-wizard).

To edit an existing configuration:

* Select ![More](/help/assets/icons/More.svg) and then ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** for an existing Content Analytics configuration. This action opens the [guided configuration wizard](#guided-configuration-wizard).

## Guided configuration wizard

The guided configuration wizard consists of four sections ([Details](#details), [Data view](#data-view), [Experience capture & definition](#experience-capture-and-definition), and [Data collection](#data-collection)), each prompting you for details that are required to set up and configure Content Analytics properly. Complete each section before moving to the next section, as some settings in a section might depend on configuration values in earlier sections.

### Details {#onboarding-details}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_button"
>title="Details"
>abstract="Provide a name for the connection. In the **[!UICONTROL Data view]**, **[!UICONTROL Experience capture and definition]**, and **[!UICONTROL Data collection]** sections you provide more details to ensure that Content Analytics can be configured correctly."

>[!CONTEXTUALHELP]
>id="aca_onboarding_details_name_header"
>title="Details"
>abstract="This guide sets up the requirements needed to configure Content Analytics. Please provide a name for this configuration"    

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
>abstract="The selection of a new data view results in an update to that data view to include Content Analytics metrics and dimensions. If necessary, the associated connection is also updated to include Content Analytics datasets. The connection and data view that are currently configured for Content Analytics are not modified."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_current_cleanup_labels_dialog"
>title="Cleanup selected Data view"
>abstract="You have selected a Data view that is already provisioned for Content Analytics. That existing Content Analytics configuration is removed and the Data view is provisioned with your new configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_dataview_prev_cleanup_labels_dialog"
>title="Cleanup previous Data view"
>abstract="You have selected a new data view. The Content Analytics configuration for the previous selected Data view is removed."

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

   You can perform the following actions:

   * To search for a specific Data view, use the ![Search](/help/assets/icons/Search.svg) field.
   * To filter the list of available Data views, select ![Show filters](/help/assets/icons/Filter.svg). You can filter the list on [!UICONTROL Connection], [!UICONTROL Owner] and [!UICONTROL Sandbox].<br/>Use ![Hide](/help/assets/icons/Filter.svg) **[!UICONTROL Hide filters]** to hide the filter pane.
   * To define which columns to show in the table, select ![Column Settings](/help/assets/icons/ColumnSetting.svg). Select which columns to display in the **[!UICONTROL Customize table]** dialog and select **[!UICONTROL Apply]** to apply the changes.
  
1. Select ![SelectBox](/help/assets/icons/SelectBox.svg) the Data view that you want to use.
1. Select **[!UICONTROL Save]** to confirm the selected Data view. Select **[!UICONTROL Cancel]** to cancel.


In Customer Journey Analytics, a Data view is tied to a Customer Journey Analytics [Connection](/help/connections/overview.md). And a Connection is based on a sandbox within your organization. Once you save the configuration, **[!UICONTROL Sandbox]** is auto populated with the name of the sandbox, based on the selected Data view.


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
>abstract="Specify the parameters that determine how content is rendered on your website."

>[!CONTEXTUALHELP]
>id="aca_onboarding_experiencecapture_edit_button"
>title="Experience capture and definition"
>abstract="You can edit the settings in the Adobe Content Analytics extension in the Tags property that is associated with the current configuration."

<!-- markdownlint-enable MD034 -->

In this section, you can select to include Experiences in the data you collect with Content Analytics.  An experience is all text on a web page that is reproducible using the URL used by the initial user visiting that web page. 

By default, **[!UICONTROL Include experiences]** is turned off. When selected, you have to define for which URLs you want to include experiences.

Only consider to include experiences when the following is applicable:

* You can access the site content using public facing URLs only. Access to the site does not require personalized tokens, cookies or other mechanisms not available through the URL.
* The pages on the site must be reproducible using the page URL.

To include Experiences in a new or not implemented configuration:

![Content Analytics configuration Experience capture and definition](../assets/aca-configuration-experience.png)

1. Enable **[!UICONTROL Include experiences]**.
1. Optionally. specify the parameters for how content is rendered on your website. The parameters are zero or more combinations of a **[!UICONTROL Domain regular expression]** and **[!UICONTROL Query parameters]**.
   1. Enter a **[!UICONTROL Domain regular expression]**, for example `/^(?!.*\b(store|help|admin)\b)/`. Ensure you escape regular expressions, using `/`.
   1. Specify a comma separated list of **[!UICONTROL Query parameters,]** for example `outdoors, patio, kitchen`.
1. Select **[!UICONTROL Remove]** if you want to remove a combination of domain regular expression and query parameters.
1. Select **[!UICONTROL Add Regex]** if you want to add another combination of a regular expression and query parameters.

To edit existing or include new Experiences in an implemented configuration:

![Content Analytics configuration Experience capture and definition](../assets/aca-configuration-experience-edit.png)

* Toggle Include experiences to enable or disable experiences for the configuration.
* Select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** to edit the configuration of collecting Experiences in Content Analytics. You are redirected to the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) in the Tags property that is associated with the current configuration.




### Data collection {#onboarding-data-collection}

In this section, you configure how to collect your content analytics data.

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
>abstract="You can edit the settings for pages in the Adobe Content Analytics extension in the Tags property that is associated with the current configuration."

>[!CONTEXTUALHELP]
>id="aca_onboarding_datacollection_assets_edit_button"
>title="Data collection"
>abstract="You can edit the settings for assets in the Adobe Content Analytics extension in the Tags property that is associated with the current configuration."

<!-- markdownlint-enable MD034 -->

#### New configuration {#new-configuration}

In a new configuration, you need to define whether you want to use an existing Tags property or create a new Tags property. And you need to define the pages and assets you want to include or exclude, using regular expressions.

* To use an existing Tags property:

    ![Content Analytics Data Collection Existing Tag](../assets/aca-configuration-datacollection-existingtag.png)

    1. Select **[!UICONTROL Choose existing]**.
    2. Select an existing property from the **[!UICONTROL Tags property]** dropdown menu. You can start typing to search for and limit the available options.

* To create a new Tags property:

    ![Content Analytics Data Collection New Tag](../assets/aca-configuration-datacollection-newtag.png)

    1. Select **[!UICONTROL Create new]**.
    1. Specify a **[!UICONTROL Tags name]**, for example `ACA Test for Documentation`.
    1. Specify **[!UICONTROL Domains]**, for example, `example.com`.

* If you have selected to include experiences, indicate which pages should be included or excluded when collecting data for Content Analytics.

  * Specify a Regular expression string for **[!UICONTROL Pages to include / exclude]**. For example: `/^(?!.*documentation).*/` to exclude all documentation pages from Content Analytics. Ensure you escape regular expressions, using `/`.

* Indicate which assets should be included or excluded when collecting data for Content Analytics.

  * Specify a Regular expression string for **[!UICONTROL Assets to include / exclude]**. For example: `/^(?!.*(logo\.jpg|\.svg)).*$/` to exclude all logo JPEG and SVG images from Content Analytics. Ensure you escape regular expressions, using `/`.


#### Existing configuration {#existing-configuration}

For an existing configuration, you cannot edit the Tags property. You can, however, edit the pages and assets to include or exclude.

* To edit which pages should be included or excluded when collecting data for Content Analytics, select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** underneath **[!UICONTROL Experience]**. You are redirected to the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) that is associated with the Tags property for the current Content Analytics configuration. You can edit the regular expression to include or exclude pages. Ensure you [publish](#publish) your changes.

* To edit which assets should be included or excluded when collecting data for Content Analytics, select ![Edit](/help/assets/icons/Edit.svg) **[!UICONTROL Edit]** underneath **[!UICONTROL Asset]**. You are redirected to the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering) that is associated with the Tags property for the current Content Analytics configuration. You can edit the regular expression to include or exclude assets. Ensure you [publish](#publish) your changes.

### Summary {#summary}

Once you have provided all necessary details, a summary provides details on the artifacts that are created or modified.

* You see a **[!UICONTROL You're almost ready to implement _configuration name_ for Content Analytics]** summary when you implement a new configuration. 

* For existing implemented configurations, you see a **[!UICONTROL You have implemented _configuration name_ for Content Analytics]** summary.

![Content Analytics Configuration Summary](../assets/aca-configuration-summary.png)

### Actions {#actions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aca_onboarding_implementation_warning_dialog"
>title="Confirmation of implementation"
>abstract="If you select **[!UICONTROL Implement]**, you will configure Content Analytics based on the input you have provided in this workflow. Several settings are chosen by default based on what is generally useful for Content Analytics, but you (as the data controller) must review the settings of each artifact to confirm the settings are implemented in accordance with your privacy policy, contractual rights and obligations, and consent requirements under applicable law.<br/><br/>Note that no data will be collected until the Tags library associated with this configuration is published manually.<br/><br/>In order to derive attributes of images and text, Adobe retrieves the attributes using:<ol><li>The URL, captured at the time of the user's site visit, per the data collection settings you have configured, and</li><li>The URL where the image is hosted.</li></ol>You must not tag images that are hosted on third-party sites."

<!-- markdownlint-enable MD034 -->

When you have created or edited a configuration, the following actions are available.

* **[!UICONTROL Discard]**: All changes made as part of creating a new configuration or editing an existing configuration are discarded.
* **[!UICONTROL Save for later]**: Changes made to a new configuration or an existing, not yet implemented configuration are saved. You can revisit the configuration at a later stage to make further changes, or implement the configuration.
* **[!UICONTROL Implement]**: Settings for or changes made to a new configuration or existing, not yet implemented configuration are saved and implemented. The implementation consists of:
  
  * **[!UICONTROL Customer Journey Analytics]** configuration:
    * The selected Data view is updated to include Content Analytics dimension and metrics.
    * The Connection tied to the selected Data view is modified to include Content Analytics events and attributes datasets.
    * A Content Analytics reporting template is added to Workspace. 

    +++ Details
 
    Details are provided for the following scenarios:

    * **Tags** property exists **✓** or does not exist **✕**.
    * **Web SDK** extension for the Tags property exists **✓** or does not exist **✕**.
    * Adobe **Content Analytics** extension for the Tag property exists **✓** or does not exist **✕**.

    <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">Scenarios:</th>
      </tr>
      <tr>
        <th>
          <strong>Setting</strong>
        </th>
        <th>
          <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td>Report Template</td>
          <td colspan="4">A report template is available</td>
        </tr>
        <tr>
          <td>Data view</td>
          <td colspan="4">Modified/Created to have ACA dimensions and metrics</td>
        </tr>
        <tr>
          <td>Connection</td>
          <td colspan="4">Modified to include ACA datasets (ACA events, Asset attributes, Experience Attribute)</td>
        </tr>
      </tbody>
    </table>

    +++

  * **[!UICONTROL Adobe Experience Platform]** configuration:
    * The creation of schemas to model Content Analytics events, asset attributes, and (if configured) experience attributes.
    * The creation of datasets to collect Content Analytics events, asset attributes and (if configured) experience attributes.
    * The creation of a dataflow that uses the featurization service to generate and update content attributes from Content Analytics events.

    +++ Details

    Details are provided for the following scenarios:

    * **Tags** property exists **✓** or does not exist **✕**.
    * **Web SDK** extension for the Tags property exists **✓** or does not exist **✕**.
    * Adobe **Content Analytics** extension for the Tag property exists **✓** or does not exist **✕**.

    <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">Scenarios:</th>
      </tr>
      <tr>
        <th>
          <strong>Setting</strong>
        </th>
        <th>
          <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Events schema</strong></td>
        </tr>
        <tr>
          <td style="margin-left: 160.0px;">Name</td>
          <td>Content Analytics Events</td>
          <td>Content Analytics Events</td>
          <td>Content Analytics Events</td>
          <td>Content Analytics Events</td>
        </tr>
        <tr>
          <td>Description</td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
        </tr>
        <tr>
          <td>Profile enabled</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Events dataset</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td>Content Analytics Events</td>
          <td>Content Analytics Events</td>
          <td>Content Analytics Events</td>
          <td>Content Analytics Events</td>
        </tr>
        <tr>
          <td>Schema</td>
          <td>Content Analytics Event</td>
          <td>Content Analytics Event</td>
          <td>Content Analytics Event</td>
          <td>Content Analytics Event</td>
        </tr>
        <tr>
          <td>Description</td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
        </tr>
        <tr>
          <td>Tags</td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
        </tr>
        <tr>
          <td>System dataset</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>Profile enabled</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>
        <tr>
          <td>Data governance (DULE labels)</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Asset Attributes schema</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
        </tr>
        <tr>
          <td>Description</td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
        </tr>
        <tr>
          <td>Profile enabled</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Assets Attributes dataset</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
        </tr>
        <tr>
          <td>Schema</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
          <td>Content Analytics Asset Attributes</td>
        </tr>
        <tr>
          <td>Description</td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
        </tr>
        <tr>
          <td>Tags</td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
        </tr>
        <tr>
          <td>System dataset</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>Profile enabled</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>
        <tr>
          <td>Data governance (DULE labels)</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Experience Attributes schema</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
        </tr>
        <tr>
          <td>Description</td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
        </tr>
        <tr>
          <td>Profile enabled</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Experience Attributes dataset</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
        </tr>
        <tr>
          <td>Schema</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
          <td>Content Analytics Experience Attributes</td>
        </tr>
        <tr>
          <td>Description</td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
          <td><i>predetermined tbd</i></td>
        </tr>
        <tr>
          <td>Tags</td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
          <td><i>empty?</i></td>
        </tr>
        <tr>
          <td>System dataset</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
        <tr>
          <td>Profile enabled</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
          <td>No</td>
        </tr>
        <tr>
          <td>Data governance (DULE labels)</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
          <td>?</td>
        </tr>
      </tbody>
    </table>

    +++

  * **[!UICONTROL Data collection]** configuration:
    * The new or existing Tags property is configured to support Content Analytics data collection. This configuration implies the inclusion of the Adobe Content Analytics extension for Tags.
    * A datastream is created for Content Analytics events.
    * The Adobe Content Analytics extension is configured to ensure that Content Analytics events are sent to the datastream for Content Analytics. 
    * If the Web SDK is not configured for the Tags property, a new Web SDK configuration is created to send only Content Analytics events.
    * If the Web SDK is configured for this Tags property, no changes are made to the existing Web SDK configuration.

    +++ Details

    Details are provided for the following scenarios:

    * **Tags** property exists **✓** or does not exist **✕**.
    * **Web SDK** extension for the Tags property exists **✓** or does not exist **✕**.
    * Adobe **Content Analytics** extension for the Tag property exists **✓** or does not exist **✕**.

    <table style="table-layout:fixed">
      <tr>
        <th></th>
        <th colspan="4">Scenarios:</th>
      </tr>
      <tr>
        <th>
          <strong>Setting</strong>
        </th>
        <th>
          <strong>✓ Tags<br>✓ Web SDK<br/>✓ Content Analytics</strong>
        </th>
        <th>
          <strong>✓ Tags<br>✓ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✓Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
        <th>
          <strong>✕ Tags<br>✕ Web SDK<br/>✕ Content Analytics</strong>
        </th>
      </tr>
      <tbody>
        <tr>
          <td colspan="5"><strong><br/>Datastream</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td><i>existing value</i></td>
          <td>Content Analytics</td>
          <td>Content Analytics</td>
          <td>Content Analytics</td>
        </tr>
        <tr>
          <td>Description</td>
          <td><i>existing value</i></td>
          <td><i>predetermined</i></td>
          <td><i>predetermined</i></td>
          <td><i>predetermined</i></td>
        </tr>
        <tr>
          <td>Mapping schema</td>
          <td><i>existing value</i></td>
          <td><i>predetermined</i></td>
          <td><i>predetermined</i></td>
          <td><i>predetermined</i></td>
        </tr>
        <tr>
          <td>Geolocation and Network Lookup</td>
          <td><i>existing values</i></td>
          <td>All options off</td>
          <td>All options off</td>
          <td>All options off</td>
        </tr>
        <tr>
          <td>Device Lookup</td>
          <td><i>existing value</i></td>
          <td>Do not collect any device information</td>
          <td>Do not collect any device information</td>
          <td>Do not collect any device information</td>
        </tr>
        <tr>
          <td>IP Obfuscation</td>
          <td><i>existing value</i></td>
          <td>None</td>
          <td>None</td>
          <td>None</td>
        </tr>
        <tr>
          <td>First Party ID Cookie</td>
          <td><i>existing value</i></td>
          <td>Off</td>
          <td>Off</td>
          <td>Off</td>
        </tr>
        <tr>
          <td>Third Party ID Synch</td>
          <td><i>existing value</i></td>
          <td>Off</td>
          <td>Off</td>
          <td>Off</td>
        </tr>
        <tr>
          <td>Access Type</td>
          <td><i>existing value</i></td>
          <td>Mixed Authentication</td>
          <td>Mixed Authentication</td>
          <td>Mixed Authentication</td>
        </tr>
        <tr>
          <td>Media Analytics</td>
          <td><i>existing value</i></td>
          <td>Off</td>
          <td>Off</td>
          <td>Off</td>
        </tr>
            <tr>
          <td>Bot Detection</td>
          <td><i>existing value</i></td>
          <td>Off</td>
          <td>Off</td>
          <td>Off</td>
        </tr>
        <tr>
          <td>Mapping</td>
          <td><i>existing value</i></td>
          <td><i>user provided</i></td>
          <td><i>user provided</i></td>
          <td><i>user provided</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Tags property</strong><br/>An existing property or new property. The name and domain are provided by the user.</td>
        </tr>
        <tr>
          <td>Name</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td><i>user provided</i> (default "Content Analytics")</td>
        </tr>
        <tr>
          <td>Domain</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td ><i>predetermined</i></td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Tags library</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>
            <br/>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Web SDK Extension</strong></td>
        </tr>
        <tr>
          <td>Name</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Content Analytics - Web SDK</td>
          <td>Content Analytics - Web SDK</td>
        </tr>
        <tr>
          <td>IMS Org</td>
          <td><i>automatically populated</i></td>
          <td><i>automatically populated</i></td>
          <td><i>automatically populated</i></td>
          <td><i>automatically populated</i></td>
        </tr>
        <tr>
          <td>Edge Domain</td>
          <td><i>existing value<br/>Might require an update to match the AppMeasurement implementation</i></td>
          <td><i>existing value<br/>Might require an update to match the AppMeasurement implementation</i></td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
          <td>
            <a href="http://edge.adobedc.net">edge.adobedc.net</a>
          </td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Datastreams</strong></td>
        </tr>
        <tr>
          <td>Production</td>
          <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
          <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
          <td><i>user provided</i>?</td>
          <td><i>user provided</i>?</td>
        </tr>
        <tr>
          <td>Staging</td>
          <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
          <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
          <td><i>user provided</i>?</td>
          <td><i>user provided</i>?</td>
        </tr>
        <tr>
          <td>Development</td>
          <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
          <td><i>existing value<br/>Datastream override used to send to a different datastream</i></td>
          <td><i>user provided</i>?</td>
          <td><i>user provided</i>?</td>
        </tr>
        <tr>
          <td>Privacy</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>In?</td>
          <td>In?</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Identity</strong></td>
        </tr>
        <tr>
          <td>Migrate ECID</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Checked</td>
          <td>Checked</td>
        </tr>
        <tr>
          <td>Use third-party cookies</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Checked</td>
          <td>Checked</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Personalization</strong></td>
        </tr>
        <tr>
          <td>Migrate Target from at.js to Web SDK</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Unchecked</td>
          <td>Unchecked</td>
        </tr>
        <tr>
          <td>Enable personalization storage</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Unchecked</td>
          <td>Unchecked</td>
        </tr>
        <tr>
          <td>Auto click collection for Adobe Journey Optimizer</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Always</td>
          <td>Always</td>
        </tr>
        <tr>
          <td>Auto click collection for Adobe Target</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Never</td>
          <td>Never</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Data Collection</strong></td>
        </tr>
        <tr>
          <td>Collect internal links clicks</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Unchecked</td>
          <td>Unchecked</td>
        </tr>
        <tr>
          <td>Collect external link clicks</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Unchecked</td>
          <td>Unchecked</td>
        </tr>
        <tr>
          <td>Collect download links clicks</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Unchecked</td>
          <td>Unchecked</td>
        </tr>
        <tr>
          <td>When sending event data, automatically include</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>All default context information</td>
          <td>All default context information</td>
        </tr>
        <tr>
          <td>Streaming Media</td>
          <td><i>existing values</i></td>
          <td><i>existing values</i></td>
          <td>Blank values</td>
          <td>Blank values</td>
        </tr>
        <tr>
          <td>Datastream Configuration Overrides</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>Match datastream configuration</td>
          <td>Match datastream configuration</td>
        </tr>
        <tr>
          <td>Advanced Settings - Edge base path</td>
          <td><i>existing value</i></td>
          <td><i>existing value</i></td>
          <td>ee</td>
          <td>ee</td>
        </tr>
        <tr>
          <td colspan="5"><strong><br/>Content Analytics Extension</strong></td>
        </tr>
        <tr>
          <td>Datastreams</td>
          <td><i>existing value</i></td>
          <td><i>predetermined</i></td>
          <td><i>predetermined</i></td>
          <td><i>predetermined</i></td>
        </tr>
        <tr>
          <td>Experience Capturing & Definition</td>
          <td><i>existing value</i></td>
          <td><i>user provided</i></td>
          <td><i>user provided</i></td>
          <td><i>user provided</i></td>
        </tr>
        <tr>
          <td>Event Filtering</td>
          <td><i>existing value</i></td>
          <td><i>user provided</i></td>
          <td><i>user provided</i></td>
          <td><i>user provided</i></td>
        </tr>
      </tbody>
    </table>

    +++

* **[!UICONTROL Save]**: Changes made to an implemented configuration are saved and the implementation is updated.
* **[!UICONTROL Exit]**. Exits the guided configuration. All changes made to an implemented configuration are discarded.


## Publish {#publish}

To activate your Content Analytics configuration, you need to [manually](manual.md) publish the Tags property that is created after you selected **[!UICONTROL Implement]**.


>[!MORELIKETHIS]
>
>[Manual configuration](manual.md)
>
