---
title: Use derived fields to report on AI traffic
description: Understand how you can use derived fields to report on AI traffic in Workspace.
solution: Customer Journey Analytics
feature: Use Cases
role: User
---

# Report on LLM and AI-generated traffic

This article explores how to use the Customer Journey Analytics derived fields capability to report on LLM (Large Language Model) and AI-generated traffic.

## Detection methods

To detect LLM and AI-generated traffic, distinguish between:

* LLM crawlers: collect data for training and retrieval augmented generation (RAG).
* AI agents: function as interfaces that perform task on behalf of humans. AI agents prefer to interact via APIs, which bypasses web analytics tracking methods. Nonetheless, you can still analyze a significant portion of AI-generated traffic through websites.

Three common core detection methods to identify and monitor LLM and AI-generated traffic are:

* User agent detection: When a request is made to your server, the HTTP User-Agent header is extracted and analyzed against known AI crawler and agent patterns. This server-side method requires access to HTTP headers and is most effective when implemented at the data collection layer.
* Referrer analysis: The HTTP Referrer header contains the URL of the previous webpage that linked to the current request. This header reveals when users click through to your site from web interfaces like ChatGPT or Perplexity.
* Query parameter tracking: AI services can append URL parameters (particularly UTM parameters) to links. These parameters persist in the URL and can be captured through standard analytics implementations, making these URL parameters valuable indicators even in client-side tracking scenarios.

The following table illustrates how the detection methods can be used against different LLM and AI interaction scenarios.

| Scenario | User agent detection | Referrer analysis | Query parameter tracking |
|---|---|---|---|
| **Training of a Model** | Detectable (GPTBot, ClaudeBot, etc.) when server-side logging is implemented. | Not present. AI crawlers don't generate referrers during training. | Not present. AI crawlers don't typically add parameters during training. |
| **Agent Browsing** | Detectable (ChatGPT-User, claude-web) when server-side logging captures headers.  | Might appear if the agent navigates from an AI interface with referrer preservation. | Sometimes present if the AI service adds tracking parameters. |
| **Retrieval-Augmented Generation (RAG) to Answer Query** | Detectable (OAI-SearchBot, PerplexityBot) with server-side logging. | Not typically present as RAG operations often bypass referrer mechanisms. | Rarely present unless specifically implemented by the AI provider. |
| **User Clicks Through** | Not detectable. AI agent appears as a normal user agent. | Detectable when users click links from AI interfaces (chatgpt.com, claude.ai, and more). | Sometimes AI services might add UTM parameters to outbound links. |
| **Traffic Visibility Conditions** | Require server-side logging integration with CJA, or server-side tagging. | Depends on AI platform referrer policies and proper HTTP header transmission. | Requires parameter preservation through redirects and proper URL parameter collection. | 

### Challenges

LLM & AI agents demonstrate complex and evolving behaviors when interacting with digital properties. These technologies operate inconsistently across platforms and versions. This inconsistency creates unique challenges for data professionals. The behavioral patterns vary significantly and depend on the specific AI platform, version, and interaction mode used. This operational diversity complicates efforts to track and categorize LLM and AI-generated traffic within standard analytics frameworks. The complex nature of these interactions, combined with their rapid evolution, requires nuanced detection and classification methods to maintain data integrity:

* Partial data collection: Some newer AI agents execute limited JavaScript, resulting in incomplete analytics data for client-side implementations. As a result, some interactions are tracked while other interactions are missed.
* Inconsistent session data: AI agents might execute JavaScript differently across sessions or page types. This execution difference creates fragmented user journeys in Customer Journey Analytics for client-side implementations.
* Detection challenges: With partial tracking, detection becomes unreliable as certain touchpoints might be invisible to analytics.
  

## Signatures

As of August 2025, the following specific signals can be identified for each of the detection methods,

### User agent identification

<table>
<thead>
<tr>
<th>Crawler</th>
<th>User Agent String</th>
<th>Purpose/Behavior</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>GPTBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; GPTBot/1.1; +<a href="https://openai.com/gptbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/gptbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">OpenAI's primary web crawler for training ChatGPT and language models</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/1.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">Used when ChatGPT browses websites on behalf of users (legacy)</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User v2</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/2.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">ChatGPT's updated version for on-demand fetching and in-response lookups</a></td>
</tr>
<tr>
<td><strong>OAI-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; OAI-SearchBot/1.0; +<a href="https://openai.com/searchbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/searchbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">ChatGPT's search-focused crawler for discovering content</a></td>
</tr>
<tr>
<td><strong>ClaudeBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ClaudeBot/1.0; +claudebot@anthropic.com</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Anthropic's crawler for training and updating the Claude AI assistant</a></td>
</tr>
<tr>
<td><strong>Claude-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-User/1.0; +Claude-User@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Supports Claude AI users when individuals ask questions to Claude, it may access websites using a Cl...</a></td>
</tr>
<tr>
<td><strong>Claude-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-SearchBot/1.0; +Claude-SearchBot@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">Navigates the web to improve search result quality for Claude AI users by analyzing online content t...</a></td>
</tr>
<tr>
<td><strong>PerplexityBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; PerplexityBot/1.0; +<a href="https://www.perplexity.ai/perplexitybot" target="_blank" rel="noopener nofollow noreferrer">https://perplexity.ai/perplexitybot</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Perplexity.ai's crawler for real-time web data indexing</a></td>
</tr>
<tr>
<td><strong>Perplexity-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Perplexity-User/1.0; +<a href="https://www.perplexity.ai/useragent" target="_blank" rel="noopener nofollow noreferrer">https://www.perplexity.ai/useragent</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Loads pages when users click Perplexity citations (bypasses robots.txt)</a></td>
</tr>
<tr>
<td><strong>Google-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Google-Extended/1.0; +<a href="https://support.google.com/webmasters/answer/182072" target="_blank" rel="noopener nofollow noreferrer">http://www.google.com/bot.html</a>)</code></td>
<td><a href="https://blog.google/technology/ai/an-update-on-web-publisher-controls/" target="_blank" rel="noopener nofollow noreferrer">Google's AI-focused crawler for Gemini separate from standard Googlebot</a></td>
</tr>
<tr>
<td><strong>BingBot</strong></td>
<td><code>Mozilla/5.0 (compatible; BingBot/1.0; +<a href="http://www.bing.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bing.com/bot.html</a>)</code></td>
<td>Microsoft's crawler powering Bing Search and Bing Chat (Copilot)</td>
</tr>
<tr>
<td><strong>DuckAssistBot</strong></td>
<td><code>Mozilla/5.0 (compatible; DuckAssistBot/1.0; +<a href="https://duckduckgo.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.duckduckgo.com/bot.html</a>)</code></td>
<td><a href="https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot" target="_blank" rel="noopener nofollow noreferrer">Scrapes content for DuckAssist, DuckDuckGo's private AI answer feature</a></td>
</tr>
<tr>
<td><strong>YouBot</strong></td>
<td><code>Mozilla/5.0 (compatible; YouBot (+<a href="http://www.you.com" target="_blank" rel="noopener nofollow noreferrer">http://www.you.com</a>))</code></td>
<td>Crawler behind You.com's AI search and browser assistant</td>
</tr>
<tr>
<td><strong>meta-externalagent</strong></td>
<td><code>Mozilla/5.0 (compatible; meta-externalagent/1.1 (+<a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers" target="_blank" rel="noopener nofollow noreferrer">https://developers.facebook.com/docs/sharing/webmasters/crawler</a>))</code></td>
<td><a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers#identify-2" target="_blank" rel="noopener nofollow noreferrer">Meta's bot for collecting data to train or fine-tune LLMs</a></td>
</tr>
<tr>
<td><strong>Amazonbot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/600.2.5 (KHTML, like Gecko) Version/8.0.2 Safari/600.2.5 (Amazonbot/0.1; +<a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">https://developer.amazon.com/support/amazonbot</a>)</code></td>
<td><a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">Amazon's crawler for search and AI applications</a></td>
</tr>
<tr>
<td><strong>Applebot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Safari/605.1.15 (Applebot/0.1; +<a href="https://support.apple.com/kb/HT6619" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/go/applebot</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Apple's crawler for Spotlight, Siri, and Safari</a></td>
</tr>
<tr>
<td><strong>Applebot-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Applebot-Extended/1.0; +<a href="https://www.apple.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/bot.html</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Apple's AI-focused crawler for future AI models (opt-in)</a></td>
</tr>
<tr>
<td><strong>Bytespider</strong></td>
<td><code>Mozilla/5.0 (compatible; Bytespider/1.0; +<a href="https://www.bytedance.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bytedance.com/bot.html</a>)</code></td>
<td>ByteDance's AI data collector for TikTok and other services</td>
</tr>
<tr>
<td><strong>MistralAI-User</strong></td>
<td><code>Mozilla/5.0 (compatible; MistralAI-User/1.0; +<a href="https://mistral.ai/bot" target="_blank" rel="noopener nofollow noreferrer">https://mistral.ai/bot</a>)</code></td>
<td><a href="https://docs.mistral.ai/robots/" target="_blank" rel="noopener nofollow noreferrer">Mistral's real-time citation fetcher for "Le Chat" assistant</a></td>
</tr>
<tr>
<td><strong>cohere-ai</strong></td>
<td><code>Mozilla/5.0 (compatible; cohere-ai/1.0; +<a href="http://www.cohere.ai/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.cohere.ai/bot.html</a>)</code></td>
<td>Collects textual data for Cohere's language models</td>
</tr>
</tbody>
</table>

## Referrer analysis

<table>
<thead>
<tr>
<th><strong>Source</strong></th>
<th><strong>Referrer</strong></th>
<th><strong>Traffic Type</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td>chatgpt.com</td>
<td>Direct traffic from ChatGPT interface</td>
</tr>
<tr">
<td>Claude</td>
<td>claude.ai</td>
<td>Traffic from Anthropic's Claude interface</td>
</tr>
<tr>
<td>Google Gemini</td>
<td>gemini.google.com</td>
<td>Traffic from Google's AI assistant</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>copilot.microsoft.com</td>
<td>Traffic from Microsoft's AI assistant</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>m365.cloud.microsoft</td>
<td>Traffic from Microsoft's AI assistant (Microsoft 365 cloud services)</td>
</tr>
<tr >
<td>Perplexity AI</td>
<td>perplexity.ai</td>
<td>Traffic from AI search with citations</td>
</tr>
<tr>
<td>Meta AI</td>
<td>meta.ai</td>
<td>Traffic from Meta's AI assistant</td>
</tr>
</tbody>
</table>

### Query parameter

<table>
<thead>
<tr>
<th><strong>LLM Service</strong></th>
<th>Example URL</th>
<th><strong>Query Parameter</strong></th>
<th><strong>Example Value</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td ><a href="https://www.yoursite.com/product?utm_source=chatgpt.com" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/product?utm_source=chatgpt.com</a></td>
<td>utm_source</td>
<td><a href="https://openai.com/chatgpt/search-product-discovery/" target="_blank" rel="noopener nofollow noreferrer">chatgpt.com</a></td>
</tr>
<tr>
<td>Perplexity</td>
<td><a href="https://www.yoursite.com/article?utm_source=perplexity" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/article?utm_source=perplexity</a></td>
<td>utm_source</td>
<td>perplexity</td>
</tr>
</tbody>
</table>

