---
description: How to ask data analysis questions of Customer Journey Analytics documentation
title: Data Analysis AI Assistant in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: yes
hide: yes
---

# Data Analysis AI Assistant in Customer Journey Analytics - Alpha

The Data Analysis AI Assistant is an intelligent, context-aware conversation agent that can help you more quickly and efficiently answer questions you may have of your Analysis Workspace data in Customer Journey Analytics. 

The Assistant looks through all the data in a data view, including the different types of metrics and components, and translates your prompt into the right dimension, metric, and date range for this analysis. Instead of having to familiarize yourself with the data view components, and then drag and drop those components in the best combination to answer your question, you can simply type the question into the AI Assistant. 

![Data ANalysis AI Assistant](assets/cja-ai-asst-da.gif)

## In-scope vs. out-of-scope features for the Alpha version

### In-scope features

| Supported Feature | Description |
| --- | --- |
| **Build and update visualizations** | Generates a freeform table and associated visualization (e.g. line, bar, donut, etc).<p>Example: *What is the profit across SKUs from February to May?* |
| **Supported visualization types** | <ul><li>Line</li><li>Multi-line</li><li>Freeform</li><li>Bar</li><li>Donut</li><li>Summary Number</li></ul> |
| **Out-of-scope prompt detection** | If you submit a prompt that is out-of-scope, such as "export this project", the Assistant responds by letting you know that the question is out of scope. | 
| **Clarifying questions** | If you ask a question that does not have enough context for the AI Assistant to answer, or is too generic, the AI Assistant responds with a clarifying question and/or suggested options. Examples: <p>**Components**<ul><li>Metric: *Which "revenue" metric did you mean?*</li><li>Dimension: *Which of the below "regions" do you want to focus on?*</li><li>Filter: *Which "Account" filter did you want to apply?*</li><li>Date Range: *By "last month", did you mean the last full month or the last 30 days?*</li></ul>**Dimension items**: Which "store name" did you mean? (for example, Store #5274, Store #2949, etc.) |
| **Multi-turn** | The AI Assistant responds to a prompt with the context from the prior prompt(s), allowing users to update visualizations and ask follow-up questions. Example: *Show me the data from March to April instead.* |
| **Feedback** |<ul><li>Thumbs Up</li><li>Thumbs Down</li><li>Flag</li></ul> |

### Out-of-scope features

| Unsupported Feature | Description |
| --- | --- |
| **In-line summary or or response** | The AI Assistant cannot respond in-line in the chat rail with a summary answer of a user prompt.Example out-of-scope prompts:<ul><li>*Give me a summary of the insights from my last prompt.*</li><li>*Summarize the highlights from the line visualization.*</li></ul> |
| **Clarifying questions** | Clarifying questions are limited to components and dimension items. The AI Assistant cannot clarify data views, visualizations, data granularity, comparison, scope, etc.. Without clarifying questions, the Assistant defaults to what you are most likely asking for. If it returns an unexpected visualization or data granularity, you can then use the multi-turn/update capability to adjust the visualization and data. |
| **Workspace Actions / Capabilities**| The AI Assistant cannot take actions for a user in Workspace aside from building and updating visualizations. For example, it cannot do any the following:<ul><li>Contextual action UI buttons (add to chart, new panel, new table)</li><li>Share</li><li>Export</li><li>Download</li><li>Manage user preferences</li><li>Curate</li><li>Manage data view</li><li>Analytics Dashboards app</li><li>Attribution</li></ul> |
| **Unsupported visualization types** | <ul><li>Flow</li><li>Fallout</li><li>Cohort Table</li><li>Area, Area Stacked</li><li>Bar stacked</li><li>Bullet</li><li>Combo</li><li>Histogram</li><li>Horizontal Bar, Horizontal Bar Stacked</li><li>Key Metric Summary</li><li>Scatter</li><li>Summary Change</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> | 
| **Explainability and Verifiability** | Transparent description or citation for how the AI Assistant generated a response, and providing you with a way to confirm that the answer is correct. |

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to the Data Analysis AI Assistant feature:

* **Solution access**: The Data Analysis AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data Analysis AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data Analysis]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data Analysis** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Access and use Data Analysis AI Assistant

1. Go to this link to open Workspace in the Labs IMS Org (in stage), and login with your Adobe ID.

1. Click **[!UICONTROL Blank project]** in the banner at the top of the projects page to open a new blank project.

1. Click the AI Assistant chat icon at the top right.

   ![AI Assistant icon](/help/assets/ai-asst-icon.png)

1. In the **[!UICONTROL Ask about Customer Journey Analytics]** dialog at the bottom, ask a data analysis question in the AI Assistant.

### Example 1

For example, let's say you are interested in the orders your business received in July. 

1. Enter "Show orders in July."

   ![AI prompt](/help/assets/ai-asst-prompt1.png)

1. The AI Assistant now gathers insights by looking through the data in the data view, including the metrics and components. It translates the prompt into the right dimension/s, metric/s, and data range.

   As you can see, it has automatically generated a Line graph and a freeform table showing orders for July.

   ![Answer to prompt - line graph and freeform table](/help/assets/ai-asst-result.png)

### Example 2

Next, you want to see how your revenue compares by region.

1. In the prompt window, enter "Show revenue by region."

2. The AI is smart enough to understand that by "region", you mean "customer region". It produces a bar chart that best shows revenue by region:

   ![Bar chart](/help/assets/ai-asst-result2.png)

### Example 3

Now, let's look at revenue by product category.

1. In the prompt window, enter "Show revenue by product category".

2. Again, the Data Analysis AI Assistant picks the most appropriate visualization, in this case the **[!UICONTROL Donut]** visualization, to answer the question.

   ![Donut](/help/assets/ai-asst-result3.png)

### Example 4

Finally, you want to know which SKU is the most profitable, and where you should invest marketing resources.

1. In the prompt window, ask "What is the profit across SKUs from February to May."

1. A simple **[!UICONTROL Bar]** chart provides the most concise answer:

   ![Bar chart](/help/assets/ai-asst-result4.png)

## Example data analysis prompts

Here are some examples of common prompts, and which visualization the AI Assistent uses to respond to those prompts.

| Example prompt | Expected visualization |
| --- | --- |
| Show me profits in [Month] | Line<p>Asking for a trend or metric within a certain time range by default returns a line visualization. |
| Trend orders in [Month] | Line |
| Show revenue by region in [Month] | Bar |
| Share of revenue by product category | Donut |
| Orders by day of week, from January to May | Bar |
| Show orders by gender, from March to June | Bar |
| What is the profit across SKUs from February to May | Bar |
| Revenue by store name in [Month] | Bar |
| What were my top 10 SKUs by profit in [Month]? | Bar |
| Proportion of purchases by month of year | Donut |
| Total profit in [Month] | Summary Number<p>Asking for the "total" of a metric across a certain time range should return a Summary number visualization. |


## Prompting best practices

TBD

## Alpha testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback.

Evaluate the response: is the answer given correct? 

If the Assistant responds in the chat rail: Evaluate the textual response.

* If a visualization/chart is shown: evaluate the visualization. Is it the appropriate/expected visualization for your question? 

* If a freeform table is shown: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied filters those that you requested or expected? 

* If a generic error message is given saying the question is out-of-scope, provide feedback on whether you think the out-of-scope message is appropriate given your prompt. Was your prompt actually in-scope? 

For every response, give a thumbs up or thumbs down, based on the response

Following the thumbs up/down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Email `taylorb@adobe.com` (PM)
* Send questions and feedback in the Alpha slack channel: #aep-cja-ai-assistant-testers ???


