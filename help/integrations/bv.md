---
title: Brand Visibility Integration
description: Integrate Brand Visibility with Customer Journey Analytics
feature: Experience Platform Integration
role: User
---

# Adobe Brand Visibility integration

[Adobe Brand Visibility](https://experienceleague.adobe.com/en/docs/llm-optimizer/using/home){target="_blank"} is a generative AI-first application for Generative Engine Optimization, designed to help brands enhance their visibility, accuracy, and influence in AI-driven search environments. Brand Visibility provides insights into brand presence in AI-generated answers, offers prescriptive content recommendations, and automates optimization fixes.

AI has become a primary discovery channel. LLM agents, such as ChatGPT, Claude, Copilot, and Perplexity, crawl brand content. 

>[!PREREQUISITES]
>
>You must have an Brand Visibility paid offering provisioned and connected to your Experience Platform configuration through the managed connector.


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

### Onboard the dataset into Customer Journey Analytics

The Brand Visibility managed connector delivers the data to Experience Platform as a summary dataset. To measure it in Customer Journey Analytics, you complete two setup steps yourself:

1. Create a connection that includes the Brand Visibility dataset. See [Create or edit a connection](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection){target="_blank"}.
2. Create a data view on that connection. The data view makes the dimensions and metrics below available in Analysis Workspace. See [Create or edit a data view](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target="_blank"}.

The dataset:

* Uses [summary datasets](/help/data-views/summary-data.md) that are based on the XDM Summary Metrics class.
* Buckets data by URL and host, time, and request characteristics such as bot type, CDN provider, and status.

>[!NOTE]
>
>The Brand Visibility dataset contains aggregated data. It does not contain any PII such as a user identifier, prompts, or responses.
>

Because it is a summary dataset, you can treat it as a lookup dataset and join it to an event dataset on a full-URL key.

Brand Visibility provides this key for you in the **CDN URL** dimension. It combines the host and the requested path into a single normalized full URL, similar to how Customer Journey Analytics stores web data. Whether the join succeeds depends on your own data collection. Your event dataset needs an equivalent full URL field, or a field that you can parse and normalize to match the URL that Brand Visibility provides. When both sides resolve to the same full URL, the Brand Visibility record matches the corresponding page in your web data.

### About the dataset

Brand Visibility reads CDN access logs on the server side and extracts records where the requesting party is a bot or automated agent. Because the data comes from the CDN layer, Brand Visibility captures requests from bots that do not fire any JavaScript tag. Standard web analytics tools miss this traffic entirely.

The dataset uses the **CDN Requests Summary** field group. Every field is located under a `cdn` object, so the field names in the tables below take the form `cdn.<name>`, for example `cdn.url` and `cdn.botType`.

Each record describes one combination of host, URL path, bot type, CDN provider, status code, referrer, forwarded host, and time to first byte for one hour. When the same combination appears more than once hourly, Customer Journey Analytics combines those records into one row and increases the request count. Use the **CDN Request Count** metric to measure volume. Do not use row count.

### Dimensions

The following dimensions are available to use as components in a data view once you have set up a connection that includes an Brand Visibility dataset. The **Field** column shows the source field in the CDN Requests Summary field group.

| Dimension | Field | Description |
|-----------|-------|-------------|
| CDN URL | `cdn.url` | The normalized full URL for the request, intended as the join key. Brand Visibility combines the host and the requested path into a single URL and normalizes it to match the full-URL form that Customer Journey Analytics stores for web data. Use this dimension to join the Brand Visibility lookup dataset to an event dataset that has an equivalent full-URL field. It includes the host and path, but not the scheme. |
| CDN URL Path | `cdn.path` | The raw URL path and query string that the agent requested, as delivered by the CDN. Does not include the scheme or host. Use this when you need the exact requested path rather than the normalized join key. |
| CDN Host | `cdn.host` | The hostname that received the request, for example, www.example.com. This host is also part of the CDN URL join key. A dataset can contain multiple hosts when an organization has multiple subdomains on the same CDN account. |
| CDN Bot Type | `cdn.botType` | Brand Visibility's classification of the requesting agent. Values cover classic search crawlers, AI index crawlers, and AI live-fetch agents. See the [Bot agent categories](#bot-agent-categories) below for the full taxonomy. |
| CDN User Agent | `cdn.userAgent` | The raw user-agent string from the CDN log. Useful for distinguishing sub-types within a bot classification, or for validating the classification assigned by Brand Visibility. |
| CDN HTTP Status | `cdn.status` | The HTTP response status code. Indicates whether the bot received the content it requested. See the [Status codes](#status-codes) below for interpretation guidance specific to AI traffic. |
| CDN Provider | `cdn.cdnProvider` | Which CDN handled the request. Values are `akamai`, `byocdn-akamai`, `byocdn-fastly`, and `byocdn-cloudfront`. The `byocdn-` prefix indicates the log collection pathway, not a different CDN vendor. A dataset can contain multiple values when an organization has hosts behind different CDN configurations. |
| CDN Referrer | `cdn.referer` | The HTTP Referer header value from the CDN log. Often empty for bot traffic. When present, it can indicate which AI product or domain triggered the fetch. For example, chat.openai.com. |
| CDN Forwarded Host | `cdn.xForwardedHost` | The X-Forwarded-Host header value, if present. Relevant when the request passed through a reverse proxy or CDN shield layer before reaching the origin. |
| CDN Event Date | Derived from the record timestamp | The date part of the hourly batch timestamp for this record. |
| CDN Event Hour | Derived from the record timestamp | The hour part of the hourly batch timestamp for this record. |

### Bot agent categories

The **CDN Bot Type** dimension organizes agents into three categories. Each category answers a different analytical question.

**Classic search crawlers** index content for traditional search engines. Use this category to measure how visible your content is to traditional search engines.

| Bot type value | Vendor | Description |
|---|---|---|
| `GoogleBot` | Google | Google's main search index crawler. Also serves Google Discover and Google News. |
| `BingBot` | Microsoft | Bing's search index crawler. Also feeds Microsoft Copilot's web grounding index. |

**AI index crawlers** crawl content to build or update an AI product's training corpus or search index. These crawlers are preparing a model's knowledge base, not responding to a live user request. When a URL has high crawler volume, AI vendors consider that content worth indexing. When a URL has low crawler volume but high live-fetch volume, the model draws from cached knowledge rather than fetching fresh content.

| Bot type value | Vendor | Description |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI's primary crawler for model training data and knowledge base construction. |
| `OAI-SearchBot` | OpenAI | OpenAI's crawler for ChatGPT's web search product. Distinct from GPTBot. This agent builds the real-time search index, not the training corpus. |
| `ClaudeBot` | Anthropic | Anthropic's primary crawler for model training data. |
| `Claude-SearchBot` | Anthropic | Anthropic's crawler for Claude's search and retrieval index. Distinct from ClaudeBot. |
| `PerplexityBot` | Perplexity | Perplexity's index crawler. Perplexity uses this agent to build the corpus for its answer generation. |

**AI live fetches** occur when a real user submits a prompt to an AI assistant and the assistant fetches the page live before responding. Use this category to measure direct user demand arriving through AI assistants.

| Bot type value | Vendor | Description |
|---|---|---|
| `ChatGPT-User` | OpenAI | A user asked ChatGPT a question. ChatGPT fetched this URL to read it and form its answer. |
| `ChatGPT Clients` | OpenAI | The ChatGPT mobile app (iOS and Android) doing a live fetch. The user-agent string includes the app version and device. |
| `Claude-User` | Anthropic | A user or application using Claude live-fetched this URL. The user-agent string may identify the specific Claude product, e.g., claude-code. |
| `Perplexity-User` | Perplexity | A user asked Perplexity a question. Perplexity fetched this URL to ground its answer. |
| `Google-NotebookLM` | Google | A user opened Google NotebookLM and sourced this domain. NotebookLM fetches every reachable URL within a sourced domain. |
| `Google-ai-mode` | Google | Google Search's AI Overviews feature fetched this URL to include it in an AI-generated answer panel in search results. |
| `Gemini-Deep-Research` | Google | A user ran a Gemini Deep Research session. Deep Research makes many sequential fetches across multiple sources to compile a research report. |
| `GoogleAgent-URLContext` | Google | A user shared a URL with Gemini and asked questions about that page. Gemini fetched the URL live to answer questions about that specific content. |
| `Amzn-User` | Amazon | An Amazon Alexa or Amazon AI agent live-fetched this URL. Typically appears on reference and documentation content. |
| `MistralAI-User` | Mistral | A live fetch from a Mistral-powered product or API consumer. |

When Brand Visibility cannot match a user-agent to a recognized pattern, it assigns the value `Unknown`. You can use the **CDN User Agent** dimension to identify what agent made those requests.

### Status codes

HTTP status codes in this dataset indicate whether the AI agent received the content it requested.

| Status | Name | Interpretation |
|--------|------|----------------|
| 200 | OK | The bot received the full response. The content was available for the AI to use. |
| 304 | Not Modified | The bot confirmed the content has not changed and used its cached version. The content was available. |
| 301 | Moved Permanently | The bot was redirected to a new URL. Each redirect adds an extra round-trip. High 301 volume on frequently crawled URLs means the redirect should be resolved at the CDN level. |
| 302 | Found (Temporary Redirect) | Same latency penalty as 301. Unlike 301, it does not signal a permanent move, so bots will keep hitting the original URL. |
| 403 | Forbidden | The CDN or origin blocked the bot. This can be intentional, e.g., through robots.txt rules or WAF policy, or unintentional, e.g., through overly broad rate limits. When AI fetches are blocked, that content cannot appear in AI answers. |
| 404 | Not Found | The URL does not exist. High 404 volume on AI agent types indicates the AI's index contains stale URLs. Use the 410 status to tell crawlers to remove a URL from their index permanently. |
| 429 | Too Many Requests | The CDN rate-limited the bot. Sustained 429 errors on live-fetch agent types mean that users asking AI assistants questions about your content will receive incomplete or missing responses. |
| 504 | Gateway Timeout | The CDN stopped waiting for the origin to respond. The content did not reach the AI. When a page times out, the AI cannot access its content and cannot include it in an answer. High 504 volume on live-fetch agent types is a direct AI visibility risk. |

### Metrics

The following metrics are available to use as components in a data view once you have set up a connection that includes an Brand Visibility dataset. The **Field** column shows the source field in the CDN Requests Summary field group.

| Metric | Field | Description |
|--------|-------|-------------|
| CDN Request Count | `cdn.requests` | The total count of CDN requests, summed from the requests field across all rows. Always use this metric to measure volume. Do not use row count. |
| CDN Error Count | `cdn.status`, `cdn.requests` | The count of requests that returned a 4xx or 5xx HTTP status code. |
| CDN Error Rate | Derived from CDN Error Count | The error count as a percentage of total requests. |
| CDN Avg Time to First Byte | `cdn.timeToFirstByte` | The average time in milliseconds from when the CDN received a request to the first byte of the response. CDN-cached responses are typically under 50ms. Responses served from the origin are typically 300ms to 700ms. AI live-fetch agents often show much higher values, which correspond to timed-out or very slow origin responses. High average values on live-fetch agent types are worth investigating as an AI visibility risk. |

### Dataset boundaries

This dataset captures only bot traffic from CDN access logs. It does not contain the following:

* **User sessions, conversions, or engagement data.** A user who clicks through from an AI answer runs the JavaScript on your page, so that visit is in your existing web data, not in this dataset. You can bring both datasets into Customer Journey Analytics and compare them for the same URL and host.
* **Any person identifier such as ECID.** You cannot make a person-level join from this dataset. The join operates at the URL and host level.
* **Sub-second time granularity.** The timestamp is hourly. You cannot break down traffic within an hour into minutes or seconds.
* **Page content or rendered HTML.** This dataset records the fact of the fetch and its outcome, not what the AI read from the page.
* **Conversion data.** This dataset does not tell you whether an AI answer led a person to visit your site or convert. It holds aggregate CDN summary data, not person-based event data, so it does not link any request to an individual person or session.

## Outbound integration

To be determined.
