---
title: Content Analytics manual configuration
description: How to configure Content Analytics manually
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
---
# Content Analytics manual configuration

{{release-limited-testing}}


This article details the manual actions that are required to start or stop the data collection of a Content Analytics configuration, or to edit your Content Analytics implementation.

The following manual configuration actions are available:

## Start data collection

To start the data collection for an implemented Content Analytics configuration:

1. Follow the [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Successfully publish the library for the Tags property that contains your Content Analytics configuration.

1. [Install](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) the embedded code in the `<head>` element of the pages on your development, staging or publishing environment, subject to Content Analytics.


## Stop data collection

To stop the data collection for an implemented Content Analytics configuration:

1. Remove the [embedded code](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) in the `<head>` element of the pages on your development, staging or production environment, subject to Content Analytics.
1. [Delete](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) the associated Tags property for your Content Analytics configuration.



## Modify data collection

You can make some minor changes to an implemented configuration using the [guided configuration wizard](guided.md). For example, change the data view, or enable or disable experiences. 

You use the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in the Tags property associated with your Content Analytics configuration to make changes to the following artifacts:

* [Sandbox and datastream](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}. 

  >[!CAUTION]
  >
  >Verify that the sandbox and datastream you configure in the Adobe Content Analytics extension are already configured for Content Analytics using the [guided configuration](guided.md) at an earlier stage. This configuration ensures that all required artifacts are available.<br/><br/>Also verify that updates for sandbox or datastreams do not interfere with another Content Analytics configuration that is configured to use the same sandbox or datastreams.
  >

* [Experience capture and definition](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  You can enable or disable experiences and edit the combinations of regular expression and query parameters to determine how content is rendered on your website.

* [Event filtering](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  You can edit regular expressions to modify how you filter pages and assets.


After you make changes in the Adobe Content Analytics extension, ensure your use [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} to start the collection of data based on the changes made. 



>[!MORELIKETHIS]
>
>[Guided configuration](guided.md)
>[Data collection Tags publishing overview](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Versioning

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
