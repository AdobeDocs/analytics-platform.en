---
title: Value bucketing component settings
description: Combine numeric values in a dimension.
exl-id: 52f9abf6-69f1-47d0-86ab-57123bc178d5
solution: Customer Journey Analytics
---
# [!UICONTROL Value Bucketing] component settings

When creating or editing a data view, value bucketing allows you to combine numeric values based on a range. It is only available for dimensions using Integer or Double schema data types.

Value bucketing is valuable when you want to group ranges together instead of treating every unique number as a separate dimension item. For example, a bucket of 'Between 5 and up to 10' appears as a line item '5 to 10' in Analysis Workspace.

![Value bucketing](../assets/value-bucketing.png)

If you would like the flexibility of reporting on both a bucketed and non-bucketed dimension, drag two copies of the component into the available dimensions list. Enable bucketing on one dimension, and disable it on the other.

| Setting | Description |
| --- | --- |
| [!UICONTROL Bucket value] | A checkbox that lets you enable bucketing. |
| [!UICONTROL Less than] | The upper boundary of the first dimension bucket. |
| [!UICONTROL Including] [!UICONTROL and less than] | Boundaries of subsequent buckets. |
| [!UICONTROL Greater than or equal to] | The lower boundary of the last dimension bucket. |
| [!UICONTROL Add bucket] | Lets you add another bucket to numeric dimension bucketing. You can add up to 20 buckets in a single dimension. |
