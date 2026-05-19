---
description: Understand how an inter-dimensional flow lets you examine user paths across various dimensions.
title: Inter-Dimensional Flows
feature: Visualizations
exl-id: 459166b1-a522-45b6-9d2c-69e3409e442e
role: User
autotag-review: '2026-05-19T08:41:06.716Z'
TQID: 'https://experienceleague.adobe.com/1er03t5uOypgXP6sjFW3z7vbN8IucVak2OiDeUG-OaU'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
subfeature_v2:
  - id: ddf59f64-0e46-4986-a525-056acc143c70
    internal-label: Workspace visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Inter-dimensional flows

An inter-dimensional flow lets you examine user paths across various dimensions. This article shows how to use this flow for two use cases: mobile app interactions and events, and how campaigns drive web visits

<!--
A dimension label at the top of each Flow column makes using multiple dimensions in a flow visualization more intuitive:

![An intero-dimensional flow highlighting multiple dimensions including Product, Page, OS version, and Time Spent.](assets/flow.png)
-->

## Mobile app interactions and events

The [!UICONTROL Screen Name] dimension is used in this example flow to see how users use the various screens (scenes) in the app. The top screen returned is **[!UICONTROL luma: content: ios: en: home]**, which is the home page of the app:

![A flow showing the Item Added.](assets/flowapp.png)

To explore the interaction between screens and event types (like add to cart, purchases, and others) in this app, drag and drop the **[!UICONTROL Event Types]** dimension:

* On top of any available step in the flow, to replace that dimension:

  ![A flow showing the Page dimension dragged dragged to the multiple areas.](assets/flowapp-replace.png)

* Outside of the current flow visualization, to add the dimension:

  ![A flow showing the Page dimension dragged to the white space at the end.](assets/flowapp-add.png)

The flow visualization below shows the result of adding the **[!UICONTROL Event Types]** dimension. The visualization provides insights to how mobile app users move through various screens in the app before adding products to a cart, close the application, are presented an offer, and more.

![A fLow showing the Page dimension results at the top of the list.](assets/flowapp-result.png)

## How campaigns drive web visits

You want to analyze which campaigns drive visits to the web site. You create a flow visualization with the **[!UICONTROL Campaign Name]** as the dimension

![Flow web campaign name dimension](assets/flowweb.png)

You replace the last **[!UICONTROL Campaign Name]** dimension with the **[!UICONTROL Formatted Page Name]** dimension and add another **[!UICONTROL Formatted Page Name]** dimension at the end of the flow visualization.

![Flow web campaign name and web page dimension](assets/flowweb-replace.png)

You can hover over any of the flows to see more details. For example which campaigns have resulted in a Cart checkout.

![Flow web campaign name and web page dimension hover](assets/flowweb-hover.png)
