---
title: Scope Component Settings
description: Configure how a a component is scoped for total population reporting.
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
---

# Scope component settings {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="Scope"
>abstract="Determine how a component is scoped when used in reports. You can select between event-based, profile-based, or total-based."

The scope of a metric component determines how the component is used in reports. 

| Scope | Description |
|---|---|
| Event-based | The scope of the metric component is event-based. |
| Profile-based | The scope of the metric component is profile based. When the component is used in reporting, the metric returns the population from your profile data, regardless of the date range applied to the panel. Date filters and date-range comparisons do not affect the reporting of this metric. |
| Total-based | The scope of the metric component is profile and event based. When the component is used in reporting, the metric returns the population from your profile and event data, regardless of the date range applied to the panel. Date filters and date-range comparisons do not affect the reporting of this metric. |

