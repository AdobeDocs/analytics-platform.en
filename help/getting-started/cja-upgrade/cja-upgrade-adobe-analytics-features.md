---
title: Understand Adobe Analytics feature support when upgrading to Customer Journey Analytics
description: Learn about Adobe Analytics feature support when upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 92053109-f80d-47ab-b011-c28a5411149c
---
# Understand Adobe Analytics feature support when upgrading to Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-migrate-projects"
>title="Components and projects"
>abstract="Components from Adobe Analytics include: Projects (with their associated freeform tables and visualizations), segments, and calculated metrics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map"
>title="Activity map overlay and link tracking"
>abstract="A browser extension that allows you to see link tracking data as an overlay on your site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-activity-map-support"
>title="Activity map overlay support is not yet available"
>abstract="Activity Map overlay support is not yet available in Customer Journey Analytics. It is planned to be available in the future."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-classification"
>title="Classification data"
>abstract="Group or categorize data as separate dimensions."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-marketing-channels"
>title="Marketing channels"
>abstract="Create rules that categorize how customers arrive on your site."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-feeds"
>title="Data Feeds"
>abstract="Export raw data from Adobe Analytics for use in external tools and processes."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-data-warehouse"
>title="Data Warehouse"
>abstract="Export processed data from Adobe Analytics in spreadsheet format."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-streaming-media"
>title="Streaming Media data"
>abstract="An add-on to Adobe Analytics and Customer Journey Analytics that specializes in data collection of media, such as audio, video, or streamed content."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-component-migration"
>title="Migrate projects and components"
>abstract="Bring Adobe Analytics projects and their associated components to Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

The following list shows only those Adobe Analytics features that require consideration during the upgrade process to Customer Journey Analytics. For a comprehensive list that shows which Adobe Analytics features are fully supported, partially supported, or not supported in Customer Journey Analytics, see [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md).

Consider which of the following Adobe Analytics features you want to continue using when you upgrade to Customer Journey Analytics:

| Adobe Analytics feature | Corresponding feature in Customer Journey Analytics | 
|---------|----------|
| [Components and projects from Adobe Analytics](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/build-workspace-project/freeform-overview) | [Migrate projects and their associated components to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration). | 
| [Activity map overlay and link tracking](https://experienceleague.adobe.com/en/docs/analytics/analyze/activity-map/overview) | Not yet available | 
| [Classification data](https://experienceleague.adobe.com/en/docs/analytics/components/classifications/c-classifications) | Lookup datasets are the method for classifying data in Customer Journey Analytics.<p>[Create a lookup dataset for each dimension containing classification data.](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)</p>| 
| [Marketing channels](https://experienceleague.adobe.com/en/docs/analytics/components/marketing-channels/c-getting-started-mchannel) | Derived fields are created within a data view. <p>[Create a marketing channel derived field.](/help/getting-started/cja-upgrade/cja-upgrade-marketing-channel.md)</p> | 
| [Data Feeds](https://experienceleague.adobe.com/en/docs/analytics/export/analytics-data-feed/data-feed-overview) | Experience Platform and Customer Journey Analytics provide a number of functionalities that either independently or combined can solve the various export requirements. These functionalities include [Experience Platform Data Access API](https://experienceleague.adobe.com/docs/experience-platform/data-access/api.html), [Experience Platform Destinations](https://experienceleague.adobe.com/docs/experience-platform/destinations/ui/activate/export-datasets.html), [Customer Journey Analytics Full Table Export](/help/analysis-workspace/export/export-cloud.md), and [BI tool integration](/help/data-views/bi-extension.md).<p>For more information about export options, see [Data export use cases](/help/use-cases/data-export/overview.md).</p>| 
| [Data Warehouse](https://experienceleague.adobe.com/en/docs/analytics/export/data-warehouse/data-warehouse) | [Customer Journey Analytics Full Table Export](/help/analysis-workspace/export/export-cloud.md) is the evolution of Data Warehouse reports in Adobe Analytics, with many new, often-requested features that are not available in Data Warehouse today. | 
| [Streaming Media data](https://experienceleague.adobe.com/en/docs/media-analytics/using/media-overview) | Streaming media data are available using the Analytics source connector as part of the Media Concurrent Viewers panel and the Media Playback Time Spent panel in Workspace. |
