---
title: Content Analytics Manual Configuration
description: Learn how to configure Content Analytics manually.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
TQID: https://experienceleague.adobe.com/McecE-5AGq-IVw-rdkZpV5WgTvax-gubrpQk0ow4JJc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---

# Content Analytics manual configuration

This article details the manual actions that are required to start or stop the data collection of a Content Analytics configuration, or to edit your Content Analytics implementation.

The following manual configuration actions are available:

## Start data collection

To start the data collection for an implemented Content Analytics configuration:

1. Follow the [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Successfully publish the library for the Tags properties that contains your Content Analytics configuration.

1. Based on the channels you have configured:

   * For **web**: [Install](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) the embedded code in the `<head>` element of the pages on your development, staging or publishing environment, subject to Content Analytics.
   * For **mobile**: Consult the solution specific [Adobe Content Analytics extension guide](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) in the [Experience Platform Mobile SDK documentation](https://developer.adobe.com/client-sdks/home/) on how to configure and instrument your mobile application for Content Analytics.

## Stop data collection

To stop the data collection for an implemented Content Analytics configuration, based on the channels you have configured:

* For **web**: 

  1. Remove the [embedded code](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) in the `<head>` element of the pages on your development, staging or production environment, subject to Content Analytics.
  1. Delete the associated web Tags property for your Content Analytics configuration.

* For **mobile**: 

  1. Remove the [Content Analytics extension](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) from your app.
  1. Delete the associated mobile Tags property for your Content Analytics configuration.

Follow the [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} to apply the changes.


## Modify data collection

You can make some minor changes to an implemented configuration using the [guided configuration wizard](guided.md). For example, change the data view, or enable or disable experiences. 


### Web

You use the [Adobe Content Analytics web extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in the Tags property associated with your Content Analytics configuration to make changes to the following artifacts:

* [Sandbox and datastream](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}. 

  >[!CAUTION]
  >
  >Verify that the sandbox and datastream you configure in the Adobe Content Analytics extension are already configured for Content Analytics using the [guided configuration](guided.md) at an earlier stage. This configuration ensures that all required artifacts are available.<br/><br/>Also verify that updates for sandbox or datastreams do not interfere with another Content Analytics configuration that is configured to use the same sandbox or datastreams.
  >

* [Experience capture and definition](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  You can enable or disable experiences and edit the combinations of regular expression and query parameters to determine how content is rendered on your website.

* [Event segmenting](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  You can edit regular expressions to modify how you segment pages and assets.


After you make changes in the Adobe Content Analytics web extension, use the [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} to start collecting data. 


### Mobile

You use the [Adobe Content Analytics mobile extension](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/) in the Tags property associated with your Content Analytics configuration to make additional changes.

After you make changes in the Adobe Content Analytics web extension, use the [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} to start collecting data.


## Versioning

>[!NOTE]
>
>This section only applies to Content Analytics for the web channel.


If you want to collect Content Analytics experiences, you should consider implementing versioning to ensure new experiences (changes to your web page) are properly collected. 

To implement versioning, you add a global `adobe.getContentExperienceVersion` function on the pages that you consider experiences that you want to analyze.

The `adobe.getContentExperienceVersion` function should return a string as value, which can be anything you choose, to identify the version. The version is appended to the [Experience ID URL](/help/content-analytics/report/components.md#experience-metadata). 

If the function is not present or no value is returned from the function, the value `NoVersion` is used as a default.

### Example

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```

>[!MORELIKETHIS]
>
>[Guided configuration](guided.md)
>[Data collection Tags publishing overview](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>
