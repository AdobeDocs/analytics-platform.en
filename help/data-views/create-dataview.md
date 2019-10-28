---
title: Create a data view
seo-title: Create a data view in [!UICONTROL Customer Journey Analytics] (CJA).
description: Describes how to create a data view to a Platform dataset.
seo-description: Describes how to create a data view within Workspace in [!UICONTROL Customer Journey Analytics].
---

# Create a data view

A data view is similar to a virtual report suite in Analytics. 

1. In [!UICONTROL Customer Journey Analytics], go to the **[!UICONTROL Data Views]** tab.

1. Click **[!UICONTROL Create New Data View]** to configure the settings.

    |Session Setting| Definition|
    |---|---|
    |Connection|This field links the data view to the connection that you established earlier, which contains the platform datasets.|
    |Name|Giving the data view a name is mandatory.|
    |Description|A detailed description is mandatory as well.|
    |Tags|Tags let you organize your data views into categories.|
    |Time Zone|Choose the time zone for your data view. **This setting determines...** |
    |Session Timeout|Select what your definition of a "session" is. The session timeout setting defines the amount of inactivity a unique visitor must have before a new session is automatically started. It defaults to 15 minutes. For example, if you set the session timeout to 30 minutes, a new session grouping is created for each sequence of hits collected, separated by 30 minutes of inactivity. **This setting impacts not only your visit counts, but also how visit segment containers are evaluated, and the visit expiration logic for any eVars expiring on visit. Decreasing the session timeout will likely increase the total number of visits in your reporting, while increasing the visit timeout will likely decrease the total number of visits in your reporting.** <!--This needs to be reviewed.-->|
    |Start New Session with Event|A new session starts when an event is fired, regardless of whether a session has timed out. The newly created session includes the event that started it. Additionally, you can use multiple events to start a session and a new session fires if any of those events are observed in the data. This setting will impact your visit count, the visit segmentation container, and the visit expiration logic on (dimensions)? |
    |Add Filters|...|

1. Click **[!UICONTROL Continue]**.

1. Now it's time to add components to the data view (similar to the curation experience in virtual report suites.) Notice that each of the fields in the datasets are now translated into dimensions or metrics. 

    ![](assets/add-all-components.png)

1. Click **[!UICONTROL Add All Components]** to add all of those dimensions and metrics to the data view.

    ![](assets/add-all-components2.png)


1. (Optional) You can rename a component or change its attribution settings (see below) by selecting it and editing its setting. Note that the underlying name is preserved.

    ![](assets/edit-component.png)

1. Click **[!UICONTROL Save]** to save your data view.

## Specify attribution settings on a data field

EVars, props, and events in the traditional Adobe Analytics sense no longer exist in CJA. You have unlimited schema elements (dimensions, metrics, list fields ). All of the attribution settings that you used to apply to eVars and props during the data collection process are now applied at query time. 

(Take some of the Attribution IQ doc on settings etc. and put it here.)

1. To specify and attribution setting, go to 