---
title: Caveats
description: Caveats for the BI extension in various BI tools in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
exl-id: b6e8ebd9-4fda-41d1-ac37-ca869f5ee57c
---
# Caveats


Each of the supported BI tools has some caveats in working with the Customer Journey Analytics BI extension.

+++ BI tools

>[!BEGINTABS]

>[!TAB Power BI Desktop] 

* Power BI Desktop Advanced date range filtering is exclusive.  For your end date, you need to select one past the day you want to report on. For example, **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL and before]** `1/2/2023`.
* Power BI Desktop defaults to **[!UICONTROL Import]** when you create a connection. Please ensure you use **[!UICONTROL Direct Query]**.
* Power BI Desktop exposes data transformations through Power Query.  Power Query primarily works with Import type connections so a many transformations that you apply like date or string functions throw an error saying you need to switch to an Import type connection.  If you need to transform data at query time, you should use derived dimensions and metrics so Power BI doesn't need to do the transforms itself.
* Power BI Desktop does not understand how to handle date-time type columns so the **[!UICONTROL daterange*X*]** dimensions like **[!UICONTROL daterangehour]** and **[!UICONTROL daterangeminute]** are not supported.
* Power BI Desktop by default tries to make multiple connections using up more Query Service sessions.  Go in to the Power BI settings for your project and disable parallel queries.
* Power BI Desktop does all the sorting and limiting client-side. Power BI Desktop also has different semantics for top *X* filtering that includes tied values. So, you cannot create the same sorting and limiting as you can do in Analysis Workspace.
* Earlier versions of the Power BI Desktop October 2024 release break PostgreSQL data sources. Ensure you use the version mentioned in this article.

>[!TAB Tableau Desktop]

* Tableau Desktop Range of Dates filtering is exclusive. For your end date, you need to select one past the day you want to report on.
* By default, when you add a date or date-time dimension like **[!UICONTROL Daterangemonth]** to the rows of a sheet, Tableau Desktop wraps the field in a **[!UICONTROL YEAR()]** function.  To get what you want, you need to select that dimension and from the drop-down menu select the date function you want to use.  For example, change **[!UICONTROL Year]** to **[!UICONTROL Month]** when you are trying to use **[!UICONTROL Daterangemonth]**.
* Limiting results to the Top *X* is not obvious in Tableau Desktop. You can limit the results explicitly or using a calculated-field and the **[!UICONTROL INDEX()]** function.  Adding a Top *X* filter to a dimension generates complex SQL using an inner-join that is not supported.

>[!TAB Looker]

* Looker has a maximum number of connections per node setting that is required to be between 5-100.  You cannot set this value to 1.  This setting implies that a Looker connection always uses at a minimum 5 of the available Query Service sessions.
* Looker lets you create a project with a view based on a Customer Journey Analytics Data view. Looker then creates a model based on the dimensions and metrics, available in the Data view, using LookerML.  This Project View does not automatically update to match the source.  If you make changes or additions to the CJA Data View dimensions, metrics, calculated-metrics, or segments, then these changes do not automatically show up in Looker.  You have to manually update the Project View or create a new Project.
* Looker's user-experience on date or date-time fields like **[!UICONTROL Daterange Date]** or **[!UICONTROL Daterangeday Date]** is confusing. 
* Looker's date range is exclusive instead of inclusive.  The **[!UICONTROL until (before)]** is in gray so you may miss that aspect.  For your end day, you need to select one past the day you want to report on.
* Looker doesn't automatically treat your metrics as metrics.  When you select a metric, by default Looker tries to treat the metric as a dimension in the query.  To treat a metrics as a metric, you need to create a custom field as illustrated above. As a shortcut you can select **[!UICONTROL ⋮]**, select **[!UICONTROL Aggregate]**, and then select **[!UICONTROL Sum]**. 

>[!TAB Jupyter Notebook]

* The main caveat for Jupyter Notebook is that the tool does not a drag-and-drop user interface like other BI tools. You can create good visuals, but you have to write code to accomplish this.  

>[!TAB RStudio]

* R dplyr works with a flat schema so the **[!UICONTROL FLATTEN]** option is required.
* The main caveat for RStudio is that the tool does not a drag-and-drop user interface like other BI tools. You can create good visuals, but you have to write code to accomplish this.  

>[!ENDTABS]

+++
