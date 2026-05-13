---
title: Annotations Overview
description: Learn how to use annotations in Analysis Workspace.
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
role: User
TQID: https://experienceleague.adobe.com/GTQ6Q0saYtBvHM4Iva-lL3ifA9ERbONI9JQkOyaqSRA
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
  - id: cb6c7d24-631f-46e5-9e39-3a2705f73962
    internal-label: Calendar
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: fa6ac035-8403-478b-9ce1-3fe29d211fca
    internal-label: Annotations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Annotations overview

Annotations enable you to communicate contextual data nuances and insights effectively to other stakeholders in your organization. Annotations let you tie calendar events to specific dimensions and metrics. You can annotate a date or date range with known data issues, public holidays, campaign launches, etc. You can then graphically display events and see whether campaigns or other events have affected your site traffic, mobile app usage, revenue, or any other metric.

For example, you are sharing projects with your organization. If you had a major downfall in your offers being accepted, you could create a **Bad Offers** annotation and scope it for your whole data view. When your users view any datasets that included that date, they see the annotation within their projects, alongside their data.

![Line chart with annotation highlighted.](assets/annotation-example.png)

Annotations can apply to:

* A single date or a date range.

* Your entire dataset or specific metrics, dimensions, or segments.

* The project in which annotations are created (default) or all projects.

* The data view in which annotations are created (default), or all data views.

See [Create annotations](/help/components/annotations/create-annotations.md) for the various options available to create annotations. You then build, modify, and save annotations in the [Annotation builder](create-annotations.md#annotation-builder).

You use the [Annotations manager](manage-annotations.md) to manage annotations.

## Turn annotations on or off

Annotations can be turned on or off at several levels:

| Level | How to... |
|---|---|
| **Visualization** | Enable or disable ![Setting](/help/assets/icons/Setting.svg) > **[!UICONTROL Settings]** >  **[!UICONTROL Show annotations]**.<br/>![Enable disable annotations for a visualization](/help/components/annotations/assets/annotations-visualization.png) |
| **Project** | From a Workspace project menu, select **[!UICONTROL Project]** > **[!UICONTROL Project info & settings]** and enable or disable **[!UICONTROL Show annotations]**.<br/>![Enable disable annotations for a project](/help/components/annotations/assets/annotations-project.png) |
| **User** | From the **[!UICONTROL Components]** tab select **[!UICONTROL Preferences]**, or from a Workspace project menu, select **[!UICONTROL Project]** > **[!UICONTROL User preferences]**. <br/>In **[!UICONTROL Preferences]**, select **[!UICONTROL Projects & Analysis]**. From the left tab bar, select **[!UICONTROL Data]**. At the bottom, enable or disable **[!UICONTROL Show annotations]** underneath the **[!UICONTROL Freeform table]** heading.<br/>![Enable disable annotations for a user](/help/components/annotations/assets/annotations-user.png) |
