---
title: LLM Optimizer Integration
description: Integrate LLM Optimizer with Customer Journey Analytics
feature: Experience Platform Integration
role: User
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
---

# LLM Optimizer integration

[Adobe LLM Optimizer](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. LLM Optimizer provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agent activity through tools like ChatGPT, Claude, Copilot, and Perplexity crawls and references brand content. 

>[!PREREQUISITES]
>
>You must have an LLM Optimizer paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


>[!IMPORTANT]
>
>As part of this integration, some temporary processing of LLM Optimizer data occurs in the United States. Data is ultimately stored in your designated region as configured in your Customer Journey Analytics contract.


## Use cases

You can benefit from the integration between Customer Journey Analytics and LLM Optimizer in two ways:

* **Inbound integration**: Use LLM Optimizer data in Customer Journey Analytics to measure LLM-driven traffic (bot crwalers, RAG requests, agent activity) alongside existing web, mobile, and other type of data. For example to address the following use cases:
  
  * Measure LLM-driven traffic by agent source alongside traditional channels.
  
  * Identify content that is heavily consumed by LLMs but underperforms in human conversion.
  
  * Detect where LLM-agent requests fail across critical paths.

  * Correlate LLM activity with downstream business outcomes (revenue, conversions, engagement).
  
* **Outbound integration**: Use Customer Journey Analytics performance data inside LLM Optimizer so AI visibility can be optimized for real business outcomes. For example, to address the following use cases:

  * Evaluate how each LLM agent correlates with revenue, conversions, and engagement.
  * Identify which LLM agents are associated with stronger downstream performance. Which LLM agents are associated with higher engagement or conversion rates.


## Inbound integration

To ingest LLM Optimizer data into Customer Journey Analytics, use the LLM Optimizer datasets available in Experience Platform. The ingestion method:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Schema class.
* Buckets data by URL/host, time, and LLM Optimizer session characteristics.

>[!NOTE]
>
>The LLM Optimizer dataset contains aggregated data that does not contain any PII data like user identifier, prompts or responses.
>

You use the LLM Optimizer dataset in a connection. In the connection you treat the LLM Optimizer dataset as a lookup dataset where you join the LLM Optimizer dataset on the URL/host key available within an event dataset.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes a LLM Optimizer dataset.

| Dimension | Description |
|-----------|-------------|
| LLM URL | The URL accessed by the LLM agent |
| LLM Host | The host domain |
| LLM Referrer | Referral source LLM |
| LLM User Agent | LLM bot user agent string |
| LLM HTTP Status | HTTP response status code |
| LLM CDN Provider | CDN serving the content |
| LLM Forwarded Host | Forwarded host header value |
| LLM Event Date | Date of the LLM request |
| LLM Event Hour | Hour of day of the LLM request |
| LLM Session Bucket | LLM session grouping |
| LLM Referral Source | Source LLM platform |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes a LLM Optimizer dataset.

| Metric | Description |
|--------|-------------|
| LLM Request Count | Total LLM agent requests |
| LLM Unique Session Count | Distinct LLM sessions |
| LLM Error Count | Requests that returned errors |
| LLM Error Rate | Error rate as a percentage |
| LLM Avg Time to First Byte | Latency metric (TTFB) |
| LLM Request Duplication Count | Duplicate request volume |

### Outbound integration

T.b.d.
