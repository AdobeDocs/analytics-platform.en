---
title: Create a data view
description: Describes how to create a data view to a Platform dataset in Customer Journey Analytics (CJA).
---

# Create a data view

A data view is similar to a virtual report suite in Analytics in that it is in sense a "filtered" view of the data. You can create different data views for the same connection, with different settings for visit timeout, attribution, etc.. You can create multiple data views for a single dataset. For example, you could have one data view where all dimensions are set to "Last Touch", and, simultaneously, another data view (based on the same dataset) with all dimensions set to "First Touch".

Workspace projects in Customer Journey Analytics are based on data views.

## Prerequisite

Before you can create data views, you need to [set up one or more connections to Adobe Experience Platform datasets](/help/connections/create-connection.md).

## Configure Settings

1. In Customer Journey Analytics, go to the **[!UICONTROL Data Views]** tab.

1. Click **[!UICONTROL Add]** to add a data view and configure its settings.

    |Session Setting| Definition|
    |---|---|
    |Connection|This field links the data view to the connection that you established earlier, which contains the Platform dataset/s.|
    |Name|Giving the data view a name is mandatory.|
    |Description|A detailed description is not mandatory, but recommended.|
    |Add Tags|Tags let you organize your data views into categories.|
    |Time Zone|Choose the time zone for your data view.|
    |Session Timeout|Select what your definition of a "session" is. The session timeout setting defines the amount of inactivity a unique visitor must have before a new session is automatically started. It defaults to 30 minutes. For example, if you set the session timeout to 45 minutes, a new session grouping is created for each sequence of hits collected, separated by 45 minutes of inactivity. <!--This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting. This needs to be reviewed.-->|
    |Start New Session with Event|A new session starts when an event is fired, regardless of whether a session has timed out. The newly created session includes the event that started it. Additionally, you can use multiple events to start a session and a new session fires if any of those events are observed in the data. This setting will impact your visit count, the Session (formerly Visit) segment container, and the visit expiration logic on dimensions. |
    |Add Filters|"Filters" is the term for "segments" in Customer Journey Analytics. If you want to filter your data, drag the appropriate filter   here from the left rail. If you don't select a filter, the data view will contain all of your data.|

1. Click **[!UICONTROL Continue]**.

## Add Components 

1. Now it's time to add components (dimensions, metrics) to the data view (similar to the curation experience in virtual report suites.) Notice that each of the fields in the datasets are now translated into dimensions or metrics. Drag dimensions and metrics into the panel or **[!UICONTROL Select All** to add all components.

    ![](assets/add-all-components.png)

1. Click the **[!UICONTROL Add Components]** tab to add dimensions and metrics to the data view.

    ![](assets/add-all-components2.png)

1. (Optional) You can rename a component to a friendly name or change its attribution settings by selecting it and editing its setting. Note that the underlying name is preserved. For more information, see [Configure data views and attribution](/help/data-views/configure-dataviews.md).

1. The next steps is to [specify component and attribution settings](/help/data-views/configure-dataviews.md).