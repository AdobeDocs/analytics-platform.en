---
description: How to ask data analysis questions of Customer Journey Analytics documentation
title: Data Analysis AI Assistant in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
hidefromtoc: yes
hide: yes
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
---
# Data Analysis AI Assistant in Customer Journey Analytics - Alpha

The Data Analysis AI Assistant is a Generative AI conversation agent that can help you more quickly and efficiently answer questions you may have of your Analysis Workspace data in Customer Journey Analytics. 

When you ask a question in AI Assistant, the AI Assistant scans through all the components in your data view, including the different types of metrics and components, and translates your prompt into the right dimension, metric, and date range for your analysis. Instead of having to familiarize yourself with the data view components, and then drag and drop those components in the best combination to answer your question, you can simply type the question into the AI Assistant. 

![Data ANalysis AI Assistant](assets/cja-ai-asst-da.gif)

## In-scope vs. out-of-scope features for the Alpha version

### In-scope Alpha features

| Supported Feature | Description |
| --- | --- |
| **Build and update visualizations** | Generates a freeform table and associated visualization (e.g. line, bar, donut, etc).<p>Example: *What is the profit across SKUs from February to May?* |
| **Supported visualization types** | <ul><li>Line</li><li>Multi-line</li><li>Freeform</li><li>Bar</li><li>Donut</li><li>Summary Number</li></ul> |
| **Out-of-scope prompt detection** | If you submit a prompt that is out-of-scope, such as "export this project", the Assistant responds by letting you know that the question is out of scope. | 
| **Clarifying questions** | If you ask a question that does not have enough context for the AI Assistant to answer, or is too generic, the AI Assistant responds with a clarifying question and/or suggested options. Examples: <p>**Components**<ul><li>Metric: *Which "revenue" metric did you mean?*</li><li>Dimension: *Which of the below "regions" do you want to focus on?*</li><li>Filter: *Which "Account" filter did you want to apply?*</li><li>Date Range: *By "last month", did you mean the last full month or the last 30 days?*</li></ul>**Dimension items**: Which "store name" did you mean? (for example, Store #5274, Store #2949, etc.) |
| **Multi-turn** | The AI Assistant responds to a prompt with the context from the prior prompt(s), allowing users to update visualizations and ask follow-up questions.Example: <ul><li>Prompt 1: *Trend events from March.*</li><li>Prompt 2: *Show me the data from March to April instead*</li></ul> |
| **Verifiability** | Data verifiability and correctness can be confirmed via the generated freeform table and data visualization. For example, if a user asks *Trend orders last month*, you can confirm that correct metric ("orders") and date range ("last month") were selected in the newly generated panel, data visualization, and freeform table. |
| **Feedback** |<ul><li>Thumbs Up</li><li>Thumbs Down</li><li>Flag</li></ul> |

### Out-of-scope Alpha features 

| Unsupported Feature | Description |
| --- | --- |
| **In-line summary or or response** | The AI Assistant cannot respond in-line in the chat rail with a summary answer of a user prompt.Example out-of-scope prompts:<ul><li>*Give me a summary of the insights from my last prompt.*</li><li>*Summarize the highlights from the line visualization.*</li></ul> |
| **Clarifying questions** | Clarifying questions are limited to components and dimension items. The AI Assistant cannot clarify data views, visualizations, data granularity, comparison, scope, etc.. Without clarifying questions, the Assistant defaults to what you are most likely asking for. If it returns an unexpected visualization or data granularity, you can then use the multi-turn/update capability to adjust the visualization and data. |
| **Workspace Actions / Capabilities**| The AI Assistant cannot take actions for a user in Workspace aside from building and updating visualizations. For example, it cannot do any the following:<ul><li>Contextual action UI buttons (add to chart, new panel, new table)</li><li>Share</li><li>Export</li><li>Download</li><li>Manage user preferences</li><li>Curate</li><li>Manage data view</li><li>Analytics Dashboards app</li><li>Attribution</li></ul> |
| **Unsupported visualization types** | <ul><li>Flow</li><li>Fallout</li><li>Cohort Table</li><li>Area, Area Stacked</li><li>Bar stacked</li><li>Bullet</li><li>Combo</li><li>Histogram</li><li>Horizontal Bar, Horizontal Bar Stacked</li><li>Key Metric Summary</li><li>Scatter</li><li>Summary Change</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> | 

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

1. Go to [experience.adobe.com](https://experience.adobe.com/), and login with your Adobe ID.

2. Select **Customer Journey Analytics** from Experience Cloud Home

3. Click **[!UICONTROL Blank project]** in the banner at the top of the projects page to open a new blank project.

4. Ensure that the selected data view for the panel is the data view that was enabled for AI Assistant use for Alpha testing (reach out in the Alpha slack channel if you are unsure)

5. Click the AI Assistant chat icon at the top right.

   ![AI Assistant icon](/help/assets/ai-asst-icon.png)

6. In the **[!UICONTROL Ask about Customer Journey Analytics]** dialog at the bottom, ask a data analysis question in the AI Assistant.

### Example 1

For example, let's say you are interested in the orders your business received in July. 

1. Enter *"Trend orders in July."*

   ![AI prompt](/help/assets/ai-asst-prompt1.png)

2. The AI Assistant now gathers insights by looking through the data in the data view, including the metrics and components. It translates the prompt into the right dimension/s, metric/s, and data range.

   As you can see, it has automatically generated a Line graph and a freeform table showing orders for July.

   ![Answer to prompt - line graph and freeform table](/help/assets/ai-asst-result.png)

### Example 2

Next, you want to see how your revenue compares by region.

1. In the prompt window, enter *"Show revenue by region."*

2. The AI Assistant intelligently understands that by "region", you mean "customer region". It produces a bar chart that best shows revenue by region:

   ![Bar chart](/help/assets/ai-asst-result2.png)
   
### Example 3

Next, in addition to understanding revenue by region you also want to see data for profit by region. Instead of having to retype the last prompt, you can ask the AI Assistant to update the most recent visualization and freeform table. 

1. In the prompt window, type *"Add profit."*

2. The **[!UICONTROL Bar]** chart still provides the most concise answer, but the profit metric has been added as a column in the freeform table:

   ![Bar chart](/help/assets/ai-asst-result4.png)

### Example 4

Finally, let's look at revenue by product category.

1. In the prompt window, enter *"Proportion of revenue by product category".*

2. Again, the Data Analysis AI Assistant picks the most appropriate visualization, in this case the **[!UICONTROL Donut]** visualization, to answer the question.

   ![Donut](/help/assets/ai-asst-result3.png)

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

The AI Assistant processes the context provided by each user prompt and tries to respond intelligently with the most appropriate visualization as well as components in a freeform table. However, the AI Assistant's response can vary based on the specific words and phrases used in a prompt, so slight changes in language can lead to different results. Here’s how to make the most of it: <ul><li>Be Specific: Include exact terms (like “last month’s sales in California”) to narrow down the response.</li><li>Use Clear Metrics and Filters: Adding specific metrics (like “Revenue”), dimensions (e.g. "website name"), filters (such as “iPhone users”), and date ranges (like "last three months") helps the AI Assistant focus on the right data.</li><li>Ask Direct Questions: Phrasing questions directly, like “What is the average revenue by product category this year?” makes it easier for the AI Assistant to provide clear, relevant insights.</li></ul>

Please review the below table of example terms and phrases you can use in prompts with the Data Analysis AI Assistant in CJA, along with the types of responses you can expect. These examples are designed to help you get familiar with how specific words or structures can influence the AI Assistant's output, ensuring more precise and valuable insights. Please note that the AI Assistant uses Generative AI, so visualizations or selected data may vary slightly across similar prompts.
  
| Desired Outcome | Example Terms and Phrases |
| --- | --- |
| Summary Number Visualization | <ul><li>Total</li></ul> |
| Compare Components | <ul><li>Compare</li><li>VS</li><li>Contrast</li><li>Week-to-Week</li><li>Month-over-Month</li><li>Quarter-over-Quarter</li><li>Year-over-Year</li></ul> |
| Donut Visualization | <ul><li>Proportion</li><li>Share of</li><li>Distribution</li><li>Percentage</li><li>Contribution</li><li>Portion</li><li>Parts</li></ul> |
| Line Visualization | <ul><li>Trend</li><li>[Metric] in [Time Range]</li></ul> |
| Bar Visualization | <ul><li>[Metric] by [dimension]</li></ul> |

## Alpha testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. Think about the following when evaluating the response from the AI Assistant: 

* Chat rail response or template: Evaluate the textual response provided by the Assistant. Is the response appropriate given the context of your prompt(s)? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate/expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied filters those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given saying the question is out-of-scope, provide feedback on whether you think the out-of-scope message is appropriate given your prompt. Was your prompt actually in-scope? 

**For every response, please give a thumbs up or thumbs down, based on the response**

Following the thumbs up/down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Alpha slack channel: #aep-cja-ai-assistant-testers ???
