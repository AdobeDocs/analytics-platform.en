---
title: CJA User Guide for Adobe Analytics users
description: What to consider from a user's perspective when your company moves data from Adobe Analytics to Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
---

# CJA User Guide for Adobe Analytics users

>[!NOTE]
>
>This page is under construction.

Your company is starting employ Customer Journey Analytics. As a user who is familiar with Adobe Analytics, you already have great head start. In working with Customer Journey Analytics, you will notice some big differences and some similarities. This page aims to explain those things that haven't changed, as well as some of the major differences. We will also tell you how you can get more information on new concepts, and further steps to make YOUR customer journey easier and more successful.

## What hasn't changed

A lot of what you are familiar with on the reporting side has not changed. 

* You can still use the power of [Analysis Workspace](/help/analysis-workspace/home.md) to analyze your data. Workspace works the same as it did in traditional Adobe Analytics.
* You also have the same version of [Adobe Analytics dashboards](/help/mobile-app/home.md) at your disposal. Dashboards (a.k.a. Mobile App) works the same as it did in traditional Adobe Analytics. 
* [Report Builder](/help/report-builder/report-buider-overview.md) has a new interface and now runs on PCs, Macs, and the web version of Excel. 

When it comes to reporting, what's different is that you have access to a lot more cross-channel data to analyze. Here is an example of some visualizations that include cross-channel data sources:

![multi-channel-visualizations](assets/cross-channel.png)

## New architecture

Customer Journey Analytics gets its data from Adobe Experience Platform. Experience Platform lets you centralize and standardize customer data and content from any system or channel and applies data science and machine learning to improve the design and delivery of personalized experiences. 

Customer data in the platform is stored as datasets, which consist of a schema and batches of data. For more detail on the platform, see [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Your CJA Admin has established [connections](/help/connections/create-connection.md) to data sets in Platform. They have then built [data views](/help/data-views/data-views.md) within those connections. Think of data views as similar to virtual report suites. Data views are the basis of reporting in Customer Journey Analytics. The concept of a report suite no longer exists.

## New concepts and terminology

Several features in CJA have been renamed and re-architected, when compared to traditional Adobe Analytics, to align with industry standards. Some updated terminology includes segments, virtual report suites, classifications, customer attributes, and container names. Familiar concepts like eVars and props no longer exist, along with the limitations they imposed.

## (Virtual) report suites are now 'data views'

[!UICONTROL Data views] take the concept of virtual report suites as they exist today and expand it to [enable additional controls on the data](/help/data-views/create-dataview.md) made available by connections. This makes timezone and session time-out intervals configurable. You can also apply attribution and expiration properties for individual dimensions dynamically. Note that these are applied retroactively on all data.

**What you need to do**:

* Notice that in Workspace, the reports suite selector that you are used to now lets you choose from the data views that your Admin has shared with you:

   ![data-view-selector](assets/data-views.png)

* Familiarize yourself with the many [use cases around data views](/help/data-views/data-views-usecases.md).

## No more eVars and props

[!UICONTROL eVars], [!UICONTROL props], and [!UICONTROL events] in the traditional Adobe Analytics sense no longer exist in [!UICONTROL Customer Journey Analytics]. You have unlimited schema elements (dimensions, metrics, list fields). So all of the attribution settings you used to apply during the data collection process are now applied at query time. Your CJA Admin has create data views

**What you need to do**:

* Familiarize yourself with the many ways these schema elements can be used to drill down into your data.

## Segments are now 'Filters'

[!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses any AEP schema. This means none of the existing segments are compatible with [!UICONTROL Customer Journey Analytics]. In addition, "segments" have been renamed to "filters".

For the time being, you cannot share/publish [!UICONTROL filters] ([!UICONTROL segments]) from [!DNL Customer Journey Analytics] to Experience Platform Unified Profile, or other Experience Cloud applications. This functionality is currently being developed.

**What you need to do**:

* If you want to move existing Adobe Analytics segments to Customer Journey Analytics, view [this video](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-adobe-analytics-segments-to-customer-journey-analytics.html?lang=en).
* Otherwise, recreate the filters in Customer Journey Analytics.

## Calculated metrics

[!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses any AEP schema. This means none of the existing calculated metrics are compatible with [!UICONTROL Customer Journey Analytics]. 

**What you need to do**:

* If you want to move Adobe Analytics calculated metrics to Customer Journey Analytics, view [this video](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/moving-your-calculated-metrics-from-adobe-analytics-to-customer-journey-analytics.html?lang=en).
* Otherwise, recreate the calculated metrics in Customer Journey Analytics.


## Cross-report-suite data

Existing implementations from multiple data sets can be combined in Experience Platform. The connections and data views that are based on these data sets can combine data that previously existed in separate report suites. 

**What you need to do**:

## Session and variable persistence settings

[!UICONTROL Customer Journey Analytics] applies all of these settings at report time, and these settings now live in [data views](help/data-views/component-settings/persistence.md). Changes to these settings are now retroactive, and you can have multiple versions by using multiple data views! 

**What you need to do**:

## Classifications are now 'Lookup datasets'



## Customer attributes are now 'Profile datasets'


## Containers have been renamed 

You specify a container for [every data view you create](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers). 
* **Hit containers are now 'Event' containers**. The [!UICONTROL Person] container includes every session and event for visitors within the specified time frame. 
* **Visit containers are now 'Session' containers**. The [!UICONTROL Session] container lets you identify page interactions, campaigns, or conversions for a specific session.
* **Visitor containers are now [!UICONTROL Person] containers**. The [!UICONTROL Person] container includes every session and event for visitors within the specified time frame.

**What you need to do**:

You have the option to rename any container to fit your organization's needs.


## `Uniques Exceeded` limitations

[!UICONTROL Customer Journey Analytics] has no unique value limitations, so no need to worry about them!
