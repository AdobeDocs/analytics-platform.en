---
description: How to ask questions of Customer Journey Analytics documentation
title: AI Assistant for Adobe Customer Journey Analytics
role: User, Admin
solution: Customer Journey Analytics
exl-id: 7a4f15c4-7fd6-4a6a-9b83-7c1f3b95be16
hide: yes
hidefromtoc: yes
---

# AI Assistant for Adobe Customer Journey Analytics

>[!NOTE]
>
>AI Assistant for Customer Journey Analytics is currently in Beta. The feature and its documentation are subject to change.

AI Assistant is a conversational experience that allows practitioners to perform tasks at a fast pace – whether its understanding concepts, troubleshooting problems, or searching through information. It also allows non-experts to perform expert tasks and increases the overall quality of work.

The AI Assistant in Customer Journey Analytics is trained on its Adobe Experience League documentation. When asked a question, AI Assistant responds with a helpful answer that enables quick learning.

As a novice user, you can use AI Assistant to learn Customer Journey Analytics concepts and onboard yourself to products and features that you are unfamiliar with. As an experienced user, you can use AI Assistant to present more advanced use cases or tips and tricks.

Some examples of concept questions include:

* What is the difference between batch and streaming ingestion?
* What is Customer Journey Analytics best used for?
* How do I set up a data view?

Questions outside the scope of Customer Journey Analytics, such as questions about other Adobe products like Adobe Target and the Adobe Creative Cloud Suite, cannot be answered. 

AI Assistant for Customer Journey Analytics is available to all product tiers.

## Product knowledge {#knowledge}

The product knowledge retrieval model is trained on Customer Journey Analytics. Other capabilities, such as data analysis, will be rolled out at a later date. 

| Product knowledge | Examples |
| --- | --- |
| Pointed learning |<ul><li>What is the difference between Adobe Analytics and Customer Journey Analytics?</li><li>How do I build a calculated metric?</li></ul> |
| Open discovery | <ul><li>How can I export a Workspace project?</li><li>How can I find duplicate Workspace components?</li></ul>  |
| Troubleshooting | <ul><li>How long does it take for data to come into CJA?</li><li>How many derived fields can I have in a Customer Journey Analytics connection?</li></ul>|

## Feature Access

In this first release, access to the AI Assistant feature is governed by the following parameters:

* **Solution access**: The AI Assistant is available in Customer Journey Analytics, but not in Adobe Analytics. It is also available in Adobe Experience Platform, Adobe Journey Optimizer, Adobe Real-Time CDP and additional Experience Platform apps.

* **Contractual access**: If you are not able to use AI Assistant, please contact your organization's administrator or Adobe Account Representative. Before AI Assistant can be used by your organization, your company must agree to certain GenAI-related legal terms.

* **Permissions**: In [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] "AI Assistant: Product Knowledge" permission determines access to this tool. 
A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in Admin Console:
   1. Navigate to [!UICONTROL Admin Console] > [!UICONTROL Products and services] > [!UICONTROL Customer Journey Analytics] > [!UICONTROL Product Profile] > [!UICONTROL Permissions] > [!UICONTROL Edit Reporting Tools].
   1. Add "AI Assistant: Product Knowledge".

## Access AI Assistant in the Customer Journey Analytics UI

1. To launch AI Assistant, select the AI Assistant icon from the top header of any page in the Customer Journey Analytics UI.

   ![AI Assistant icon](assets/ai-asst1.png)

   Upon using AI Assistant for the first time, a disclaimer appears with some terms and conditions for usage of the Assistant.

1. In the box provided, ask a specific natural-language question of the AI Assistant.

   ![Question box](assets/ai-asst2.png)

1. (Optional) To show sources, click **[!UICONTROL Show Sources]**, and the documentation source or sources that informed the answer are shown.

1. (Optional) You can also provide a thumbs-up or thumbs-down vote on the helpfulness of any given answer.
