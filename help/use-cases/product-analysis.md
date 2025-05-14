---
title: Product analysis in Customer Journey Analytics
description: Learn what features that you can use inside Customer Journey Analytics to perform product analysis effectively.
exl-id: b185a2ed-18c8-4fb3-8c69-693d5fee0e67
---
# Product analysis in Customer Journey Analytics

Product analysis is the process of understanding how users interact with your product at every stage of their journey. It involves analyzing data to uncover insights about user behavior, product performance, and opportunities for growth. Effective product analysis helps teams make informed decisions to improve user experiences, drive engagement, and achieve business goals.

Customer Journey Analytics empowers teams with the tools to analyze and optimize product experiences with capabilities to:

* **Manage product data at scale**: Easily ingest, transform, and manage product data to meet your business needs, ensuring reliable insights.
* **Measure Acquisition and Activation**: Track how new users discover your product and engage with first value-driving events.
* **Measure Engagement and Adoption**: Understand how users progress through the product funnel, identify friction points, and track adoption of key features.
* **Measure Retention and Churn**: Analyze user retention over time, identify indicators of churn, and develop strategies to reduce drop-off and increase loyalty.
* **Action product insights**: Turn data-driven insights into actionable strategies to improve the user experience and drive sustainable product growth.
* **Share insights with your organization**: Communicate key findings across teams to align efforts, foster collaboration, and ensure that everyone is working toward shared product and business goals.

By leveraging these capabilities, Customer Journey Analytics enables you to unlock the full potential of your product and create a seamless, data-driven approach to driving user and business success.

## Manage product data at scale

Accurate product data is the cornerstone of effective product analysis. Data ingestion refers to the process of instrumenting and gathering product data, while data management involves transforming and maintaining this data to ensure it meets your analytical requirements.

The following capabilities within Adobe Experience Platform and Customer Journey Analytics empower you to ingest and manage your product data at scale:

* Adobe Experience Platform
  * [Datasets​](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)
  * [Data prep​](https://experienceleague.adobe.com/en/docs/experience-platform/data-prep/home)
  * [Data Distiller​](https://experienceleague.adobe.com/en/docs/experience-platform/query/data-distiller/overview)
* Customer Journey Analytics
  * [Connections​](/help/connections/overview.md)
  * [Data views](/help/data-views/data-views.md), including [derived fields​](/help/data-views/derived-fields/derived-fields.md)
  * [Segments​](/help/components/filters/filters-overview.md)
  * [Calculated metrics](/help/components/calc-metrics/calc-metr-overview.md)
  * [Guided analysis​: Timeline​](/help/guided-analysis/types/timeline.md)

## Measure acquisition and activation

Product growth hinges on actionable top-of-funnel insights that attract new users, reveal conversion paths, and eliminate friction along the journey.

* Acquisition tracks new users coming to your product, including how they arrive and which efforts are most or least effective.
* Activation monitors new users who engage with your first value event, defined according to your specific goals.

![Active growth](/help/guided-analysis/assets/active.png)

![Engagement analysis](/help/guided-analysis/assets/feature-matrix.png)

The following capabilities in Customer Journey Analytics enable you to measure both acquisition and activation effectively:

* [Guided analysis​: Active growth](/help/guided-analysis/types/active-growth.md)
* [Guided analysis: Net growth](/help/guided-analysis/types/net-growth.md)
* [Guided analysis: Trends](/help/guided-analysis//types/trends.md)
* [Attribution panel​](/help/analysis-workspace/c-panels/attribution.md)
* [Freeform table](/help/analysis-workspace/c-panels/freeform-panel.md) that includes the marketing channel dimension (creating using a [derived field](/help/data-views/derived-fields/derived-fields.md))

## Measure engagement and adoption

Acquiring new users expands the top of your product funnel. Engagement focuses on guiding those users further down the funnel and removing obstacles to their success. Their success directly drives your business success.

The following capabilities in Customer Journey Analytics help you track product engagement and adoption:

* [Guided analysis: Engagement](/help/guided-analysis/types/engagement.md)
* [Guided analysis: Trends](/help/guided-analysis/types/trends.md)
* [Guided analysis: Frequency](/help/guided-analysis/types/frequency.md)
* [Guided analysis: Funnel](/help/guided-analysis/types/funnel.md)
* [Guided analysis: Conversion trends](/help/guided-analysis/types/conversion-trends.md)
* [Guided analysis: Release impact](/help/guided-analysis/types/release-impact.md)
* [Guided analysis: First use impact​](/help/guided-analysis/types/first-use-impact.md)
* [Guided analysis: Timeline](/help/guided-analysis/types/timeline.md)
* [Freeform tables​](/help/analysis-workspace/c-panels/freeform-panel.md)
* [Flow](/help/analysis-workspace/visualizations/c-flow/flow.md)

## Measure retention and churn

Retention measures how many users continue to engage with the product after initial acquisition and activation. High-performing products maintain a stable, loyal user base by maximizing interaction with the features that most strongly correlate with continued use. A retained user returns and interacts with the product over time, while a churned user does not. Product teams track retention to pinpoint the features that drive ongoing engagement, and design interventions that shift churned users toward retained user behavior.

![Retention analysis](/help/guided-analysis/assets/retention.png)

The following capabilities in Customer Journey Analytics help you track retention and churn effectively:

* [Guided analysis: Retention](/help/guided-analysis/types/retention.md)​
* [Guided analysis: Active growth](/help/guided-analysis/types/active-growth.md)
* [Guided analysis: Net growth](/help/guided-analysis/types/net-growth.md)
* [Cohort table​](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)

## Actionable product insights

Insights deliver value only when they drive action. Convert analytics findings into actions that improve the user experience and support long-term product growth.

The following capabilities within Experience Cloud enable you to act on insights effectively:

* [Create and publish audiences](/help/components/audiences/publish.md)​ for activation from Customer Journey Analytics
* Activate audiences through Experience Cloud products:
  * [Run experiments](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/content-management/content-experiment/get-started-experiment) in AJO and Adobe Target, and measure the impact of variations in Customer Journey Analytics using the [Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md)
  * [Deliver in-app engagements](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/channels/in-app/get-started-in-app) to users in AJO
* [Activate audiences](https://experienceleague.adobe.com/en/docs/experience-platform/destinations/ui/activate/activation-overview) to external destinations with Adobe Real-time CDP​

## Share insights to the organization​

Communicate key findings across teams to align efforts, foster collaboration, and ensure everyone works toward shared product and business goals.

![Guided Analysis in Workspace](assets/guided-analysis-workspace.png)

The following capabilities in Customer Journey Analytics help you share insights effectively:

* [Share](/help/analysis-workspace/curate-share/share-projects.md) guided analysis views tailored to specific business questions, enabling consumers to self-serve their next question
* Combine guided analyses, panels, and visualizations into a comprehensive dashboard in [Analysis Workspace](/help/analysis-workspace/home.md)
* Create a [mobile scorecard](/help/mobile-app/home.md) with key product insights for Executives and other consumers on the go
