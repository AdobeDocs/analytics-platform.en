---
title: CJA User Guide for Adobe Analytics users
description: What to consider from a user's perspective when your company moves data from Adobe Analytics to Customer Journey Analytics
role: User
solution: Customer Journey Analytics
feature: CJA Basics
---

# CJA User Guide for Adobe Analytics users

Congratulations, your company has moved at least some of its data to Customer Journey Analytics! In starting to work with Customer Journey Analytics, you will notice some big differences and some similarities. This page aims to explain those things that haven't changed, as well as some of the major differences.

We will also tell you how you can get more information on new concepts, and further steps to make YOUR customer journey easier and more successful.

## What hasn't changed

A lot of what you are familiar with on the reporting side has not changed. You can still use the power of Analysis Workspace to analyze your data, plus Adobe Analytics dashboards and a new version of Report Builder. Workspace and dashboards work essentially the same as they did in traditional Adobe Analytics. Report Builder has a new interface and now runs on PCs, Mac computers, and the web version of Excel. Reporting-wise, what's different is that you have access to a lot more cross-channel data to analyze. Here is an Workspace example of 

## New architecture

Customer Journey Analytics gets its data from Adobe Experience Platform. Experience Platform lets you centralize and standardize customer data and content from any system or channel and applies data science and machine learning to improve the design and delivery of personalized experiences. 

Customer data in the platform is stored as datasets, which consist of a schema and batches of data. For more detail on the platform, see [Adobe Experience Platform Architecture Overview](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=en).

Your CJA Admin will establish connections to the data in Platform, and builds data views within those connections. Think of data views as similar to virtual report suites. Data views are the basis of reporting in Customer Journey Analytics.

## New concepts and terminology

Several features in CJA have been renamed and re-architected, when compared to traditional Adobe Analytics, to align with industry standards. Some updated terminology includes segments, virtual report suites, classifications, customer attributes, and container names. Familiar concepts like eVars and props no longer exist, along with the limitations they imposed.

### eVars and props

[!UICONTROL eVars], [!UICONTROL props], and [!UICONTROL events] in the traditional Adobe Analytics sense no longer exist in [!UICONTROL Customer Journey Analytics]. You have unlimited schema elements (dimensions, metrics, list fields). So all of the attribution settings you used to apply during the data collection process are now applied at query time.

### Segments are now 'Filters'

[!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses any AEP schema. This means none of the existing segments are compatible with [!UICONTROL Customer Journey Analytics]. In addition, "segments" have been renamed to "filters".

For the time being, you cannot share/publish [!UICONTROL filters] ([!UICONTROL segments]) from [!DNL Customer Journey Analytics] to Experience Platform Unified Profile, or other Experience Cloud applications. This functionality is currently being developed.

### Calculated metrics

[!UICONTROL Customer Journey Analytics] no longer uses eVars, props, or events and instead uses any AEP schema. This means none of the existing calculated metrics are compatible with [!UICONTROL Customer Journey Analytics]. 

### Session and variable persistence settings

[!UICONTROL Customer Journey Analytics] applies all of these settings at report time, and these settings now live in Data Views. Changes to these settings are now retroactive, and you can have multiple versions by using multiple Data Views! 

### Virtual Report Suites are now 'Data views'



### Classifications are now 'Lookup datasets'

### Customer attributes are now 'Profile datasets'


### Hit containers are now 'Event' containers

### Visit containers are now 'Session' containers

### Visitor containers are now 'Person' containers

### `Uniques Exceeded` limitations

[!UICONTROL Customer Journey Analytics] has no unique value limitations, so no need to worry about them!
