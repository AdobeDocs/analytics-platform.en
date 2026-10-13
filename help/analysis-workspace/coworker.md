---
title: Analyze and Build Workspace Projects with Coworker
description: Use Coworker in Analysis Workspace to summarize the open project, find insights, and build panels, tables, and segments from natural-language prompts.
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ae3aff40-b2f6-4df1-8c01-0b0720d1510f
    internal-label: AI Tools
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Use Coworker in Analysis Workspace

{{release-limited-testing}}

Coworker is available in a chat panel on the right side of Analysis Workspace. Coworker uses your current open project as context, so you can ask questions about your analysis without explaining what the project contains. 

You can ask Coworker for help understanding the project or for help building it out:

* **Understand a project**: Ask Coworker to do things like summarize the project, find insights, or explain a metric. 

* **Build out a project**: Ask Coworker to do things like add panels and tables, break down data, or create segments.

## Understand Coworker in Workspace

### Choose between Coworker in Workspace and the Coworker application

Coworker in Analysis Workspace has many of the same capabilities as the [CX Enterprise Coworker application](https://experienceleague.adobe.com/en/docs/cx-enterprise-coworker/content/chat/analytics-chat), including the skills that you have access to. However, there are important differences that determine when you might use one over the other:

| | Coworker in Analysis Workspace | CX Enterprise Coworker application |
| --- | --- | --- |
| **When to use** | You want to build a project that you plan to keep, share with other users, or update over time. | You want a quick answer. You might choose to turn the analysis into a Workspace project later, if needed. |
| **Context** | Project-focused<p>Uses the open Workspace project as its starting point. You can refer to and build off panels, tables, and components that are already in the project.</p> | Data view-focused<p>Uses the data views you have access to or those you set as a preference in Coworker memory. You describe what you want to analyze in your prompt.</p> |
| **Typical user** | Analysts who build and validate analysis in Workspace. | Business users who want answers, without needing to access or learn Analysis Workspace. |
| **Output** | Panels, tables, and components are added directly to the Workspace project. <p>As appropriate, answers can also be given in the chat.</p> | Answers and analyses are provided in the conversation, with the option to open in Analysis Workspace. |



## What you can do with Coworker

### Understand the open project

Coworker can see every panel and table in the open project. You can ask Coworker to:

* Summarize the project.
* Find insights and flag anomalies in the data.
* Run a root cause analysis on a panel.
* Explain how to do something in Analysis Workspace, such as how to add a line chart or how to color table cells based on their values.

### Build and edit the project

You can ask Coworker to:

* Create a Freeform panel with the dimensions, metrics, and date range that you specify.
* Add panels to the project. Coworker adds new panels without overwriting your existing panels.
* Break down a table, or add comparison columns.
* Change the date range or visualization type of a panel, such as changing a table to a line chart.
* Rename a panel.
* Apply an existing segment by name, create a segment from a plain-language description, or copy a segment and change its logic.
* Create date ranges and simple calculated metrics.
* Add descriptions or a Text visualization that contains insights to the project.
* Create a project with multiple panels, or copy a project and adapt it for a different audience or region.
* Save the project.

Coworker also shows its work. The segments, metrics, and filters that Coworker uses to answer a question are added to the project so that you can verify them.

### Example prompts {#example-prompts}

| Prompt | What Coworker does |
| --- | --- |
| *Summarize this project* | Provides a summary in the chat panel and offers to add it to the project as a Text visualization. |
| *Find insights in this project* | Provides insights in the chat panel and offers to add the findings to the project. |
| *Do a root cause analysis on the drop in mobile visits* | Provides the analysis in the chat panel and offers to add the findings to the project. |
| *How do I color cells based on their values?* | Explains the steps in the chat panel. |
| *Show me sessions by page* | Adds a new panel or table to the project. |
| *Break this table down by device* | Adds the breakdown to the table that you referenced. |
| *Change the date range of this panel to last month* | Updates the date range of the panel. |
| *Create a segment for visitors from Canada* | Creates the segment and adds it to the project. |
| *Delete the old panels* | Lists the panels that it plans to delete and waits for your confirmation before it deletes them. |

## Where Coworker places results

Coworker decides whether to answer in the chat panel or to change the project based on what you ask:

* **You say where you want the result**: Coworker follows your instruction. For example, include *in chat* or *just tell me* to get an answer in the chat panel, or include *add to the project* or *in this table* to change the project.

* **You ask Coworker to explain, summarize, or discuss**: Coworker answers in the chat panel. This includes requests such as *explain*, *summarize*, and *tell me more*. Root cause analysis and similar skills also stay in the chat panel until you ask Coworker to add the results to the project.

* **You ask Coworker to build or edit**: Coworker changes the project. This includes requests to add, create, edit, break down, or compare data, change a visualization type or date range, or create a segment.

When the placement isn't clear, Coworker explains what it's doing.

## Stay in control of Coworker

* **Clarifying questions**: When a request is vague or matches more than one component, Coworker asks a clarifying question or suggests options to choose from. For example, if more than one metric matches the name that you used, Coworker suggests the matching metrics.

* **Steer or stop a task**: While Coworker is working, press **Shift+Enter** to give it more direction, or press **Esc** to stop it.

* **Undo changes**: Ask Coworker to undo a specific change that it made to the project.

* **Confirmation before deletion**: Coworker lists the panels that it plans to delete and waits for your confirmation before it deletes them.

* **Edits that you make at the same time**: If you edit the project while Coworker is working, Coworker recognizes your changes.

* **Data quality notes**: Coworker includes data quality notes in its answers. For example, if you compare a month that has only just started to a full month, Coworker tells you that the comparison is based on partial data.

## Open Coworker in Analysis Workspace

1. In Customer Journey Analytics, open an existing Workspace project or create a new project.

1. **[PLACEHOLDER: How to open the Coworker panel, such as the icon name and location. Add a screenshot.]**

1. In the chat panel, describe what you want Coworker to do. See [Example prompts](#example-prompts) for ideas.

## Prerequisites

* **[PLACEHOLDER: Permissions and product profile requirements. Include the Admin Console steps to grant access, if applicable.]**

* **[PLACEHOLDER: Any additional requirements, such as whether the organization must have Coworker enabled.]**

Coworker uses your existing Analysis Workspace and data view permissions. It can't access data or components that you don't already have access to.

## Current limitations

Coworker in Analysis Workspace has the following limitations:

* **Segment definitions**: When you refer to a segment by name, Coworker doesn't know the definition of the segment. Coworker might infer what the segment contains based on its name. Verify the segment definition before you rely on the results.

* **Data Dictionary**: Coworker is not connected to the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md). It can't use the definitions in the Data Dictionary to explain metrics and dimensions.

* **Approved components**: Coworker doesn't give preference to approved components over similar components.

* **Copying panels**: Coworker can't copy or duplicate a panel.

* **New segments in the components list**: Segments that Coworker creates don't appear in the components list in the left rail until you refresh the page. Date ranges that Coworker creates appear without a refresh.

* **Anomaly detection**: When you ask Coworker to show anomalies on a visualization, the anomalies might not appear.

* **Conversation history**: Conversations are saved for each user, not with the project. Other users who open the project can't see your conversation with Coworker. To share context with other users, add it to the descriptions of the panels in the project.

* **Multiple browser tabs**: If you open the same conversation in more than one browser tab, Coworker might lose track of what it's working on.

* **Languages other than English**: In data views that use a language other than English, Coworker might use a mix of English and the data view language in its responses.


