---
title: Customer Journey Analytics Report Builder
description: Describes how to use Report Builder to pull Customer Journey Analytics data into Excel for recurring reporting.
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
---

# Report Builder

This article outlines how [!DNL Report Builder] can be used to implement the following [data export use case](overview.md):

* Ad hoc and recurring reporting

## Introduction

[!DNL Report Builder] [!DNL Report Builder] is a Microsoft Excel add-in that pulls Customer Journey Analytics data into data blocks in a workbook. Business users who are already familiar with Excel can build recurring reports without learning Analysis Workspace or SQL.

## More information

Each data block in [!DNL Report Builder] returns up to 50,000 rows. To retrieve more rows, use the **[!UICONTROL Page]** and **[!UICONTROL Rows]** options to pull data in sequential pages beyond the 50,000-row limit. See [Filter dimensions](/help/report-builder/filter-dimensions.md) for more information.

You can schedule a workbook for delivery by email or export it to a cloud destination, such as Amazon S3, Google Cloud Platform, or Azure. See [Schedule workbooks by sharing through email](/help/report-builder/schedule-reportbuilder.md) and [Schedule workbooks by exporting to cloud destinations](/help/report-builder/report-builder-export.md) for more information.

For an introduction to setting up and using [!DNL Report Builder], see [Report Builder overview](/help/report-builder/rb-overview.md).
