---
title: Product usage overview
description: View insights and reports on how your organization uses Customer Journey Analytics.
hide: yes
hidefromtoc: yes
---
# Product usage overview

Product usage provides your organization with the ability to view analytics data on how your organization uses Customer Journey Analytics. Once enabled, the following Adobe Experience Platform components are automatically created and hooked up for you:

* A schema in Adobe Experience Platform
* A dataset in Adobe Experience Platform
* A connection in Customer Journey Analytics
* A data view in Customer Journey Analytics

All data collection and setup is automatically configured for you once enabled. Any time a user makes an action in Analysis Workspace, that action is tracked and available for reporting.

## Available dimensions

When you enable Product usage, the following dimensions are available:

| Dimension | Description |
| --- | --- |
| Action Name | The type of action that the user took. You can use this dimension as any desired metric by creating a copy in data view settings. |
| Attribution Model Used | The type of attribution model that the current component uses. |
| Component | A derived field. |
| Component Type | The type of component added, removed, or modified. |
| Connection | The connection that the project uses. |
| Data View | The data view that the project uses. |
| Feature | The feature that the project uses. |
| Identifier | The unique identifier for the event. |
| Login User | The user that took the action. |
| Panel Used | The panel where the component was added, removed, or modified. |
| Project | A derived field. |
| Project Name | The friendly name of the project. |
| Project Type | The project type. |
| User ID | The user ID that triggered the event. |
| Visualization Used | The visualization that was added, removed, or modified. | 

Product usage does not track individual project components when a project is merely opened or viewed. The user action of opening a project is tracked, however.
