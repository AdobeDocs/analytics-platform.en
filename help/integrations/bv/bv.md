---
title: Brand Visibility Integration
description: Integrate Brand Visibility with Customer Journey Analytics
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---

# Adobe Brand Visibility integration

[Adobe Brand Visibility](https://experienceleague.adobe.com/en/docs/brand-visibility/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. Brand Visibility provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. Large language model (LLM) agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl brand content. 

>[!NOTE]
>
>You must have a Brand Visibility paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of Brand Visibility data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and Brand Visibility in two ways:

* **Inbound integration**: Use Brand Visibility data in Customer Journey Analytics to measure LLM-driven traffic (bot crawlers, RAG requests, agent activity) alongside existing web, mobile, and other types of data. For example, you can:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Compare LLM bot demand for a page against that page's conversions and revenue in your web data, matched at the URL and host level.
  
* **Outbound integration**: Send Customer Journey Analytics performance data into Brand Visibility so you can optimize AI visibility for the LLM sources that send you valuable traffic, such as ChatGPT or Perplexity. For example, you can:

  * See which LLM sources send human visitors who go on to convert or generate revenue. Customer Journey Analytics measures this from the referred web traffic, not from the bot dataset.
  * Rank LLM sources by the downstream value of the human visitors they send, then focus your AI visibility work on the sources that perform best.


## Inbound integration

LLM traffic reaches your site in two ways. Customer Journey Analytics measures each way from a different data source.

The first way is a person who reads an AI answer and then clicks through to your site. That visit runs the same JavaScript that collects the rest of your web data. Your existing Customer Journey Analytics web data therefore includes the visit and the referring domain that sent the user to you, for example chatgpt.com. Customer Journey Analytics does not label these visits as AI traffic on its own. To identify and group them, you create a derived field on the connection that matches the AI referring domains, then build segments and reports on that field. See [Derived fields](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}. You do not need the Brand Visibility dataset for this human traffic.

The second way is a bot or agent that requests your pages directly. This includes crawlers that build an AI index and live fetches that occur when a user submits a prompt to an AI assistant. These requests do not run any JavaScript, so your existing web data does not record them. The Brand Visibility dataset captures this traffic from the CDN layer. The rest of this section describes that dataset.


### Onboard the dataset

The Brand Visibility managed connector delivers the data to Experience Platform as a summary dataset. To measure it in Customer Journey Analytics, you complete two setup steps yourself:

1. Create a connection that includes the Brand Visibility dataset. 
2. Create a data view on that connection. The data view makes the dimensions and metrics below available in Analysis Workspace. 

The dataset:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Metrics class.
* Buckets data by URL and host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The Brand Visibility dataset contains aggregated data. It does not contain any PII such as a user identifier, prompts, or responses.
>

Because it is a summary dataset, you can use it as a lookup dataset and join it to an event dataset on a full-URL key.

Brand Visibility provides this key for you in the **CDN URL** dimension. It combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. Whether the join succeeds depends on your own data collection. Your event dataset needs an equivalent full URL field, or a field that you can parse and normalize to match the URL that Brand Visibility provides. When both sides resolve to the same full URL, the Brand Visibility record matches the corresponding page in your web data.

See for more information:

* [Setup and configure inbound integration](/help/integrations/bv/configure.md)
* [Dataset reference](/help/integrations/bv/reference.md)

## Outbound integration

For information on the outbound integration, refer to [Customer Journey Analytics Integration](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"} in the Adobe Brand Visibility documentation.
