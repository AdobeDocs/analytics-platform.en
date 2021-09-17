---
description: Use templates in Workspace and create custom templates.
title: Templates
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
exl-id: 464032a1-6dae-4df5-b4db-b277788e88c2
---
# Templates

>[!NOTE]
>
>You are viewing the documentation for Analysis Workspace in Customer Journey Analytics. Its feature set differs slightly from [Analysis Workspace in traditional Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html). [Learn more...](/help/getting-started/cja-aa.md)

You can choose whether to create a project from:

* **Blank project (default)**: For instructions, see [Create an Analysis Workspace Project](/help/analysis-workspace/home.md).
* **Standard template**: These templates are created by Adobe and ship with the product.
* **Custom template**: These templates can be created, shared, or deleted by users with admin rights or by non-admins, provided they have been granted the [!UICONTROL Analysis Workspace: Save as Template] permission in the Admin Console. [Learn more...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Create a custom template {#create-custom-template}

Users with admin rights can turn any project they create into a custom template. Here's how: 

1. Open the project.
1. Go to **[!UICONTROL Project]** > **[!UICONTROL Save As Template]**.

   ![](assets/save_project_template.png)

   The project will be saved under the current project name, followed by the word (Template) in parentheses. Admins can change this name by editing the template.

   >[!NOTE]
   >
   >By default, project templates are visible to everyone in your organization. You can organize them by applying tags. (Go to **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]** to edit tags and descriptions.)

### Actions you can perform on custom templates

   ![](assets/custom_templates.png)

| Action | Description |
|--- |--- |
|Edit template|Lets an admin edit the template by changing its data source, modifying components, visualizations, date ranges, etc.  To edit a custom template, either<ul><li>Bring up the list of custom templates in Analysis Workspace, select one, and click  Edit Template, or</li><li>In Analytics, navigate to  Components >  Projects, then filter on  Templates. Click the name of the template you want to edit.</li></ul>**Note:** After editing a template, depending on the situation, you have two options: Save, Save As. Here is how they differ:<ul><li>**Save:** Updates the custom template for all users. When someone else creates a project from this custom template, they will see the changes you have made.</li><li>**Save As:** Creates a copy of the custom template with your changes. (You can tell that you are in edit mode when the  Share >  Share Project menu item is disabled.)</li></ul>|
|Search on templates|In the Custom Templates dialog, click  Search Templates.|
|Sort templates|You can sort templates alphabetically, by relevance, and by creation date.  In the Custom Templates dialog, click Sort:.|
|Apply tags to template|Open the template and go to  Project >  Project Info & Settings. Click  Add Tags.|
|Modify template description|Open the template and go to  Project >  Project Info & Settings. Double-click the description and edit it.|


## Standard templates 

When you first open a Workspace, templates are available in the left rail. Analysis Workspace Templates cover common use cases. They are grouped by the vertical they belong to and are populated with different dimensions, filters, metrics and visualizations, depending on the data view you have selected.

You can use these pre-populated templates as they are or adapt them to your needs (by adding or replacing metrics or visualizations, for example) and save them under a new name.

>[!VIDEO](https://video.tv.adobe.com/v/23960)

*(2:46)*

Here are available templates and the questions that each template helps answer.

### Training

These standard templates walk you through common terminology and steps for building your first analysis in Workspace. They is available as a standard template in the New Project modal and replace the sample project that exists today for new users that do not have other projects in their list.

* **Training Tutorial - Internal Search Analysis**: The Internal Search tutorial helps you understand what your visitors are looking for on the website or app, but not finding. Analyzing this type of data can surface content optimization opportunities.

* **Training Tutorial - Marketing Analysis**: This tutorial shows you how to put together a marketing analysis for your executives, including what custom dimensions & metrics are important.

### Media

* **Audio Consumption**: Which content is being consumed the most and is engaging users? 
* **Recency - Frequency - Loyalty**: Who are my loyal readers?


### Retail

* **Campaign Performance:** What campaigns are driving the most revenue? 
* **Products:** Which products are performing the best?

### Web

* **Acquisition:** What are the top traffic drivers to my website? 
* **Content Consumption:** What are the top places people go on my site? 
* **Retention:** What types of users are likely to be loyal users of my site? 
* **Technology:** What technology are people using to access my site?

