---
title: Configure Settings For Report Builder
description: Learn how to configure settings for Report Builder.
role: Admin
feature: Report Builder
type: Documentation
exl-id: 32423cb4-1a4c-4ea3-ad4b-9520aff9ae4b
solution: Customer Journey Analytics
---
# Report Builder settings

Use the **Settings** pane to configure application-level settings such as the language displayed by the UI or whether or not to work in off-line mode. The settings are applied immediately and they are set for all future sessions until they're changed.

To change Report Builder settings

1. Select the **Settings** icon.

1. Make changes to [enable of disable off-line mode](#off-line-mode), [select a language](#language), or [enable troubleshooting](#troubleshooting).

1. Select **[!UICONTROL Apply]**.

    ![Report Builder date range pane showing the Cancel and Apply button.](./assets/report-builder-settings.png){zoomable="yes"}

## Off-line mode

When you create and edit a data block in off-line mode, data is not retrieved. Instead, simulation data is used so that you can quickly work without waiting for the request to run. When you are back online, select ![Refresh](/help/assets/icons/Refresh.svg) **[!UICONTROL Refresh data block]** or ![DocumentRefresh](/help/assets/icons/DocumentRefresh.svg) **[!UICONTROL Refresh all data blocks]** to refresh the data blocks with actual data.

To enable off-line mode

1. Select ![Setting](/help/assets/icons/Setting.svg).

1. Toggle **[!UICONTROL Enable off-line mode]** on.

1. Enter a positive integer in the **[!UICONTROL Display metric data]** as field.

1. Select **[!UICONTROL Apply]**.


## Language

You can choose the language for the Report Builder interface. All supported Customer Journey Analytics languages are available.

To select the language used in the Report Builder interface:

1. Select a language from the **[!UICONTROL Language]** drop-down menu.

1. Select **Apply.**

## Troubleshooting

The **[!UICONTROL Troubleshooting logs]** setting logs all client/server data to a local file. Use this option to help resolve support tickets.

To enable troubleshooting logs, check **[!UICONTROL Log report builder request to local file]**.
