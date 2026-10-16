---
title: Analyze and Build Workspace Projects with Coworker
description: Use the in-product experience for Coworker to summarize the open project, find insights, and build panels, tables, and segments from natural-language prompts.
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hold: true
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
# Use the in-product experience for Coworker

{{release-limited-testing}}

The in-product experience for Coworker is available in a chat panel on the right side of Analysis Workspace. Coworker uses the open project as context, so you can ask about your analysis or have Coworker build out the project without needing to explain what it contains.

## Understand Coworker in Workspace

### Prerequisites

* **Coworker is enabled for your organization**: The in-product experience for Coworker is disabled by default. A Customer Journey Analytics administrator must enable it for the organization before users can access it.

  If you can't access Coworker in Workspace, contact your administrator. For more information, see [IMS Organization preferences](/help/analysis-workspace/user-preferences.md#ims-organization-preferences). <!-- need to update this section with the new toggle -->

<!-- FOLLOW-UP: Coworker permissions are still being finalized. The Coworker permission name below is a placeholder. Confirm the name, category, and Admin Console steps with the SME. -->

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL Coworker]** permission determines access to Coworker. A [product profile administrator](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) must add this permission to your product profile. For more information, see [Access control](/help/technotes/access-control.md#access-control).

* **Data view access**: Coworker uses your existing Analysis Workspace and data view permissions. It can't access data or components that you don't already have access to.

### Choose between Coworker in Workspace and the Coworker application

The in-product experience for Coworker has many of the same capabilities as the [CX Enterprise Coworker application](https://experienceleague.adobe.com/en/docs/coworker/content/chat/use-cases/data-insights/analytics-chat), including the skills that you have access to. However, there are important differences that determine when you might use one over the other:

| | In-product experience for Coworker | Coworker application |
| --- | --- | --- |
| **When to use** | You want to build a project that you plan to keep, share with other users, or update over time. | You want a quick answer. You might choose to turn the analysis into a Workspace project later, if needed. |
| **Context** | Project-focused<p>Uses the open Workspace project as its starting point. You can refer to and build on panels, tables, and components that are already in the project.</p> | Data view-focused<p>Uses the data views you have access to or those you set as a preference in Coworker memory. You describe what you want to analyze in your prompt.</p> |
| **Typical user** | Analysts who build and validate analysis in Workspace. | Business users who want answers without needing to access or learn Workspace. |
| **Output** | Coworker adds panels, tables, and components directly to the Workspace project. <p>When appropriate, it also answers in the chat.</p> | Answers and analyses are provided in the conversation, with the option to open in Analysis Workspace. |

### What you can do with Coworker

#### Ask questions about the open project

You can ask Coworker questions like:

* Summarize the project.
* Find insights and flag anomalies in the data.
* Run a root cause analysis on a panel.
* Explain how to do something in Analysis Workspace, such as how to add a line chart or how to color table cells based on their values.
* Explain a component, such as a metric or dimension.

For more information, see [Ask questions about a project](#ask-questions-about-a-project).

#### Build and edit the open project

You can ask Coworker to do things like:

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

For more information, see [Update a project](#update-a-project).

### When Coworker updates the project or answers in the chat

Coworker decides whether to answer in the chat panel or to change the project based on what you ask. For more information, see [Update a project](#update-a-project) and [Ask questions about a project](#ask-questions-about-a-project).

You can also be explicit about what you want Coworker to do. For example, you can use phrases like _in chat_ or _just tell me_ to get an answer in the chat panel, or phrases like _add to the project_ or _in this table_ to update the project.

## Use Coworker with your projects

Coworker can see every panel and table in the open project. You can ask Coworker to answer questions about the project or to help you update it.

>[!TIP]
>
>You can interrupt Coworker or update the project at any time:
>
>* **Steer or stop a task**: While Coworker is working, press **Shift+Enter** to give it more direction, or press **Esc** to stop it.
>
>* **Make updates to a project in Workspace**: If you edit the project while Coworker is working, Coworker recognizes your changes.

### Update a project

When you ask Coworker to build or edit something in the project, Coworker updates the project accordingly. This includes requests that begin with words like _add_, _create_, _edit_, _break down_, _change_, and _compare_. For example, you can ask Coworker to add panels and tables, break down data, or create segments.

1. In Customer Journey Analytics, open an existing Workspace project or create a new project.

1. Select the **Coworker** icon ![Ask Coworker](/help/assets/icons/coworker.svg) in the upper-right corner of the header to open the Coworker chat panel.

1. In the chat panel, describe what you want Coworker to do.

   The following table lists example prompts.

   | Prompt | What Coworker does |
   | --- | --- |
   | _Show me sessions by page for last month_ | Adds a new Freeform panel with the dimension, metric, and date range that you specify. Existing panels aren't overwritten. |
   | _Break this table down by device_ | Adds the breakdown to the table that you referenced. |
   | _Add a comparison to last month in this table_ | Adds a comparison column to the table that you referenced. |
   | _Change the date range of this panel to last month_ | Updates the date range of the panel. |
   | _Change this table to a line chart_ | Changes the visualization type of the panel. |
   | _Rename this panel to Mobile performance_ | Renames the panel. |
   | _Apply the Mobile users segment to this panel_ | Applies the existing segment to the panel. Coworker doesn't know the segment definition, so verify that the segment contains what you expect. |
   | _Create a segment for visitors from Canada_ | Creates the segment and adds it to the project. The segment appears in the components list after you refresh the page. |
   | _Copy the Canada visitors segment and change it to visitors from Mexico_ | Creates a copy of the segment with the updated logic and adds it to the project. |
   | _Create a date range for the last 6 weeks_ | Creates the date range. The date range appears in the components list without a refresh. |
   | _Create a calculated metric for revenue per session_ | Creates the calculated metric. Coworker can create simple calculated metrics. |
   | _Add a description to this panel that explains the drop in visits_ | Adds the description to the panel. |
   | _Add a Text visualization with the key insights_ | Adds a Text visualization that contains the insights to the project. |
   | _Create a project with panels for traffic, conversion, and revenue_ | Creates a project with a panel for each area that you describe. |
   | _Copy this project and adapt it for the EMEA region_ | Creates a copy of the project and adapts it for the region that you specify. |
   | _Save the project_ | Saves the project. |
   | _Undo the breakdown you added_ | Undoes the change that you specify. |
   | _Delete the old panels_ | Lists the panels that it plans to delete and waits for your confirmation before it deletes them. |

1. Review the changes that Coworker made to the project. For more information, see [Verify Coworker results](#verify-coworker-results).

### Ask questions about a project

When you ask questions about a project, Coworker answers in the chat panel. This includes requests such as _explain_, _summarize_, _discuss_, and _tell me more_. Results from root cause analysis and similar skills also stay in the chat panel until you ask Coworker to add them to the project.

1. In Customer Journey Analytics, open an existing Workspace project or create a new project.

1. Select the **Coworker** icon ![Ask Coworker](/help/assets/icons/coworker.svg) in the upper-right corner of the header to open the Coworker chat panel.

1. In the chat panel, describe what you want Coworker to do.

   The following table lists example prompts.

   | Prompt | What Coworker does |
   | --- | --- |
   | _Summarize this project_ | Provides a summary in the chat panel and offers to add it to the project as a Text visualization. |
   | _Find insights in this project_ | Provides insights in the chat panel and offers to add the findings to the project. |
   | _Flag any anomalies in this panel_ | Describes the anomalies in the chat panel. If you ask Coworker to show anomalies on a visualization, the anomalies might not appear. See [Current limitations](#current-limitations). |
   | _Do a root cause analysis on the drop in mobile visits_ | Provides the analysis in the chat panel and offers to add the findings to the project. |
   | _How do I color cells based on their values?_ | Explains the steps in the chat panel. |
   | _Explain the Bounce rate metric_ | Explains the component in the chat panel. The explanation doesn't come from the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md). Support for Data Dictionary definitions is planned for a future release. |

1. Review the answer that Coworker provides. For more information, see [Verify Coworker results](#verify-coworker-results).

## Verify Coworker results

Coworker helps you check the accuracy of its results. Keep the following in mind as you review them:

* **Coworker shows its work**: The segments, metrics, and filters that Coworker uses to answer a question are added to the project so that you can verify them.

* **Clarifying questions**: When a request is vague or matches more than one component, Coworker asks a clarifying question or suggests options to choose from. For example, if more than one metric matches the name that you used, Coworker suggests the matching metrics.

* **Data quality notes**: Coworker includes data quality notes in its answers. For example, if you compare a month that has only just started to a full month, Coworker tells you that the comparison is based on partial data.

## Current limitations

The in-product experience for Coworker has the following limitations:

* **Segment definitions**: When you refer to a segment by name, Coworker doesn't know the definition of the segment. Coworker might infer what the segment contains based on its name. Verify the segment definition before you rely on the results.

* **Data Dictionary**: Coworker isn't connected to the [Data Dictionary](/help/components/data-dictionary/data-dictionary-overview.md). It can't use the definitions in the Data Dictionary to explain metrics and dimensions.

* **Approved components**: Coworker doesn't give preference to approved components over similar components.

* **Copying panels**: Coworker can't copy or duplicate a panel.

* **New segments in the components list**: Segments that Coworker creates don't appear in the components list in the left rail until you refresh the page. Date ranges that Coworker creates appear without a refresh.

* **Anomaly detection**: When you ask Coworker to show anomalies on a visualization, the anomalies might not appear.

* **Conversation history**: Conversations are saved for each user, not with the project. Other users who open the project can't see your conversation with Coworker. To share context with other users, add it to the descriptions of the panels in the project.

* **Multiple browser tabs**: If you open the same conversation in more than one browser tab, Coworker might lose track of what it's working on.

* **Languages other than English**: In data views that use a language other than English, Coworker might use a mix of English and the data view language in its responses.


