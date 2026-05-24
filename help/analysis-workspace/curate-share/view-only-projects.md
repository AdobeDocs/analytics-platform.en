---
description: Understand the experience of read-only projects in Analysis Workspace.
keywords: Read-only projects
title: Read-Only Projects
feature: Curate and Share
exl-id: 2bc26444-aeea-4695-92a5-a2b45ac18e0d
role: User
autotag-review: '2026-05-19T08:24:39.395Z'
TQID: 'https://experienceleague.adobe.com/unXy2ZoBYHCtuKNQ9VfM3iJEEjVUU-fr-XRQ7pci5fo'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: a3b826fd-7a63-4a83-8736-83eee6668f44
    internal-label: Curate and share, Curate and share (CJA)
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Read-only projects

You can share projects as read-only to recipients through the [share functionality](/help/analysis-workspace/curate-share/share-projects.md). Recipients placed in the **[!UICONTROL Read only]** role will receive a more limited project experience. 

This may be desired if you are sharing a project to users that are less familiar with your organization's data structure, Analysis Workspace or Customer Journey Analytics generally, but you still want them to consume data and insights in a safe environment. 

![Share as read-only](assets/read-only-project-sender.png)

The interactions for the read-only recipients are limited.

![Share as read-only received](assets/read-only-project-receiver.png)

## Disabled interactions

Disabled interactions in a view-only project include: 

* Hidden left panel 
* Panel calendar date range. Note: If you want to grant calendar control to recipients, add in a [drop-down segment with date ranges](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters.html). 
* Freeform segmenting 
* Freeform # of visible rows 
* Freeform row, column or visualization settings 
* Panel segments 
* Edit, Insert & Component menus
* Workspace tips

## Enabled interactions

Some of the more notable enabled interactions in a view-only project include: 

| Area | Enabled interactions |
| --- | --- |
| **Freeform tables** | <li>Pagination and sorting</li><li>Hovering</li><li>Cell selections that update linked visualizations</li><li>From the context menu > Get Visualization Link</li><li>From the context menu > Copy to Clipboard</li> |
| **Visualizations** | <li>Clicking to turn on/off legend</li><li>Hovering</li><li>From the context menu > Get Visualization Link</li><li>Collapse/expand</li><li>Flow - expand Flow nodes</li><li>Map - zoom</li></ul> |
| **Panels** | <li>Interactive drop-down segments</li><li>From the context menu > Get Panel Link</li><li>Collapse/expand</li> |
| **Project** | <li>Inspecting all info icons</li><li>Project menu - New, Open, Set as landing page, Refresh, Download CSV/PDF, limited Project Info & Settings</li><li>Share menu - Get project link, Send file now</li><li>Help menu - All actions except Tips & Debugger options</li> |


## Share with anyone experience

If you have selected a project using [Share with anyone](share-projects.md#share-a-project-with-anyone-no-login-required) the receiver of the link can only view the project and not interact with the project.

![Share with anyone experience](assets/share-with-anyone-receiver.png)
