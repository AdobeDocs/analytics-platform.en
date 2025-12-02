---
description: Learn how to create and manage templates in Analysis Workspace.
title: Create And Manage Templates
feature: Workspace Basics
role: User, Admin
exl-id: 23cdf02f-56a1-4465-ae7f-b3a1bcad28af
---
# Create and manage templates

Administrators can create templates and save them for others in their login company to use.

People in the login company can use these company templates as described in [Use templates](/help/analysis-workspace/templates/use-templates.md). 

## Create a template {#create-templates}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="use-case-ajo-template"
>title="Use template in Journey Optimizer"
>abstract="When you use this template in Journey Optimizer, the data view that is set as the default data view in Adobe Journey Optimizer is used, regardless of the data view that is selected with this template in Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

To create a new template that can be used by people in your login company:

1. In Analysis Workspace, build a project to your desired state.

1. Select [!UICONTROL **Project**] > **[!UICONTROL Save as template…]**.
   
   ![Company template](assets/company-template-save.png)

1. Specify the following information in the [!UICONTROL Save as template] dialog box:
   
   | Field | Description |
   |---------|----------|
   | **[!UICONTROL Name]** | Provide a descriptive name for the template. |
   | **[!UICONTROL Description]** | Provide a short description for the template that describes its intended uses. |
   | **[!UICONTROL Why use this template]** | Provide a short explanation to inform people in the organization about how this template could be used. This explanation displays on the template's Preview page.  |
   | **[!UICONTROL Channels]** | Choose any applicable channels that apply to this template. You can select multiple channels: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]**, and **[!UICONTROL In-store]**.<p>The selections you choose determine where the template is displayed and which segments apply for users accessing it from the Organization Templates page.</p> |
   | **[!UICONTROL Use cases]** | Choose any use cases that apply to this template. You can select multiple use cases: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]**, and **[!UICONTROL Journey Optimizer]**. <p>The selections you choose determine the location of the template on the Organization Templates page. Users can navigate to the template or they can filter the list by use case. </p><p>**Note:** When you select the **[!UICONTROL Journey Optimizer]** option, the template is available for use in Adobe Journey Optimizer. In Journey Optimizer, a drop-down menu is available on the **[!UICONTROL Reports]** page, allowing users to select this template or the default template. For more information, see [Get started with the updated reporting experience](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) in the Journey Optimizer documentation.</p><p>Consider the following when selecting the Journey Optimizer option:</p><ul><li>This option is available only if Journey Optimizer data exists in the data view you are using in Customer Journey Analytics.</li><li>When you use this template in Journey Optimizer, the data view that is set as the default data view in Adobe Journey Optimizer is used, regardless of the data view that is selected with this template in Customer Journey Analytics. <br/>For more information about setting a data view as the default data view in Journey Optimizer, see [Compatibility](/help/data-views/create-dataview.md#compatibility) in [Create or edit a data view](/help/data-views/create-dataview.md).</li></ul>   |
   | **[!UICONTROL Journey Optimizer activity type]** | Choose the Journey Optimizer activity type to associate with this template: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]**, or **[!UICONTROL Subscriptions]**. <p>Leave this field blank if you want this template to be associated with all activity types.</p><p>This field displays only if **[!UICONTROL Journey Optimizer]** is selected in the **[!UICONTROL Use cases]** field.</p> |
   | **[!UICONTROL Journey Optimizer activity]** |  Choose the Journey Optimizer activity to associate with this template. <p>Leave this field blank if you want this template to be associated with all activities of the selected activity type.</p><p>This field displays only if **[!UICONTROL Journey Optimizer]** is selected in the **[!UICONTROL Use cases]** field.</p> |
   | **[!UICONTROL Tags]** | Specify any tags that you want to apply to the template. People can filter the list of templates by the tags you add. |

1. Select [!UICONTROL **Save as template**]. 

For information about how users can create a project based on a template, see [Create a project based on a template](/help/analysis-workspace/templates/use-templates.md#create-a-project-based-on-a-template) in [Use templates](/help/analysis-workspace/templates/use-templates.md).

## Edit or delete a template

Administrators can edit or delete company templates.

1. In Analysis Workspace, select the [!UICONTROL **Workspace**] tab, then under **[!UICONTROL Templates]** in the left rail, select **[!UICONTROL _login_company_name_ templates]**.

1. If you are viewing templates in a column view ![column view icon](assets/column-view-icon.png):

   1. Go to the template that you want to edit or delete, select the info icon next to the template name.

      ![Company template info](assets/company-template-info.png)

   1. Select **[!UICONTROL Preview]**.

   1. Select the More icon, then select **[!UICONTROL Edit]** or **[!UICONTROL Delete]**.

      ![Edit or delete template](assets/company-template-edit-delete.png)

1. If you are viewing templates in a card view ![card view icon](assets/card-view-icon.png):

   1. Locate the template that you want to edit or delete.

      ![Company template card view](assets/company-template-cards.png)

   1. Hover over the template, then select **[!UICONTROL Preview]**.

   1. Select the More icon, then select **[!UICONTROL Edit]** or **[!UICONTROL Delete]**.

      ![Company template card edit or delete](assets/company-template-card-edit-delete.png)

1. If you are editing a template, make any desired edits, then select [!UICONTROL **Project**] > **[!UICONTROL Save as template…]**.
   
   ![Company template](assets/company-template-save.png)

1. Specify the following information in the [!UICONTROL Save as template] dialog box:
   
   | Field | Description |
   |---------|----------|
   | **[!UICONTROL Name]** | Provide a descriptive name for the template. |
   | **[!UICONTROL Description]** | Provide a short description for the template that describes its intended uses. |
   | **[!UICONTROL Why use this template]** | Provide a short explanation to inform people in the organization about how this template could be used. This explanation displays on the template's Preview page.  |
   | **[!UICONTROL Channels]** | Choose any applicable channels that apply to this template. You can select multiple channels: **[!UICONTROL Web]**, **[!UICONTROL Mobile]**, **[!UICONTROL Cross-channel]**, **[!UICONTROL Call center]**, and **[!UICONTROL In-store]**. If no channels are selected, the template is included with all channels.<p>The selections you choose determine where the template is displayed and which filters apply for users accessing it from the Organization Templates page.</p> |
   | **[!UICONTROL Use cases]** | Choose any use cases that apply to this template. You can select multiple use cases: **[!UICONTROL Engagement]**, **[!UICONTROL Conversion]**, **[!UICONTROL Audience]**, **[!UICONTROL Acquisition]**, and **[!UICONTROL Journey Optimizer]**. <p>The selections you choose determine the location of the template on the Organization Templates page. Users can navigate to the template or they can filter the list by use case. </p><p>**Note:** When you select the **[!UICONTROL Journey Optimizer]** option, the template is available for use in Adobe Journey Optimizer. In Journey Optimizer, a drop-down menu is available on the **[!UICONTROL Reports]** page, allowing users to select this template or the default template. For more information, see [Get started with the updated reporting experience](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/channel-report/report-gs-cja) in the Journey Optimizer documentation.</p><p>Consider the following when selecting the Journey Optimizer option:</p><ul><li>This option is available only if Journey Optimizer data exists in the data view you are using in Customer Journey Analytics.</li><li>When you use this template in Journey Optimizer, the data view that is set as the default data view in Adobe Journey Optimizer is used, regardless of the data view that is selected with this template in Customer Journey Analytics. <br/>For more information about setting a data view as the default data view in Journey Optimizer, see [Compatibility](/help/data-views/create-dataview.md#compatibility) in [Create or edit a data view](/help/data-views/create-dataview.md).</li></ul>    |
   | **[!UICONTROL Journey Optimizer activity type]** | Choose the Journey Optimizer activity type to associate with this template: **[!UICONTROL Campaigns]**, **[!UICONTROL Journeys]**, **[!UICONTROL Landing pages]**, **[!UICONTROL Reports]**, or **[!UICONTROL Subscriptions]**. <p>Leave this field blank if you want this template to be associated with all activity types.</p><p>This field displays only if **[!UICONTROL Journey Optimizer]** is selected in the **[!UICONTROL Use cases]** field.</p> |
   | **[!UICONTROL Journey Optimizer activity]** |  Choose the Journey Optimizer activity to associate with this template. <p>Leave this field blank if you want this template to be associated with all activities of the selected activity type.</p><p>This field displays only if **[!UICONTROL Journey Optimizer]** is selected in the **[!UICONTROL Use cases]** field.</p> |
   | **[!UICONTROL Tags]** | Specify any tags that you want to apply to the template. People can filter the list of templates by the tags you add. |

1. Select [!UICONTROL **Save as template**]. 

## Rename, tag, or approve templates

Administrators can Rename, tag, and approve company templates.  

1. In Analysis Workspace, select the [!UICONTROL **Workspace**] tab, then select the **[!UICONTROL Projects tab]** in the left rail.

1. Select the filter icon to filter the list of projects.

1. In the filter rail, select **[!UICONTROL Other filters]** and then select **[!UICONTROL Company templates]**. 
    
   A list of the company templates are displayed. All regular projects, unless they're pinned, are not displayed.

   Company templates can be identified by the ![templates icon](https://spectrum.adobe.com/static/icons/workflow_18/Smock_FileTemplate_18_N.svg) that precedes the template name. 

   ![Display company templates filters](assets/company-templates-filter.png)

1. Click the **...** elilpsis icon next to a template to view the available options. 

   ![Company template actions](assets/company-templates-actions.png)

1. Select **[!UICONTROL Rename]**, **[!UICONTROL Tag]**, or **[!UICONTROL Approve]**.

   You can also delete a template, or you can delete a template as described in [Edit or delete templates](#edit-or-delete-templates).

1. (Optional) To return to the regular view, in the filter rail, deselect **[!UICONTROL Company templates]**.

## Add missing components to the data view for a given template

By default, some templates provided by Adobe can't be used because they contain components that are not in your data view. 

For each missing component, a matching context label is available in your data view. You need to either add the matching context label to a component that is already in your data view, or you need to add a new component to your data view and add the context label to it. 

To add missing components to a template: 

1. In Analysis Workspace, select the [!UICONTROL **Workspace**] tab, then under **[!UICONTROL Templates]** in the left rail, select **[!UICONTROL Adobe templates]**.

1. Select the filter icon to filter the list of templates.
   
1. Select **[!UICONTROL Not ready for use]** to show templates that require components that are not in your data view.

      ![Use a template that is missing components](assets/template-not-ready.png)

1. Locate a template that is not yet ready to use with your data view.

1. Do either of the following:

   * **If you are viewing templates in a column view** ![column view icon](assets/column-view-icon.png):

     1. Go to the template that is not yet ready to use with your data view, then select the info icon next to the template name.

        ![Company template info](assets/company-template-info.png)

     1. Select **[!UICONTROL Preview]**.

         ![Template preview page](assets/template-preview.png)

   * **If you are viewing templates in a card view** ![card view icon](assets/card-view-icon.png):

     1. Locate the template that is not yet ready to use with your data view.

        ![Company template card view](assets/company-template-cards.png)
   
     1. Hover over the template, then select **[!UICONTROL Preview]**.

        ![Template preview page](assets/template-preview.png)

1. In the **[!UICONTROL Missing components]** section, a list of components that are missing from the data view are displayed. Select **[!UICONTROL Add these components to your data view]**.

   The configuration page for the data view is displayed in a new tab. 

1. Select the **[!UICONTROL Components]** tab for the data view.

   ![Data view components tab](assets/template-dataview.png)

1. For each component that was listed as missing from the template, do either of the following on the **[!UICONTROL Components]** tab:

   * In the **[!UICONTROL Included components]** section, select a component that is already included in the data view that you want to use for the missing component. 

   * Add a new component to the data view that you want to use for the missing component, then select the component.
   
     To add a new component to the data view, search the list of schema fields, then drag it into the **[!UICONTROL Included components]** section.

1. With the component selected, locate the **[!UICONTROL Context labels]** drop-down menu in the right column.

   ![Data view components tab](assets/template-dataview-context-label.png)

1. In the **[!UICONTROL Context labels]** drop-down menu, select the context label that has the same name as the missing component.

1. Select **[!UICONTROL Save and continue]**.

1. For each missing component, repeat the process of adding the matching context label to a component in the data view.
      

## Access a company template

Like with templates that are provided by Adobe, users in the organization can access templates that administrators create. 

For information about how to access a company template, see [Access and run a template](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) in [Use templates](/help/analysis-workspace/templates/use-templates.md).

## Hide the Templates tab 

Administrators can hide the Templates tab for all users within their organization.

1. Go to **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Preferences]** > **[!UICONTROL Company]**.
1. Select the option to **[!UICONTROL Hide Templates tab]**.
