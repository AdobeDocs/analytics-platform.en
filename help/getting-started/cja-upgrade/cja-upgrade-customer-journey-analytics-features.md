---
title: Understand features unique to Customer Journey Analytics
description: Learn about features unique to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 4e6cacb9-4eca-4dfb-bce4-e69850507596
TQID: https://experienceleague.adobe.com/8yBVFyHrc31-ac8XLV-aW-SWBfDZodlIXirICmdzpkY
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
---
# Understand features unique to Customer Journey Analytics {#feature-support-upgrade}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-tie-data"
>title="Tie together data of varying sources"
>abstract="(Recommended) Tie data from various web, mobile, and offline properties to create a single, consolidated view of customer behavior. This ability to combine analytics data from other channels is the primary use case for Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-datasets"
>title="Stitch hits from multiple datasets"
>abstract="If any of your datasets don't share a primary identifier (such as an Experience Cloud ID), you can still stitch that data together using another dimension, such as login username or email address."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-stitch-customer-care"
>title="Enable stitching for relevant datasets"
>abstract="If you have a field that contains an identifier that exists in multiple datasets but is not the primary identifier, you can use stitching to elevate the data into one or more of these datasets."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-rtcdp"
>title="Integrate with Real-time CDP"
>abstract="Combine profile data from multiple sources to generate audiences and segments based on user traits."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-target"
>title="Temporarily integrate with Adobe Target"
>abstract="Adobe recommends integrating with Adobe Journey Optimizer for personalization use cases. Integrating with Adobe Target is possible, but a short-term solution."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-ajo"
>title="Integrate with Journey Optimizer"
>abstract="Deliver connected, contextual, and personalized experiences to customers."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-integrate-aam"
>title="Temporarily integrate with Adobe Audience Manager"
>abstract="Adobe recommends integrating with Adobe Real-time CDP for audience-based use cases. Integrating with Audience Manager is possible, but a short-term solution."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}} 

The following list shows only those Customer Journey Analytics features that require consideration during the upgrade process. For a comprehensive list that shows which Adobe Analytics features are fully supported, partially supported, or not supported in Customer Journey Analytics, see [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md).

Consider which of the following Customer Journey Analytics features you want to adopt when you upgrade to Customer Journey Analytics:

| Customer Journey Analytics feature | Function |
|---------|----------|
| [Tie web data with data from other channels, such as call center data](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-usecases/cross-channel/cross-channel) | Customer Journey Analytics is combined with Experience Platform's ability to hold all kinds of data schemas and types. Using [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), data can be uniformly represented and organized, ready for combination and exploration. Adobe Analytics is predominantly focused on web and mobile analytics data with some capabilities to [import data](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| [Stitch hits from other datasets using a custom dimension](https://experienceleague.adobe.com/en/docs/analytics-platform/using/stitching/overview) | Customer Journey Analytics allows you to [combine data](/help/connections/combined-dataset.md) from multiple report suites as if they were a single report suite in Adobe Analytics. |
| [Integrate with Adobe Real-time CDP](/help/components/audiences/audiences-overview.md) | You can [create and publish audiences](/help/components/audiences/audiences-overview.md) discovered in Customer Journey Analytics to Real-Time Customer Profile in Adobe Experience Platform for customer targeting and personalization. |
| [Integrate with Adobe Target (A4T)](/help/integrations/at.md) | Target Reporting in Customer Journey Analytics enables you to [measure and report on Adobe Target activities](/help/integrations/at.md) directly in Customer Journey Analytics. However, Adobe recommends integrating with Adobe Journey Optimizer for personalization use cases.  |
| [Integrate with Adobe Journey Optimizer](/help/integrations/ajo.md) | You can configure data generated by Journey Optimizer to [perform advanced analysis in Customer Journey Analytics](/help/integrations/ajo.md).  |
| [Integrate with Adobe Audience Manager](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing) | You can [share Audience Manager traits and segments to Adobe Experience Platform](https://experienceleague.adobe.com/en/docs/audience-manager/user-guide/implementation-integration-guides/integration-experience-platform/aam-aep-audience-sharing). However, Adobe recommends integrating with Adobe Real-time CDP for audience-based use cases.  |
