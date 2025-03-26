---
title: Content Analytics manual configuration
description: How to configure Content Analytics manually
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: yes
hidefromtoc: yes
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
---
# Content Analytics manual configuration

{{draft-aca}}

{{release-limited-testing}}

This article details the manual actions that are required to activate or de-activate a Content Analytics configuration or to edit your Content Analytics implementation.

The following manual configuration actions are available:

## Activate

To activate a new configuration or changes you made to an existing configuration:

1. You need to follow the [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}. Successfully publish the library for the Tags property that contains your Content Analytics configuration.

1. You need to [install](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation) the embedded code in the `<head>` element of the pages on your development, staging or publishing environment, subject to Content Analytics.


## Deactivate

To deactivate the collection of content analytics data:

1. Remove the [embedded code](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments) in the `<head>` element of the pages on your development, staging or production environment, subject to Content Analytics.
1. [Delete](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) the associated Tags property for your Content Analytics configuration.



## Modify 

You can make some minor changes to an implemented configuration using the [guided configuration wizard](guided.md). For example, change the data view. 

You use the [Adobe Content Analytics extension](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview) in the Tags property associated with your Content Analytics configuration to make changes to the following artifacts:

* [Sandbox and datastream](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}. 

  >[!CAUTION]
  >
  >Verify that the sandbox and datastream you configure in the Adobe Content Analytics extension are already configured for Content Analytics using the [guided configuration](guided.md) at an earlier stage. This configuration ensures that all required artifacts are available.<br/><br/>Also verify that updates for sandbox or datastreams do not interfere with another Content Analytics configuration that is configured to use the same sandbox or datastreams.
  >

* [Experience capture and definition](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  You can edit the regular expression to modify how you .

* [Event filtering](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  You can edit regular expressions to modify how you filter pages and assets.


After you make changes in the Adobe Content Analytics extension, ensure your use [publishing flow](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} to activate your changes. 



>[!MORELIKETHIS]
>
>[Guided configuration](guided.md)
>[Data collection Tags publishing overview](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## Versioning

If you require versioning of your Content Analytics experiences, you must add a global `adobe.getContentExperienceVersion` function on the pages that you consider experiences that you want to analyze.

The `adobe.getContentExperienceVersion` function should return a string as value, which can be anything you choose, to identify the version. The version is appended to the [Experience ID URL](/help/content-analytics/report/components.md#experience-metadata). 

If the function is not present or no value is returned from the function, the value `NoVersion` is used as a default.

### Example

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}

```
