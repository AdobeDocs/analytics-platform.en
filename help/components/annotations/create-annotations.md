---
title: Create Annotations
description: Learn how to create annotations in Analysis Workspace.
feature: Components
exl-id: 68fef9b3-dc47-4e56-bea6-d1c4c39fb51b
role: User, Admin
TQID: https://experienceleague.adobe.com/khuUFSkYrbrDsCBMZkzNwvZFsJ8MrN-FA9O7C-Q-Vg4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
  - id: fa6ac035-8403-478b-9ce1-3fe29d211fca
    internal-label: Annotations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Create annotations

By default, only administrators can create annotations. Users have rights to view annotations, similar to how users view other components (such as segments, calculated metrics, etc.).

However, administrators can give the **[!UICONTROL Annotation Creation]** permission for **[!UICONTROL Reporting Tools]** in **[!UICONTROL Edit permissions for CJA Workspace Access]** to users via the Admin Console. See [User-level access control](/help/technotes/access-control.md#user-level-access) for more information.

You can create an annotation in the following ways:

![Create an annotation](assets/create-annotation.png)

* **A**. In the main interface, select **[!UICONTROL Components]** and select **[!UICONTROL Annotations]**. Select ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] from the [[!UICONTROL Annotations] manager](/help/components/annotations/manage-annotations.md). 
* **B**. In a Workspace project, from the context menu in a visualization, select **[!UICONTROL Create annotation from selection]**.
* **C**. In a Workspace project, from the context menu in a line graph, select **[!UICONTROL Annotate Selection]**.
* **D**. In a Workspace project, select **[!UICONTROL Components]** from the menu, and select **[!UICONTROL Create annotation]**. 
* **E**.  In a Workspace project, use the shortcut **[!UICONTROL ctrl+shift+o]** (Windows) or **[!UICONTROL shift+command+o]** (macOS)

To define the annotation, you use the [[!UICONTROL Annotation builder]](#annotation-builder).

<!-- 
Should we really mention API here. If so, we can do it all over the place in the docs...
| **Use the [Customer Journey Analytics Annotations API](https://developer.adobe.com/cja-apis/docs/endpoints/annotations/)** | The Customer Journey Analytics Annotations APIs allow you to create, update, or retrieve annotations programmatically through Adobe Developer. These APIs use the same data and methods that Adobe uses inside the product UI. |
-->


## Annotation builder {#annotation-builder}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_details"
>title="Annotation details"
>abstract="Annotations enable you to communicate contextual data nuances and insights to your organization effectively. Annotations let you tie calendar events to specific dimensions and metrics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="components_annotations_scope"
>title="Scope"
>abstract="Scope allows you to customize what data is annotated. Calculated metrics and segments do not automatically inherit annotations applied to components used in their definitions. You may add new calculated metrics to the scope section of an existing annotation. New segments require a new annotation."

<!-- markdownlint-enable MD034 -->


The **[!UICONTROL Annotations builder]** dialog is used to create new or edit existing annotations. The dialog is titled **[!UICONTROL New annotation]** or **[!UICONTROL Edit annotation]** for annotations that you create or manage from the [[!UICONTROL Annotations] manager](/help/components/annotations/manage-annotations.md).


>[!BEGINTABS]

>[!TAB Annotation builder] 

![Annotation details window showing fields and options described in the next section.](assets/annotation-builder.png){zoomable="yes"}

>[!TAB  Edit annotation] 

![Annotation details window showing fields and options described in the next section.](assets/create-edit-annotation.png){zoomable="yes"}

>[!ENDTABS]

1. Specify the following details (![Required](/help/assets/icons/Required.svg) is required):

   | Element | Description |
   | --- | --- |
   | **[!UICONTROL Data view]** | You can select the data view for the annotation. The annotation you define is available as an annotation in the Workspace projects based on the selected data view. This selection is overruled when you have enabled [!UICONTROL Apply to all data views]. |
   | **[!UICONTROL Project-only Annotation]** | An info box to explain that the annotation you create is only visible in the Workspace project you are working on. Enable **[!UICONTROL Make this Annotation available to all your projects]**, to make the annotation visible to all your projects. This info box is only visible when you create an annotation from within a Workspace project. |
   | **[!UICONTROL Title]** ![Required](/help/assets/icons/Required.svg) | Name the annotation, for example, `Needs further investigation`. |
   | **[!UICONTROL Description]** | Provide a description for the annotation, for example, `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Tags]**|  Organize the annotation by creating or applying one or more tags. Start typing to find existing tags you can select. Or press **[!UICONTROL Enter]** to add a new tag. Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove a tag. |
   | **[!UICONTROL Applied date]** ![Required](/help/assets/icons/Required.svg) | Select the date or date range that needs to be present for the annotation to be visible. When you create an annotation using the shortcut, the annotation defaults to a date range for just the day. When you create an annotation using a selection in a visualization, the annotation defaults to the date range based on the date range for the panel the visualization belongs to. |
   | **[!UICONTROL Color]** | Apply a color to the annotation. The annotation appears in the project with the selected color. Color can be used to categorize annotations, such as public holidays, external events, tracking issues, etc. |
   | **[!UICONTROL Scope]** | Drag and drop metrics from the component panel that trigger the annotation. For example, People, Sessions and Events. Then drag and drop any dimensions or segments from the component panel that act as segments to determine whether to display or not to display the annotation. If you don't specify a scope, the annotation applies to all your data. <br/>You have two options:<ul><li>**[!UICONTROL Any of these metrics are present]**: Drag and drop up to 10 metrics that trigger the annotation to show.<br/>For example, the Revenue metric has stopped collecting data for a specific date range. Drag the Revenue metric into this box.</li><li>**[!UICONTROL With all of these segments]**: Drag and drop up to 10 dimensions or segments that segment whether the annotation shows.</li></ul><p><p>**Note:** Any annotation applied to a component that is then subsequently used as part of a calculated metric or segment definition does NOT automatically inherit the annotation. The desired calculated metric must also be added to the scope section to display the annotation. However, a new annotation should be created for any segment that you wish to annotate with the same information. For example, you apply an annotation to [!UICONTROL Orders] on a specific day. You then use [!UICONTROL Orders] in a calculated metric for the same date range. The new calculated metric does not automatically display the annotation for orders. Also add the calculated metric to the scope section for the annotation to display.|
   | **[!UICONTROL Apply to all data views]** | By default, the annotation applies to the originating data view. By checking this box, you can make the annotation apply to all data views in the company. |

   {style="table-layout:auto"}
   
1. Select 
   * **[!UICONTROL Save]** to save the annotation.
   * **[!UICONTROL Save As]** to save a copy of the annotation. 
   * **[!UICONTROL Delete]** to delete an annotation.
   * **[!UICONTROL Cancel]** to cancel any changes you made to an annotation or cancel the creation of a new annotation.
