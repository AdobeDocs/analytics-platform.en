---
title: CJA User Guide for Adobe Analytics users
description: What to consider from a user's perspective when your company moves data from Adobe Analytics to Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
---
# CJA User Guide for Adobe Analytics users

Your company is starting to employ Customer Journey Analytics. As a user who is familiar with Adobe Analytics, you already have a great head start. In working with Customer Journey Analytics, you will notice some similarities and some big differences. This page aims to explain those things that haven't changed, as well as some of the major differences. We will also tell you how you can get more information on new concepts, and further steps to make YOUR customer journey easier and more successful.

Several features in CJA have been renamed and re-architected, when compared to traditional Adobe Analytics, to align with industry standards. Some updated terminology includes segments, virtual report suites, classifications, customer attributes, and container names. Familiar concepts like eVars and props no longer exist, along with the limitations they imposed.

## What hasn't changed

A lot of what you are familiar with on the reporting side has not changed. 

* You can still use the power of [Analysis Workspace](/help/analysis-workspace/home.md) to analyze your data. Workspace works the same as it did in traditional Adobe Analytics.
* You also have the same version of [Adobe Analytics dashboards](/help/mobile-app/home.md) at your disposal. Dashboards (a.k.a. Mobile App) works the same as it did in traditional Adobe Analytics. 
* [Report Builder](/help/report-builder/report-buider-overview.md) has a new interface and now runs on PCs, Macs, and the web version of Excel. 

When it comes to reporting, **what's different** is that you have access to a lot more cross-channel data to analyze. Here is an example of some visualizations that include cross-channel data sources:

![multi-channel-visualizations](assets/cross-channel.png)

## New architecture {#architecture}

Customer Journey Analytics gets its data from Adobe Experience Platform. Experience Platform lets you centralize and standardize customer data and content from any system or channel and applies data science and machine learning to improve the design and delivery of personalized experiences. 

Customer data in the platform is stored as datasets, which consist of a schema and batches of data. For more detail on the platform, see [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Your CJA Admin has established [connections](/help/connections/create-connection.md) to data sets in Platform. They have then built [data views](/help/data-views/data-views.md) within those connections. Think of data views as similar to virtual report suites. Data views are the basis of reporting in Customer Journey Analytics. The concept of a report suite no longer exists.

## Connections

A connection lets your Analytics Admin integrate datasets from [!DNL Adobe Experience Platform] into [!UICONTROL Workspace]. In order to report on [!DNL Experience Platform] datasets, you first have to establish a connection between datasets in [!DNL Experience Platform] and [!UICONTROL Workspace].

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12&learn=on)

## Report suites {#report-suites}

Your report suite data can be brought into Experience Platform via the Adobe Analytics Source Connector or the Web SDK, if your organization is still on the Adobe Analytics platform and adding CJA/AEP. You will typically source datasets that are report-suite specific using the Analytics schema.

However, reports suites are no longer the basis for reporting in CJA - [data views](/help/data-views/data-views.md) are. See the section below for more information on data views.

Existing implementations from multiple data sets can be combined in Experience Platform. The connections and data views that are based on these data sets can combine data that previously existed in separate report suites. 

## (Virtual) report suites are now 'data views' {#data-views}

[!UICONTROL Data views] take the concept of virtual report suites as they exist today and expand it to [enable additional controls on the data](/help/data-views/create-dataview.md) made available by connections. This makes timezone and session time-out intervals configurable. You can also apply attribution and expiration properties for individual dimensions dynamically. Note that these are applied retroactively on all data.

**What you need to do**:

* Notice that in Workspace, the report suite selector that you are used to now lets you choose from the data views that your Admin has shared with you:

   ![data-view-selector](assets/data-views.png)

* Familiarize yourself with the many [use cases around data views](/help/data-views/data-views-usecases.md).

## eVars and props

[!UICONTROL eVars], [!UICONTROL props], and [!UICONTROL events] in the traditional Adobe Analytics sense no longer exist in [!UICONTROL Customer Journey Analytics]. You have unlimited schema elements (dimensions, metrics, list fields). So all of the attribution settings you used to apply during the data collection process are now applied at query time.

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

## Session and variable persistence settings

[!UICONTROL Customer Journey Analytics] applies all of these settings at report time, and these settings now live in [data views](/help/data-views/component-settings/persistence.md). Changes to these settings are now retroactive, and you can have multiple versions by using multiple data views! 

## Classifications are now 'Lookup datasets'

Lookup datasets are used to look up values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names. See [this use case](/help/use-cases/b2b.md) for an example.

## Customer attributes are now 'Profile datasets'

Profile datasets contain data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. For example, it allows you to upload CRM data about your customers. You can pick which Person ID you want to include. Each dataset defined in the [!DNL Experience Platform] has its own set of one or more Person IDs defined, such as Cookie ID, Stitched ID, User ID, Tracking Code, etc.

## Identities

CJA expands the concepts of identities beyond ECIDs to include any ID you want to use, including Customer ID, Cookie ID, Stitched ID, User ID, Tracking Code, and so on. Using a common namespace ID across datasets, or using [Cross-Channel Analytics](/help/connections/cca/overview.md) helps link people together across different datasets. Any user setting up a Workspace project in CJA needs to understand the IDs used across the datasets.

Here is a video that highlights the use of identities in Customer Journey Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Containers have been renamed 

You specify a container for [every data view you create](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=en#containers). 

* **Hit containers are now 'Event' containers**. The [!UICONTROL Person] container includes every session and event for visitors within the specified time frame. 
* **Visit containers are now 'Session' containers**. The [!UICONTROL Session] container lets you identify page interactions, campaigns, or conversions for a specific session.
* **Visitor containers are now [!UICONTROL Person] containers**. The [!UICONTROL Person] container includes every session and event for visitors within the specified time frame.

**What you need to do**:

You have the option to rename any container to fit your organization's needs.

## `Uniques Exceeded` limitations

[!UICONTROL Customer Journey Analytics] has no unique value limitations, so no need to worry about them!
