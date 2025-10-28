---
title: Transition Guide
description: Learn how to transition from Customer Journey Analytics to Customer Journey Analytics B2B Edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
---
# Transition guide

This guide discusses how to transition from Customer Journey Analytics to the B2B Edition of Customer Journey Analytics.

The article assumes you already use Customer Journey Analytics to some extent:

* You have [connections](/help/connections/overview.md) that ingest data into Customer Journey Analytics.
* You have [data views](/help/data-views/data-views.md) that use the data from these connections.
* You have [projects](/help/analysis-workspace/home.md) with reports and visualizations leveraging these data views.

If you have not used Customer Journey Analytics before, refer to the [B2B Edition quick start guide](cja-b2b-quick-start-guide.md).

If you are an Adobe Analytics user and plan to use Customer Journey Analytics B2B Edition, first refer to the [upgrade from Adobe Analytics to Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md) documentation.


## Existing implementation

The existing implementation of Customer Journey Analytics does not change at all once you are licensed and provisioned for Customer Journey Analytics B2B Edition. 

All existing connections are considered [person-based connections](cja-b2b-concepts-features.md#connections-and-identifiers) and continue to work without any update. Everything that relies on the data from these person-based connections, such as data views, workspace projects, segments, scheduled exports, alerts, and more, continue to work as originally planned and intended.

>[!IMPORTANT]
>
>You are not able to change existing person-based connections to an account-based connection. A new account-based connection is required to make use of the B2B Edition features.
>


## Implement B2B features

To implement B2B features in your existing implementation, you need to follow these steps:

1. Model your B2B data. Customer Journey Analytics B2B Edition assumes at least account-based time-series event data, and benefits from additional profile or lookup record data. Such as account data, buying group data, opportunity data, marketing list member data, and more.

   * Define which identifier you want to use as the primary account identifier (Account ID). Often an existing CRM or other tool (for example: Demandbase) helps you to determine that identifier.
   * Identify additional identifiers for the other B2B data you plan to use: global account identifier, opportunity identifier, buying group identifier, and person identifier.

1. Prepare your B2B data. Ensure you add and collect account identifiers across all time-series event data and relevant record data. Similarly, ensure your time-series event data and lookup record contains other identifiers for relevant events. For example: an event that signals the move to another sales stage, should have an opportunity identifier. And that identifier should be part of your opportunity lookup data.

1. [Create a new account-based connection](/help/connections/create-connection.md#account-based-connection). Select which optional containers you want to include, [add datasets](/help/connections/create-connection.md#add-datasets) and define the [settings for each dataset](/help/connections/create-connection.md#dataset-settings). Use [match by container](cja-b2b-concepts-features.md#match-by-container) for lookup record datasets whenever that is possible.

1. [Create data views](/help/data-views/create-dataview.md) based on your new connection. 
 
   * Ensure you add all relevant fields as metrics or dimensions from the data you have ingested. 
   * Apply component settings (like persistence, attribution, and more) if so required. 
   * Add additional derived fields where appropriate. 

1. [Create workspace projects](/help/analysis-workspace/build-workspace-project/create-projects.md) to report and gain insights on your B2B data. Use specific B2B features, like [containers](cja-b2b-concepts-features.md#containers), to gain deep insights. 

   You can combine B2B (person-based) and B2B (account-based) reports and insights, through the use of multiple [panels](/help/analysis-workspace/c-panels/panels.md), in one workspace project.
