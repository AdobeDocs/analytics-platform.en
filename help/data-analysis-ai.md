---
description: How to ask data analysis questions of Customer Journey Analytics documentation
title: Data Analysis AI Assistant in Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
feature: AI Tools
hidefromtoc: yes
hide: yes
exl-id: 262d5f15-16cb-4851-a769-7dbd205b2f81
---
# Visualize data with the AI Assistant in Customer Journey Analytics

The AI Assistant in Customer Journey Analytics is a generative AI conversation agent that quickly and efficiently answers questions about your data. It builds relevant visualizations in Analysis Workspace using components from your data view and using your actual data.

Using the AI Assistant to answer data-centric questions in Analysis Workspace can save countless hours that you might otherwise spend manually building visualizations in Analysis Workspace and familiarizing yourself with your data view components. 

![Data Analysis AI Assistant](assets/cja-ai-asst-da.gif)

## In-scope vs. out-of-scope features for the Alpha version

### In-scope Alpha features

| Supported feature | Description |
| --- | --- |
| **Build and update visualizations** | Generates a freeform table and associated visualization (such as a line, bar, donut, and so forth).<p>Example: *What is the profit across SKUs from February to May?* |
| **Supported visualization types** | <ul><li>Line</li><li>Multi-line</li><li>Freeform table</li><li>Bar</li><li>Donut</li><li>Summary number</li></ul> |
| **Out-of-scope prompt detection** | If you submit a prompt that is out of scope, such as "export this project," the Assistant responds by letting you know that the question is out of scope. | 
| **Clarifying questions** | If you ask a question that does not have enough context for the AI Assistant to answer, or is too generic, the AI Assistant responds with a clarifying question or suggested options. Examples: <p>**Components**<ul><li>Metric: *Which "revenue" metric did you mean?*</li><li>Dimension: *Which of the below "regions" do you want to focus on?*</li><li>Filter: *Which "Account" filter did you want to apply?*</li><li>Date Range: *By "last month," did you mean the last full month or the last 30 days?*</li></ul>**Dimension items**: Which "store name" did you mean? (For example, Store #5274, Store #2949, and so forth.) |
| **Multi-turn** | The AI Assistant responds to a prompt with the context from any prior prompts, allowing users to update visualizations and ask follow-up questions. Example: <ul><li>Prompt 1: *Trend events from March.*</li><li>Prompt 2: *Show me the data from March to April instead*</li></ul> |
| **Verifiability** | Data verifiability and correctness can be confirmed via the generated freeform table and data visualization. For example, if a user asks *Trend orders last month*, you can confirm that the correct metric ("orders") and date range ("last month") were selected in the newly generated panel, data visualization, and freeform table. |
| **Feedback** |<ul><li>Thumbs up</li><li>Thumbs down</li><li>Flag</li></ul> |

### Out-of-scope Alpha features 

| Unsupported feature | Description |
| --- | --- |
| **In-line summary or response** | The AI Assistant cannot respond in-line in the chat rail with a summary answer of a user prompt. Example out-of-scope prompts:<ul><li>*Give me a summary of the insights from my last prompt.*</li><li>*Summarize the highlights from the line visualization.*</li></ul> |
| **Clarifying questions** | Clarifying questions are limited to components and dimension items. The AI Assistant cannot clarify things such as data views, visualizations, data granularity, comparison, and scope. When clarifying questions cannot be used, the Assistant defaults to what you are most likely asking for. If it returns an unexpected visualization or data granularity, you can then use the multi-turn / update capability to adjust the visualization and data. |
| **Workspace actions / Capabilities**| The AI Assistant cannot take actions for a user in Workspace aside from building and updating visualizations. For example, it cannot do any of the following:<ul><li>Contextual action UI buttons (add to chart, new panel, new table)</li><li>Share</li><li>Export</li><li>Download</li><li>Manage user preferences</li><li>Curate</li><li>Manage data view</li><li>Analytics Dashboards app</li><li>Attribution</li></ul> |
| **Unsupported visualization types** | <ul><li>Flow</li><li>Fallout</li><li>Cohort Table</li><li>Area, Area Stacked</li><li>Bar Stacked</li><li>Bullet</li><li>Combo</li><li>Histogram</li><li>Horizontal Bar, Horizontal Bar Stacked</li><li>Key Metric Summary</li><li>Scatter</li><li>Summary Change</li><li>Text</li><li>Treemap</li><li>Venn</li></ul> | 

<!---## Feature access in the Customer Journey Analytics UI

[Do we even need this section for the Alpha?]

The following parameters govern access to Data visualization in AI Assistant:

* **Solution access**: Data visualization in AI Assistant is available for Customer Journey Analytics Prime and Ultimate customers. It is not available in Adobe Analytics. 

It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before your organization can use Data visualization in AI Assistant, your must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL AI Assistant: Data visualization]** permission determines access to this tool. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**
   1. Select the title of the product profile for which you want to provide access to [!UICONTROL AI Assistant: Product Knowledge].
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **AI Assistant: Data visualization** to **[!UICONTROL Included permission items]**.
   
      ![Add permission](assets/ai-assistant-permissions.png).

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.--->

## Access and use data visualization in AI Assistant

1. Go to [experience.adobe.com](https://experience.adobe.com/) and login with your Adobe ID.

2. Select **Customer Journey Analytics** from Experience Cloud Home.

3. Select **[!UICONTROL Blank project]** in the banner at the top of the projects page to open a new blank project.

4. Ensure that the selected data view for the panel is the same data view that was enabled for use with the AI Assistant for Alpha testing. 

   If you are unsure, contact the Alpha Slack channel.

5. Select the AI Assistant chat icon at the top-right area of the page. 

   If you do not see the chat icon, contact your administrator so they can enable the following features in the Admin Conole:
   
   * **[!UICONTROL AI Assistant: Product Knowledge]**

   * **[!UICONTROL AI Assistant: Data Analysis]**
   
   For additional details, administrators can see [these instructions](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/access). 

   ![AI Assistant icon](/help/assets/ai-asst-icon.png)

6. In the **[!UICONTROL Ask about Customer Journey Analytics]** dialog at the bottom of the page, ask a data visualization question in the AI Assistant.
 
   For more information, see the following examples.

### Example 1

For example, let's say you are interested in the orders your business received in July. 

**Prompt:** Enter *"Trend orders in July."*

   ![AI prompt](/help/assets/ai-asst-prompt1.png)

**Response:** The AI Assistant gathers insights by looking through the data in the data view, including the metrics and components. It translates the prompt into the right dimensions and metrics within the data range.

   As you can see, it automatically generated a line graph and a freeform table to show orders for July.

   ![Answer to prompt - line graph and freeform table](/help/assets/ai-asst-result.png)

### Example 2

Next, you want to see how your revenue compares by region.

**Prompt:** In the prompt window, enter *"Show revenue by region."*

**Response:** The AI Assistant intelligently understands that by "region," you mean "customer region." It produces a bar chart that best shows revenue by region:

   ![Bar chart](/help/assets/ai-asst-result2.png)
   
### Example 3

Next, in addition to understanding revenue by region you also want to see data for profit by region. Instead of repeating the previous prompt, you can ask the AI Assistant to update the most recent visualization and freeform table. 

**Prompt:** In the prompt window, type *"Add profit."*

**Response:** The **[!UICONTROL Bar]** chart still provides the most concise answer, but the profit metric has been added as a column in the freeform table:

   ![Bar chart](/help/assets/ai-asst-result4.png)

### Example 4

Finally, let's look at the revenue by product category.

**Prompt:** In the prompt window, enter *"Proportion of revenue by product category."*

**Response:** Again, data visualization in AI Assistant picks the most appropriate visualization, in this case the **[!UICONTROL Donut]** visualization, to answer the question.

   ![Donut](/help/assets/ai-asst-result3.png)

## Example data visualization prompts

Following are some examples of common prompts and the visualizations used by the AI Assistant to respond to those prompts.

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

The AI Assistant processes the context provided by each user prompt and tries to respond intelligently with the most appropriate visualization and components in a freeform table. 

Responses can vary based on the specific words and phrases used in the prompt, and slight changes in language can lead to different results. 

To achieve the best results, consider the following guidelines: 

* Be specific: Include exact terms to narrow down the response. Following is an example of a specific prompt: "Last month's sales in California"

* Use clear metrics and filters: Adding specific metrics (such as "Revenue"), dimensions (such as "website name"), filters (such as "iPhone users"), and date ranges (such as "last three months") helps the AI Assistant focus on the right data.

* Ask direct questions: Phrasing questions directly makes it easier for the AI Assistant to provide clear, relevant insights. Following is an example of asking a direct question in a prompt: "What is the average revenue by product category this year?" 

Review the following table of example terms and phrases that you can use in prompts with data visualization in AI Assistant, along with the types of responses you can expect. 

These examples are designed to help you get familiar with how specific words or structures can influence the AI Assistant's output, ensuring more precise and valuable insights. The AI Assistant uses generative AI, so visualizations or selected data may vary slightly across similar prompts.
  
| Desired outcome | Example terms and phrases |
| --- | --- |
| Summary number visualization | <ul><li>Total</li></ul> |
| Compare components | <ul><li>Compare</li><li>VS</li><li>Contrast</li><li>Week-to-Week</li><li>Month-over-Month</li><li>Quarter-over-Quarter</li><li>Year-over-Year</li></ul> |
| Donut visualization | <ul><li>Proportion</li><li>Share of</li><li>Distribution</li><li>Percentage</li><li>Contribution</li><li>Portion</li><li>Parts</li></ul> |
| Line visualization | <ul><li>Trend</li><li>[Metric] in [Time range]</li></ul> |
| Bar visualization | <ul><li>[Metric] by [Dimension]</li></ul> |

## Alpha testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from the AI Assistant: 

* Chat rail response or template: Evaluate the textual response provided by the Assistant. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied filters those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Alpha Slack channel: #cja-assistant-data-alpha
