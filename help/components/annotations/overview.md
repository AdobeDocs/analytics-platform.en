---
title: Annotations overview
description: How to use annotations in Workspace.
role: User, Admin
solution: Customer Journey Analytics
feature: Components
exl-id: a87f6968-27a5-4595-be4f-0a38e03b9398
---
# Annotations overview

Annotations enable you to effectively communicate contextual data nuances and insights to your organization. They let you tie calendar events to specific dimensions/metrics. You can annotate a date or date range with known data issues, public holidays, campaign launches, etc. You can then graphically display events and see whether campaigns or other events have affected your site traffic, mobile app usage, revenue, or any other metric.

For example, let's say you are sharing projects with your organization. If you had a major spike in traffic due to a marketing campaign, you could create a "Campaign launch date" annotation and scope it for your whole data view. When your users view any datasets that included that date, they see the annotation within their projects, alongside their data.

![](assets/multi-day.png)

Keep this in mind:

* Annotations can be tied to a single date or to a date range.

* They can apply to your entire dataset or to specified metrics, dimensions, or filters.

* They can apply to the project in which they were created (default) or to all projects.

* They can apply to the data view in which they were created (default) or to all data views.

## Permissions

By default, only Admins can create annotations. Users have rights to view annotations like they do with other other Analytics components (such as filters, calculated metrics, etc.).

However, Admins can give the [!UICONTROL Annotation Creation] permission (Analytics Tools) to users via the [Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/analytics-tools.html).

## Turn annotations on or off {#annotations-on-off}

Annotations can be turned on or off at several levels:

* At the Visualization level: [!UICONTROL Visualization] settings > [!UICONTROL Show annotations]

* At the Project level: [!UICONTROL Project info & settings] > [!UICONTROL Show annotations]

* At the User level: [!UICONTROL Components] > [!UICONTROL User preferences] > [!UICONTROL Data] > [!UICONTROL Show annotations]

![](assets/show-ann.png)

![](assets/show-ann2.png)
