---
title: Frequently Asked Question On Attribution
description: Get answers to commonly asked questions about attribution.
feature: Attribution
role: User, Admin
exl-id: 8e05957a-f954-4e61-aeed-cd2bd2fe11f8
TQID: https://experienceleague.adobe.com/AY9LM5Beia2e9FrGZ5gF3Ao6qVzIe3raOQuB9qP-rOg
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---
# Frequently asked questions

Here are answers to commonly asked questions about attribution.

+++What is the *None* line item when using attribution?

The *None* line item is a catch-all item that represents all conversions that happened without any touch points within the lookback window. To reduce the number of conversions attributed to the *None* line item, try using a longer lookback window.

+++


+++Are attribution models available in other Analytics capabilities?

Yes. Attribution models are also available as part of the component settings for a metric component in a data view. See [Attribution component settings](/help/data-views/component-settings/attribution.md). For dimension components, you can use persistence. Persistence is the ability for a given dimension value to attribute to a metric beyond the event it is set on. It uses a combination of allocation and expiration. See [Persistence component settings](/help/data-views/component-settings/persistence.md) for more information

+++


+++What dimensions and metrics are supported?

Attribution is supported on all non-standard metrics that you have defined in your data view.

+++



+++Does attribution work with lookup data?

Yes, dimensions from lookup data are fully supported.

+++
