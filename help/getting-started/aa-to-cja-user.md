---
title: CJA User Guide for Adobe Analytics users
description: What to consider from a user's perspective when your company moves data from Adobe Analytics to Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: e4762cca-b2da-422b-b48f-2a5fec14c97f
---
# CJA User Guide for Adobe Analytics users

If your organization is starting to employ Customer Journey Analytics (CJA), you may notice some similarities and differences between traditional Analytics and CJA. This page aims to explain those differences to help acclimate your organization to the new implementation and reporting workflow. This page also provides additional resources on new concepts, and further steps to make your journey as an analyst easier and more successful.

Several features in CJA are renamed and redesigned to align with industry standards. Some updated terminology includes segments, virtual report suites, classifications, customer attributes, and container names. The limitations of eVars and props no longer exist, in favor of flexible custom dimensions and metrics.

## What hasn't changed

Much of what you are familiar with on the reporting side has not changed.

* You can still use the power of [Analysis Workspace](/help/analysis-workspace/home.md) to analyze your data. Workspace operates the same as it does in traditional Adobe Analytics.
* The same version of [Adobe Analytics dashboards](/help/mobile-app/home.md) is available, and works similarly between CJA and traditional Analytics.
* [Report Builder](/help/report-builder/report-buider-overview.md) has a new interface and runs on MS Windows, MacOS, and the web version of Excel. (Before this version of Report Builder, you couldn’t use in on Mac unless you ran it on VMware.) This version doesn’t support traditional AA data request yet.

## Changes to reporting

You have access to a lot more cross-channel data to analyze. For example, you can create a workspace project that analyzes performance of multiple channels, provided these datasets are ingested by your organization and included in data views used by CJA (see "Changes to data architecture" below).

![multi-channel-visualizations](assets/cross-channel.png)

## Changes to data architecture {#architecture}

CJA gets its data from Adobe Experience Platform. Experience Platform lets you centralize and standardize customer data and content from any system or channel and applies data science and machine learning to improve the design and delivery of personalized experiences.

Customer data in the Experience Platform is stored as datasets, which consist of a [schema](https://experienceleague.adobe.com/docs/platform-learn/tutorials/schemas/schemas-and-experience-data-model.html) and batches of data. For more detail on the platform, see [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html).

Your CJA Admin establishes [connections](/help/connections/create-connection.md) to data sets in Experience Platform. They then build [data views](/help/data-views/data-views.md) using those connections. Data views are conceptually similar to virtual report suites, and are the basis of reporting in CJA. Since Experience Platform sources all data for reporting, report suites no longer exist as a container for data.

A connection lets your Analytics Admin integrate datasets from Adobe Experience Platform into CJA, included in the following video:

>[!VIDEO](https://video.tv.adobe.com/v/35111/?quality=12)

Adobe offers multiple ways to bring data in to Adobe Experience Platform, including report suite data through the Adobe Analytics Source Connector or the Web SDK. Existing implementations from multiple report suites can be combined in Experience Platform. The connections and data views that are based on these data sets can combine data that previously existed in separate report suites.

## Changes to the concept of virtual report suites {#data-views}

[!UICONTROL Data views] take the concept of virtual report suites as they exist today and expand it to [enable additional controls on the data](/help/data-views/create-dataview.md) made available by connections. These changes make general settings like timezone and session time-out intervals configurable and retroactive. Individual variable settings like attribution and expiration can also be customized on a report or data view level. These settings are non-destructive and retroactive.

Notice that the report suite selector in the top right now lets you choose from available data views:

![data-view-selector](assets/data-views.png)

See [Use cases around data views](/help/data-views/data-views-usecases.md) for more information around this concept.

## Changes to the concept of eVars and props

The concepts of [!UICONTROL eVars], [!UICONTROL props], and [!UICONTROL events] in traditional Adobe Analytics no longer exist in [!UICONTROL Customer Journey Analytics]. In Adobe Analytics, eVars and props store descriptions of content, customers, campaigns, etc. and events count things like revenue, subscriptions, or leads generated. Customer Journey Analytics preserves both types of data, and you can access them the same way — from the left rail in Analysis Workspace, under Dimensions or Metrics, respectively. 

In CJA, unlimited schema elements are available, including dimensions, metrics, and list fields. These are mapped to unlimited schema elements including dimensions, metrics and list fields in Experience Platform. All visit and attribution settings applied after processing rules in Adobe Analytics now apply at query time in Customer Journey Analytics.

With this flexibility, you may run into situations in which a single schema field can be used as both a dimensions and a metric to support different tracking needs.

## Changes to the concept of segments

Adobe has renamed the "segments" component to "filters" to better align with industry standards and provide better distinction with segments in Adobe Experience Platform.

[!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses the Experience Platform schema field name to which they’ve been mapped. This change means that none of the existing segments in Adobe Analytics are compatible with [!UICONTROL Customer Journey Analytics]. If you want to move existing Adobe Analytics segments to Customer Journey Analytics, see the following video:

>[!VIDEO](https://video.tv.adobe.com/v/31982/?quality=12)

While you cannot yet share or publish [!UICONTROL filters] ([!UICONTROL segments]) from [!DNL Customer Journey Analytics] to Experience Platform Unified Profile, this functionality is under development.

In addition to the concept of segments changing, segment containers are also updated.

* **Hit containers are now [!UICONTROL Event] containers**. The [!UICONTROL Event] container lets you break down visitor information based on individual page views/hits. 
* **Visit containers are now [!UICONTROL Session] containers**. The [!UICONTROL Session] container lets you identify page interactions, campaigns, or conversions for a specific session.
* **Visitor containers are now [!UICONTROL Person] containers**. The [!UICONTROL Person] container includes every session and event for a visitor within the specified time frame.

## Changes to the concept of calculated metrics

Calculated metrics are similarly named between traditional Analytics and CJA. However, [!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses any Experience Platform schema element. This fundamental change means that none of the existing calculated metrics are compatible with [!UICONTROL Customer Journey Analytics]. If you want to move Adobe Analytics calculated metrics to Customer Journey Analytics, see the following video:

>[!VIDEO](https://video.tv.adobe.com/v/31788/?quality=12)

## Changes to variable attribution and expiration settings

[!UICONTROL Customer Journey Analytics] applies all variable settings, including attribution and expiration, at report time. These settings now reside in [data views](/help/data-views/component-settings/persistence.md), and some variable settings (like attribution) can be changed in Workspace projects.

You can have multiple versions of the same variable in the same data view. For example, you can have one Tracking Code dimension that expires after 30 days, and another that expires at the end of a session. Both of these Tracking Code dimensions use the same source data, but use different attribution settings.

You can also have multiple data views based on the same connection. For example, you can have one data view with a session timeout of 30 minutes, and another with a session timeout of 15 minutes. Both data views appear in the upper right selector so you can seamlessly transition between them.

## Changes to the concept of classifications

"Classifications" are now known as "Lookup datasets". Lookup datasets are used to look up values or keys found in your Event or Profile data. For example, you might upload lookup data that maps numeric IDs in your event data to product names. See [Add account-level data as a lookup dataset](/help/use-cases/b2b.md) for an example use case.

## Changes to the concept of customer attributes

"Customer attributes" are now known as "Profile datasets". Profile datasets contain data that is applied to your visitors, users, or customers in the [!UICONTROL Event] data. For example, it allows you to upload CRM data about your customers. You can pick which Person ID you want to include. Each dataset defined in [!DNL Experience Platform] has its own set of one or more Person IDs defined.

## Changes to how Adobe identifies visitors

CJA expands the concepts of identities beyond ECIDs to include any ID you want to use, including Customer ID, Cookie ID, Stitched ID, User ID, Tracking Code, and so on. Using a common namespace ID across datasets, or using [Cross-Channel Analytics](/help/connections/cca/overview.md) helps link people together across different datasets. Any user setting up a Workspace project in CJA must understand the IDs used across the datasets. See the following video that highlights the use of identities in CJA:

>[!VIDEO](https://video.tv.adobe.com/v/30750/?quality=12)

## Changes to the concept of low-traffic dimension item

In traditional Adobe Analytics, a variable that receives too many unique values starts bucketing dimension items under [!UICONTROL Low-Traffic]. CJA has fewer limitations to high cardinality fields. Changes to the reporting architecture allows Analysis Workspace to report on many more unique dimension items. See [Long Tail](../analysis-workspace/workspace-faq/long-tail.md) for more information around how CJA optimizes reporting for dimensions with many unique values.
