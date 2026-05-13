---
description: Learn how to create a project in Analysis Workspace.
title: Create Projects
feature: Workspace Basics
role: User
exl-id: cc3d3ac9-c31f-4a8d-999c-78590512b57c
TQID: https://experienceleague.adobe.com/DWTWJ2Bd9iEPO2awiiOLcUzUGPc-clZul3dNFcyWvxk
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: a8b1c240-f315-46e3-b813-f545c4279dd1
    internal-label: Workspace basics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: fa6ac035-8403-478b-9ce1-3fe29d211fca
    internal-label: Annotations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Create projects {#create-projects}


[Projects](/help/analysis-workspace/build-workspace-project/freeform-overview.md) in Analysis Workspace allow you to create and view business-critical analyses.  These analyses can be shared with stakeholders inside or outside your organization. 

1. In Customer Journey Analytics, select **[!UICONTROL Workspace]**.

1. Select **[!UICONTROL Projects]** in the left panel, then select **[!UICONTROL Create project]**.

1. Select **Blank Workspace project** to create your Workspace project using a browser.

   See [Blank mobile scorecard](/help/mobile-app/curator.md) for more information on how to create a Mobile scorecard project that you can share with other stakeholders using a mobile app. And see [Guided analysis](/help/guided-analysis/overview.md) for  more information on the various options available to create your guided analysis project.

1. Select [!UICONTROL **Create**].


Now that you have created a Blank Workspace project, ensure you are familiar with the [Analysis Workspace](/help/analysis-workspace/home.md) user interface. Once you are, you can build your project. To do so:

  ![Example project](assets/example-project.png)

* Add [panels](/help/analysis-workspace/c-panels/panels.md) to your project. For example, the **[!DNL Example Panel]** ➊.
   
* Add [visualizations](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md) to your panels. For example: 
  * **[!DNL Line Graph]** [Line](/help/analysis-workspace/visualizations/line.md) visualization ➋  
  * **[!DNL Countries]** [Freeform table](/help/analysis-workspace/visualizations/freeform-table/freeform-table.md) visualization ➌
* Add [components](/help/components/overview.md) to your visualizations. For example:
  * **[!DNL Store Country]** [dimension](/help/components/dimensions/overview.md) ➍
  * **[!DNL People]** [metric](/help/components/apply-create-metrics.md) ➎ 
  * **[!DNL Avg Order Value]** [calculated metric](/help/components/calc-metrics/calc-metr-overview.md) ➏ 
  * **[!DNL Mobile App Sessions]** [segment](/help/components/segments/seg-overview.md) ➐
  * **[!DNL Last Month]** [date range](/help/components/date-ranges/overview.md) ➑ 
  * **[!DNL Example]** [annotation](/help/components/annotations/overview.md) ➒


## Project Info & Settings {#project-info-settings}

>[!CONTEXTUALHELP]
>id="workspace_project_countrepeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/><br/>Note: this setting does not apply to Flow or Fallout visualizations."

>[!CONTEXTUALHELP]
>id="workspace_project_repeatinstances"
>title="Count repeat instances"
>abstract="Specifies whether repeat instances are counted in reports.<br/>Note: this setting does not apply to Flow or Fallout visualizations."


>[!CONTEXTUALHELP]
>id="workspace_project_commenting"
>title="Allow commenting"
>abstract="When enabled, a comments area is available in the right rail of the project in Analysis Workspace."


Project settings provides project-level information on the currently active project.

![The Project Info & Settings window.](./assets/projectinfo.png)

Settings include:

|  Setting  | Description  |
|---|---|
|  Project name  | The name given to the project. You can double-click the name to edit it.  |
|  Owner  | Project owner name  |
|  Last modified  | Date of last modification to the project.  |
|  Tags  |Lists any tags applied to a project for easier categorization.  |
|  Description  | A description is useful for clarifying the purpose of a project. You can double-click the description to edit it.  |
|  Count repeat instances  | Specify whether repeat instances are counted in reports. Note: this setting does not apply to Flow or Fallout visualizations.  |
| Show annotations | Specify whether annotations are shown for this project or not. |
|  [Project color palette](/help/analysis-workspace/build-workspace-project/color-palettes.md)  | You can change the categorical color palette used in Workspace, by choosing from out-of-the-box palettes that have been optimized for color blindness, or by specifying your custom palette. This feature affects many things in Workspace, including most visualizations.  |
| [View Density](/help/analysis-workspace/build-workspace-project/view-density.md) | Lets you see more data on the screen by reducing the vertical padding of the left panel, freeform tables and cohort tables. |
| Allow commenting | When this option is enabled, a comments area is available in the right rail of the project in Analysis Workspace. For more information, see [Add and manage comments in projects](/help/analysis-workspace/build-workspace-project/comment-projects.md).  |



