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
    |Description|...|
    |Tags|...|
    |Time Zone|Choose the time zone...  |
    |Session Timeout|Select what your definition of a "session" is.|
    |Start New Session with Event|...|
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

