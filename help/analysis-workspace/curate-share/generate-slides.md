---
description: Learn how to generate presentations in pptx format from Workspace reports.
keywords: Analysis Workspace
title: Generate presentations from Workspace reports
feature: Curate and Share
role: User
hide: yes
hidefromtoc: yes
---
# Data storytelling: Generate slide presentations from Workspace reports {#generate-powerpoint}

Users with [the necessary permissions](#permission-requirements-to-generate-slides) can automatically generate .pptx presentations from Analysis Workspace projects. When generating slide presentations, Customer Journey Analytics automatically identifies key insights and converts them into stakeholder-ready slides. 

This functionality reduces the time and effort required to surface findings from your Workspace projects, and it allows you to quickly build executive narratives and communicate business impact.

## Generate a .pptx presentation based on a Workspace project

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="Included panels and visualizations"
>abstract="Choose the panels and visualizations that you want to include in the presentation. You can include up to 50 visualizations."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="Emphasized components"
>abstract="Choose up to 5 metrics and 5 dimensions from your visualizations that you want to emphasize in the presentation. The metrics you choose are shown in italics, dimensions are shown in bold, and dimension items are shown in a contrasting color."

<!-- markdownlint-enable MD034 -->

1. Go to the Workspace project that contains the data that you want to use as the basis of your presentation.

1. Select **[!UICONTROL Generate slides]** in the upper-right corner of the page.

   The Generate slides dialog displays.

   ![Generate slides dialog](assets/generate-slides.png)

1. Specify the following information:

   |Option | Description | 
   |---------|----------|
   | **[!UICONTROL Cover title]** | Specify a title for the presentation. This title appears on the title slide of the presentation.  | 
   | **[!UICONTROL Include presenter name]** | Specify the name of the presenter. This name appears on the title slide of the presentation, below the cover title. | 
   | **[!UICONTROL Panels and visualizations to include]** | Choose the panels and visualization you want to include in the presentation. You can include up to 50 visualizations.<p>Most panels and visualizations are supported. For information about unsupported panels and visualization, see [Unsupported project elements and features](#unsupported-project-elements-and-features).</p> | 
   | **[!UICONTROL Panel and visualization descriptions]** | | 
   | **[!UICONTROL Annotations]** | | 
   | **[!UICONTROL Emphasize components]** | Choose up to 5 metrics and 5 dimensions from your visualizations that you want to emphasize in the presentation.<p>When no emphasis is applied, components show in presentations as follows:<ul><li>**Metrics and dimensions:** Italics</li><li>**Dimension items:** Quotation marks</li></ul></p><p>When emphasis is applied, components show in presentations as follows:</p><ul><li>**Metrics and dimensions:** Italics and bold</li><li>**Dimension items:** Bold when the corresponding dimension is emphasized<p>A color is also applied to the dimension item when the dimension item is highlighted in the chart.</p></li></ul> | 

1. (Conditional) Select **[!UICONTROL Default theme]** if you want to quickly generate slides in fewer steps, and if a corporate theme is not required for your slide presentation. 

   Simply choose the color theme of your presentation by selecting the desired color.

   ![Generate slides with the default theme](assets/generate-slides-default-theme.png)

1. (Conditional) Select **[!UICONTROL Upload template]** if your slide presentation needs to match a corporate theme. This option requires more steps and that you upload a custom template. 

   ![Generate slides with a custom template](assets/generate-slides-upload-template.png)

   To use a custom template, we recommend that you:

   1. Download this blank template

   1. Apply your custom styles

   1. Re-upload the template without changing any master layout names

   Alternatively, you can upload a custom template directly. If you do, make sure that the uploaded file has master layouts with the following names: "Title_Slide", "Section_Divider", "Title_Text", "Title_Chart", "Title_Two_Content_Mixed", "Title_Three_Content_Mixed"

   .pptx and .potx files up to 25MB in size are supported.

1. Select **[!UICONTROL Export PPT]**.


## Edit slides from a previously generated presentation


## Download a generated .pptx presentation



## Permission requirements to generate slides

>[!AVAILABILITY]
>
>If your organization does not have access to this capability, please contact your Adobe account representative to learn more about licensing.
>
>This capability is enabled by default for all users in organizations who have the required licensing. 

Product profile administrators whose organizations have licensing to generate slides can disable access if needed.

In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL Data storytelling]** permission determines access to this capability. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL Data storytelling].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/RemoveCircle.svg) to remove **Data storytelling** from the **[!UICONTROL Included permission items]**.
   
      <!--add screenshot of permission in the admin console-->

   1. Select **[!UICONTROL Save]** to save the permissions.

For more information, see [User-level access](/help/technotes/access-control.md#user-level-access) in  [Access control](/help/technotes/access-control.md#access-control) for more information.

## Unsupported project elements and features {#unsupported}

The following Analysis Workspace elements and features used in a project aren't supported when generating slides:

* Attribution panel

  This panel shows as dimmed when the configuration options are displayed.
  
  All other panels can be included in slides that are generated from a Workspace project.

* Some visualizations

  Most visualizations can be included in slides that are generated from a Workspace project. However, the following visualizations cannot be included, and show as dimmed when the configuration options are displayed:

  * Cohort table

  * Journey canvas

  * Bullet

  * Combo

  * Scatter

  * Treemap

* Breakdowns

* Guided analyses


