---
title: View annotations
description: How to view annotations in Workspace.
role: User
feature: Components
exl-id: c0e4fb37-b20c-463c-b29a-310ca3adb2c7
---
# View annotations

Annotations manifest slightly differently, depending on whether they span a single day or a date range.

## View annotations in Line charts or Tables

| Date | Appearance |
| --- | --- |
| **Single day** |   ![LIne chart visualization with highlighted annotation](assets/single-day.png)<p>When you hover over the annotation, you can see its details, you can edit it by selecting the pen icon, or you can delete it:<p> ![Annotations details with the option to edit or delete the annotation.](assets/hover.png) |
| **Date range** |  The icon changes and when you hover over it, the date range appears.<p>![Date range annotation icon](assets/multi-day.png)<p>When you select it in the line chart, the annotation metadata appear, and you can edit or delete it:![](assets/multi-hover.png)<p>In a table, an icon appears on every date in the date range.<p>![](assets/multi-day-table.png)|
| **Overlapping annotations** | On days that have more than one annotation tied to them, the icon appears in a grey color.<p>![Details for overlapping annotations  ](assets/grey.png)<p>When you hover over the grey icon, all overlapping annotations appear:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## View annotations in a .pdf file

Since you cannot hover over icons in a .pdf file, this file (after export) provides notes of explanations at the bottom of a panel. Here is an example:

![Highlighted view of a .pdf file showing explanations of annotations.](assets/ann-pdf.png)

## View annotations with non-trended data

Sometimes annotation are shown with non-trended data, but tied to a specific dimension. In that case, they appear only in a summary annotation in the bottom right corner. Here is an example:

![](assets/non-date.png)

The summary chart appears in all visualization types in the corner, not just in non-trended freeform tables and summary numbers. It also appears in visualizations like [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort], and so on.

![Summary chart in visualizations](assets/ann-summary.png)
