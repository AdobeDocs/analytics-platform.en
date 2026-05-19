---
title: Analyze Experience Platform Audiences In Customer Journey Analytics
description: Learn how to analyze Experience Platform audiences in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Audiences
role: Admin
exl-id: 095cae34-1337-464a-9682-3c899295c0a8
autotag-review: '2026-05-19T10:44:54.802Z'
TQID: 'https://experienceleague.adobe.com/ljj9CIUW58m27w8Mo9HlRJ0kgYXGIgqwuarPR2wNUjw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Analyze Experience Platform audiences in Customer Journey Analytics {#analyze-audiences-RTCDP}

After you [create an audience analysis configuration](/help/connections/audience-analysis/audience-analysis-configure.md), audience data becomes available as new dimensions in the data views where you configure them to be created. You can use the new audience dimensions anywhere in Analysis Workspace if you have access to a data view where the audience analysis dimensions were added.

## Use the Audience overview template

An Audience overview template is available in Customer Journey Analytics. 

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? Are they the dimensions available in the Audience overview template? (Audience Name, Audience Origin, Exited Audience Name, Exited Audience Origin; Audience Description, Exited Audience Description). Metrics included (Distinct Audiences) -->

For information about how to access the Audience overview template, see [Access and run a template](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template) in [Use templates](/help/analysis-workspace/templates/use-templates.md).

The Audience overview template contains the following panels:

## Usage overview panel

Shows data for all audiences with usage events that are associated with the selected data view. Audience membership data is updated daily from Experience Platform. Data is always shown for yesterday, so changing the panel date range results in inaccurate data. 

Use the table in this panel to better understand audience behavior. Drag the Audience Description dimension from the selected data view and add it as a breakdown. Or use any other interaction dimension (such as Page, Action, and so forth) as the breakdown.

## Top audience origins panel

Shows where the audience was created, whether in RTCDP, Customer Journey Analytics, and so forth.

Use the table in this panel to better understand how the audience origin might affect other factors. Drag the Audience Name dimension from the selected data view and add it as a breakdown. Or use any other interaction dimension (such as Page, Action, and so forth) as the breakdown.

## Audience overlap panel

Shows data for all audiences with usage events that are associated with the selected data view. Data is always shown for yesterday, so changing the panel date range results in inaccurate data. 

Select up to three audiences in the table in this panel to see how they overlap in the corresponding Venn diagram.

## Exited audience usage panel

Shows data for all exited audiences with usage events that are associated with the selected data view. Data is always shown for yesterday, so changing the panel date range results in inaccurate data. "Exited audiences" are audiences in which people with usage events left or exited yesterday. 

Use the table in this panel to better understand audience behavior. Drag the Exited Audience Description dimension from the selected data view and add it as a breakdown. Or use any other interaction dimension or metric (such as Page, Action, and so forth) as the breakdown.

## Top exited audience origins panel

Shows where each audience that exited was originally created, whether in RTCDP, Customer Journey Analytics, and so forth. 

Use the table in this panel to better understand how the audience origin might affect other factors. Drag the Exited Audience Name dimension from the selected data view and add it as a breakdown. Or use any other interaction dimension or metric (such as Page, Action, and so forth) as the breakdown.
