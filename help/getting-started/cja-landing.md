---
title: Customer Journey Analytics Guide
description: Customer Journey Analytics landing page.
solution: Customer Journey Analytics
feature: Basics
exl-id: 7f67c497-386b-4442-a502-6b492f35c6e6
---
# Customer Journey Analytics Guide

This technical documentation guide provides self help assistance for Customer Journey Analytics. Customer Journey Analytics allows you to bring your customer data from any channel you choose (both online and offline) into Adobe Experience Platform. And then analyze this data just as you would your existing digital data using Analysis Workspace today.

Customer Journey Analytics lets you control how you connect your online and offline data in Analysis Workspace on any common customer ID, allowing you to do attribution, segments, flow, fallout, etc. across your customer data.

## What's new?

Get a glimpse of the newest enhancements in the Customer Journey Analytics product and documentation! For a comprehensive list of features, improvements, and fixes, check out the detailed [Release Notes](../release-notes/latest.md). Visit the [documentation updates page](../release-notes/doc-changes.md) to stay up-to-date with the latest documentation updates.

>[!BEGINTABS]

>[!TAB B2B Edition]

Customer Journey Analytics B2B Edition helps B2B companies align their marketing, sales, and product teams by providing actionable account insights that drive revenue growth. With the account placed at the center of the data model, all analysis focuses on the account journey.

[![image](assets/learn-more-button.svg)](/help/getting-started/cja-b2b-edition.md)

>[!TAB Content Analytics]

Content Analytics allows you to quickly and easily investigate large volumes of content data to uncover trends, spot anomalies, identify content fatigue, and gain insights from content exposure.

[![image](assets/learn-more-button.svg)](/help/content-analytics/content-analytics.md)

>[!TAB Event Depth]

Event Depth is a new standard dimension and provides new ways to measure and better understand how events are positioned within customer sessions. The Event Depth dimension enables detailed tracking and analysis of where specific events occur in the sequential flow of user interactions within a session.

[![image](assets/learn-more-button.svg)](/help/components/dimensions/overview.md#standard-dimensions)


>[!TAB Shared metrics and dimensions]

Shared metrics and dimensions provide a central location to manage dimensions and metrics that can be used across any number of data views. These components are especially valuable to organizations that use multiple data views, especially if those data views share common component settings.

[![image](assets/learn-more-button.svg)](/help/data-views/shared-metrics-dimensions/smd-overview.md)


<!--
>[!TAB AI Assistant] 

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace - whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

[![image](assets/learn-more-button.svg)](/help/ai-assistant.md)


>[!TAB Guided Analysis] 

Guided Analysis is now available directly from within Analysis Workspace, enabling users to create dashboards with comprehensive insights from panels, visualizations, and guided analyses.

[![image](assets/learn-more-button.svg)](/help/guided-analysis/overview.md)



>[!TAB Intelligent captions v2] 

Intelligent captions are now supported, with additional interface improvements, for [Line](/help/analysis-workspace/visualizations/line.md) (including multi-line), [Bar](/help/analysis-workspace/visualizations/bar.md), [Horizontal bar](/help/analysis-workspace/visualizations/horizontal-bar.md), [Area](/help/analysis-workspace/visualizations/area.md) (including multiple Area lines), [Donut](/help/analysis-workspace/visualizations/donut.md), [Fallout](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md) visualizations.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Alerts] 

Alerts allow you to be notified based on changed percentages or specific data points. You can preview how often an alert will trigger, send alerts by email or SMS, create stacked alerts, and more.

[![image](assets/learn-more-button.svg)](/help/components/c-intelligent-alerts/intelligent-alerts.md)


>[!TAB Summary data] 

Allows you to bring in time-series data that does not have a person ID. This time-series data can be used to support various use cases, such as 

- Presenting high-level performance indicators as part of or next to event-level data. 
- Uploading targets or goals at an hourly or daily basis, then positioning these targets or goals against event-level metrics. 

[![image](assets/learn-more-button.svg)](/help/data-views/summary-data.md)

-->

>[!TAB Graph-based stitching*] 

Through Graph-based stitching, you can use the identity graph from the Experience Platform Identity Service to get a better view of the customer journey by: <ul><li>Joining datasets with different identifiers without having to extract, transform and load additional data to reflect a single identifier.</li> <li>Improving coverage of preferred or golden identity for a single dataset by sharing identities across datasets,</li><li>Aligning profiles created in Real-Time Customer Data Platform and Journey Optimizer with people in Customer Journey Analytics.</li></ul>

[![image](assets/learn-more-button.svg)](/help/stitching/overview.md#graph-based-stitching)

*_You must have the Prime package for graph-based stitching._*

>[!TAB BI extension*] 

The BI extension enables SQL access to the data views that you have defined in Customer Journey Analytics. You can now use your favorite BI tool (Power BI Desktop, Tableau Desktop, Looker, Juyter Notebook, and RStudio) to create reporting and dashboards based on the same data views that Customer Journey Analytics users use with their Analysis Workspace projects. [Use cases](/help/use-cases/data-views/bi-extension-usecases.md) are provided.

[![image](assets/learn-more-button.svg)](/help/data-views/bi-extension.md)

*_You must have the Select package or higher to use the BI extension._*


>[!ENDTABS]

## Start with the basics

Start by reading the material in the links below to familiarize yourself with Customer Journey Analytics capabilities and functionalities.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
    <a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/aa-vs-cja.png"></a>
    <div><strong>Beyond online data</strong><br/>Learn how Customer Journey Analytics compares to Adobe Analytics, what features are shared and how you can use your Analytics data.</div>
    </td>
    <td>
    <a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/data-ingestion.png"></a>
    <div><strong>Ingest and use data</strong><br/>Learn about the options that you have to ingest data into Experience Platform and use it for analysis and reporting in Customer Journey Analytics.</div>
    </td>
    <td>
    <a href="/help/guided-analysis/overview.md"><img src="./assets/product-analytics.png"></a>
    <div><strong>Guided Analysis</strong><br/>Learn how to use workflows to gain data and insights about your customer's product experience. Product Analytics through guided analysis…
    </div>
    </td>
    <td>
    <a href="/help/analysis-workspace/home.md"><img src="./assets/workspace.png"></a>
    <div><strong>Analysis Workspace</strong><br/>Use Analysis Workspace to perform basic and advanced analysis, like attribution, flow and fallout diagrams, dimension breakdowns.</div>
    </td>
  </tr>
  <tr style="border: 0;">
    <td align="center"><a href="/help/getting-started/aa-vs-cja/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/data-ingestion/data-ingestion.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/guided-analysis/overview.md"><img src="./assets/learn-more-button.svg"></a></td>
    <td align="center"><a href="/help/analysis-workspace/home.md"><img src="./assets/learn-more-button.svg"></a></td>
    </tr>
</table>


## Explore the documentation

Understand how Customer Journey Analytics compares to Adobe Analytics. And how to get your data in the solution and then prepare, view, analyze, and democratize that data and the resulting analysis and reports.

<table style="table-layout:fixed">
  <tr style="border: 0;">
    <td>
      <img src="./assets/analytics.svg" width="35px"><br/>
      <strong>Compare to Adobe Analytics</strong><br/><a href="/help/getting-started/aa-vs-cja/overview.md">Overview</a> - <a href="/help/getting-started/aa-to-cja.md">Evolution</a> - <a href="/help/getting-started/aa-vs-cja/aa-data-in-cja.md">Use Adobe Analytics data</a> - <a href="/help/getting-started/aa-vs-cja/cja-aa.md">Feature support</a> - <a href="/help/getting-started/aa-vs-cja/terminology.md">Terminology</a> - <a href="/help/getting-started/aa-vs-cja/data-processing-comparisons.md">Data processing</a> - <a href="/help/getting-started/cja-b2b-edition.md">Customer Journey Analytics B2B Edition</a>
    </td>
    <td>
      <img src="./assets/connections.svg" width="35px"><br/>
      <strong>Connections</strong><br/><a href="/help/connections/overview.md">Overview</a> - <a href="/help/connections/create-connection.md">Create</a> - <a href="/help/connections/manage-connections.md">Manage</a> - <a href="/help/stitching/overview.md">Stitch</a> - <a href="/help/connections/combined-dataset.md">Combined event datasets</a> - <a href="/help/connections/standard-lookups.md">Standard Lookups</a>
    </td>
     <td>
      <img src="./assets/dataviews.svg" width="35px"><br/>
      <strong>Data views</strong><br/><a href="/help/data-views/data-views.md">Overview</a> - <a href="/help/data-views/create-dataview.md">Create or edit</a> - <a href="/help/data-views/session-settings.md">Session settings</a> - <a href="/help/data-views/derived-fields/derived-fields.md">Derived fields</a> - <a href="/help/data-views/summary-data.md">Summary data</a> - <a href="/help/data-views/component-reference.md">Component reference</a>
    </td>
    
  </tr>
  <tr style="border: 0;">
    <td>
      <img src="./assets/workspace.svg" width="35px"><br/>
      <strong>Workspace Projects</strong><br/><a href="/help/analysis-workspace/home.md">Analysis Workspace</a> - <a href="/help/analysis-workspace/perform-basic-analysis.md">Basic</a> & <a href="/help/analysis-workspace/perform-adv-analysis.md">Advanced analysis</a> - <a href="/help/analysis-workspace/build-workspace-project/freeform-overview.md">Projects</a> - <a href="/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md">Visualizations</a> - <a href="/help/analysis-workspace/c-panels/freeform-panel.md">Panels</a>
    </td>
    <td>
      <img src="./assets/guided-analysis.svg" width="35px"><br/>
      <strong>Guided Analysis</strong><br/><a href="/help/guided-analysis/overview.md">Overview</a> - <a href="/help/guided-analysis/types/active-growth.md">User Growth</a> - <a href="/help/guided-analysis/types/trends.md">Trends</a> - <a href="/help/guided-analysis/types/funnel.md">Funnel</a> - <a href="/help/guided-analysis/types/release-impact.md">Impact</a> - <a href="/help/guided-analysis/industry-use-cases.md">Industry use cases</a>
    </td>
    <td>
      <img src="./assets/share.svg" width="35px"><br/>
      <strong>Share, export, integrate</strong><br/><a href="/help/analysis-workspace/curate-share/share-projects.md">Projects</a> - <a href="/help/mobile-app/home.md">Analytics Dashboards</a> - <a href="/help/report-builder/rb-overview.md">Report Builder</a>  - <a href="/help/components/exports/manage-exports.md">Cloud export</a> - <a href="/help/integrations/overview.md">Integrations</a>
    </td>
  </tr>
</table> 

## Additional resources

<table style="table-layout:fixed"><tr style="border: 0;">
<td><strong>Customer Journey Analytics</strong><br/>
<a href="https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/overview" target="_blank">Tutorials</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics.html" target="_blank">Customer Journey Analytics product description</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/adobe-analytics-addon-customer-journey-analytics.html" target="_blank">Adobe Analytics (Customer Journey Analytics add-on) product description</a> - <a href="https://helpx.adobe.com/legal/product-descriptions/customer-journey-analytics-b2b.html" target="_blank">Customer Journey Analytics B2B Edition product description</a> - <a href="https://developer.adobe.com/cja-apis/docs/" target="_blank">Customer Journey Analytics APIs</a> - <a href="/help/ai-assistant.md">AI Assistant</a>
</td>
<td><strong>Data Ingestion</strong><br/><a href="/help/data-ingestion/data-ingestion.md">Overview</a> - <a href="/help/data-ingestion/analytics.md">Analytics</a> - <a href="/help/data-ingestion/aepwebsdk.md">Web SDK</a> - <a href="/help/data-ingestion/aepmobilesdk.md">Mobile SDK</a> - <a href="/help/data-ingestion/batch.md">Batch</a> - <a href="/help/data-ingestion/streaming.md">Streaming</a> - <a href="/help/data-ingestion/sources.md">Sources</a> - <a href="/help/data-ingestion/serverapi.md">Server API</a>
</td>
</tr>
</table>


<table style="table-layout:auto" class="tablelayout-is-fixed"><tbody><tr style="border: 0;"><td><img src="./assets/newsletter.png"></td><td>
<b>Stay informed, contribute to the community, and elevate your Customer Journey Analytics experience!</b><br>Visit the Adobe Analytics community to discuss the functionality with fellow practitioners. <a href="https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community">Join the community today!</a></td></tr></tbody></table>
