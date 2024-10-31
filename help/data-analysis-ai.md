---
description: How to ask data analysis questions of Customer Journey Analytics documentation
title: Data Analysis AI Assistant in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: yes
hide: yes
---

# Data Analysis AI Assistant in Customer Journey Analytics - Alpha

The Data Analysis AI Assistant is an intelligent, context-aware conversation agent that can help you more quickly and efficiently answer questions you may have of your Analysis Workspace data in Customer Journey Analytics. The Assistant looks through all the data in a data view, including the different types of metrics and components, and translates your prompt into the right dimension, metric, and date range for this analysis. Instead of having to familiarize yourself with the data view components, and then drag and drop those components in the best combination to answer your question, you can simply type the question into the AI Assistant. 

## In-scope vs. out-of-scope features for the Alpha version

In-scope features:

| Supported Feature | Description |
| --- | --- |
| Build and update visualizations | Generates a freeform table and associated visualization (e.g. line, bar, donut, etc).<p>Example: *What is the profit across SKUs from February to May?* |
| Supported visualization types | Line, Multi-line, Freeform, Bar, Donut, Summary number visualizations |
| Out-of-scope prompt detection | If you submit a prompt that is out-of-scope, such as "export this project", the Assistant responds by letting you know that the question is out of scope. | 
| Clarifying questions | If you ask a question that does not have enough context for the AI Assistant to answer, or is too generic, the AI Assistant responds with a clarifying question and/or suggested options. Examples: <p>**Components**<ul><li>Metric: *Which "revenue" metric did you mean?*</li><li>Dimension: *Which of the below "regions" do you want to focus on?*</li><li>Filter: *Which "Account" filter did you want to apply?*</li><li>Date Range: *By "last month", did you mean the last full month or the last 30 days?*</li></ul>**Dimension items**: Which "store name" did you mean? (for example, Store #5274, Store #2949, etc.) |
| Multi-turn | The AI Assistant responds to a prompt with the context from the prior prompt(s), allowing users to update visualizations and ask follow-up questions. Example: *Show me the data from March to April instead.* |
| Feedback |<ul><li>Thumbs Up</li><li>Thumbs Down</li><li>Flag</li></ul> |

Out-of-scope features:

| Unsupported Feature | Description |
| --- | --- |
| In-line summary or or response | The AI Assistant cannot respond in-line in the chat rail with a summary answer of a user prompt.Example out-of-scope prompts:<ul><li>*Give me a summary of the insights from my last prompt.*</li><li>*Summarize the highlights from the line visualization.*</li></ul> |
| Clarifying questions | Clarifying questions are limited to components and dimension items. The AI Assistant cannot clarify data views, visualizations, data granularity, comparison, scope, etc.. Without clarifying questions, the Assistant defaults to what the user is most likely asking for. If it returns an unexpected visualization or data granularity, the user can then use the multi-turn/update capability to adjust the visualization and data. |
| Workspace Actions / Capabilities | The AI Assistant cannot take actions for a user in Workspace aside from building and updating visualizations. For example, it cannot do any the following:<ul><li>Contextual action UI buttons (add to chart, new panel, new table)</li><li>Share</li><li>Export</li><li>Download</li><li>Manage user preferences</li><li>Curate</li><li>Manage data view</li><li>Analytics Dashboards app</li><li>Attribution</li></ul> |
| Unsupported visualization types | 

## Feature access in the Customer Journey Analytics UI

TBD

## Example Data analysis prompts

Here are some examples of how the AI Assistent responds to prompts:

## Prompting best practices

TBD

## Alpha testing expectations and requested feedback

TB D

## Questions and Contact

Email `taylorb@adobe.com` (PM)
Send questions and feedback in the Alpha slack channel




