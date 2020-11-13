---
title: Import Marketing Channels into CJA using Analytics Data Connector
description: Use the correct Analytics Data Connector settings to bring Marketing Channel processing rules into Adobe Experience Platform.
---

# Import Marketing Channels into CJA using Analytics Data Connector

If your organization uses the [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) to bring report suite data into CJA, you can configure a connection in CJA to report on Marketing Channel dimensions.

## Prerequisites

* Report suite data must already be imported into Adobe Experience Platform using the [Analytics Data Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html).
* Marketing channel processing rules must already be set up. See [Processing rules for Marketing Channels](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-rules.html) in the traditional Analytics Components guide.

## Marketing Channel schema elements

Once you use the Analytics Data Connector on a desired report suite, an XDM schema is created for you. This schema contains all Analytics dimensions and metrics as raw data. This raw data does not contain attribution or persistence. Instead, each hit runs through marketing channel processing rules and records the first rule it matches. You specify attribution and persistence when creating a data view in CJA.

1. [Create a connection](/help/connections/create-connection.md) that includes a dataset based on the Analytics Data Connector.
2. [Create a data view](/help/data-views/create-dataview.md) that includes the following dimensions:
   * **`channel.typeAtSource`**: Equivalent to the [Marketing channel](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) dimension.
   * **`channel._id`**: Equivalent to the [Marketing channel detail](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. Give each dimension the desired attribution model and persistence. If you want both first and last touch dimensions, drag each marketing channel dimension to the components area multiple times. Give each dimension the desired attribution model and persistence. Adobe also recommends giving each dimension a display name to make it easier for use in Workspace.
4. Create the data view.

Your marketing channel dimensions are now available for use in Analysis Workspace.

## Processing and architecture differences

>[!IMPORTANT]
>
>There are several fundamental data differences between report suite data and Platform data. Adobe highly recommends adjusting your report suite's marketing channel processing rules to help facilitate proper data collection in Platform.


Since first and last touch channel dimensions are in essence the same dimension with different attribution models, you can recreate similar dimensions when [creating a data view](/help/data-views/create-dataview.md). You can create multiple dimensions based on the same schema element, giving them different attribution models and persistence.

## Differences between

