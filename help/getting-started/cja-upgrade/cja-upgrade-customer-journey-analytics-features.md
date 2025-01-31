---
title: Understand features unique to Customer Journey Analytics
description: Learn about features unique to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Understand features unique to Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Tie together data of varying sources"
>abstract="(Recommended) The ability to combine analytics data from other channels is the primary use case for Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Stitch hits from multiple datasets"
>abstract="If any of your datasets don't share a primary identifier (such as an Experience Cloud ID), you can still stitch that data together using another dimension, such as login username or email address."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/). 

The following list shows only those Customer Journey Analytics features that require consideration during the upgrade process. For a comprehensive list that shows which Adobe Analytics features are fully supported, partially supported, or not supported in Customer Journey Analytics, see [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md).

Consider which of the following Customer Journey Analytics features you want to adopt when you upgrade to Customer Journey Analytics:

| Customer Journey Analytics feature | Function | 
|---------|----------|
| [Tie web data with data from other channels, such as call center data](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics is combined with Experience Platform's ability to hold all kinds of data schemas and types. Using [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), data can be uniformly represented and organized, ready for combination and exploration. Adobe Analytics is predominantly focused on web and mobile analytics data with some capabilities to [import data](https://experienceleague.adobe.com/docs/analytics/import/home.html). | 
| [Stitch hits from other datasets using a custom dimension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics allows you to [combine data](/help/connections/combined-dataset.md) from multiple report suites as if they were a single report suite in Adobe Analytics. | 
| [Integrate with Adobe Real-time CDP]() |  | 
| [Integrate with Adobe Journey Optimizer](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) |  | 


