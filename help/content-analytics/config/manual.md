---
title: Content Analytics manual configuration
description: How to configure Content Analytics manually
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
---
# Content Analytics manual configuration

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

* [Event segmenting](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  You can edit regular expressions to modify how you segment pages and assets.


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

## Identities

Content Analytics handle identities in the following way:

* ECID is automatically populated in the `identityMap` portion of the Content Analytics schema.
* If you require other identity values in the `identityMap`, you need to set these values in the `onBeforeEventSend` callback within the Web SDK extension.
* Field-based stitching is not supported because the schema is system-owned. So, you cannot add another field to the schema to support field-based stitching


To ensure Content Analytics identity data and Adobe Experience Platform Web SDK data identity data are stitched correctly at the field level, you need to make modifications to the Web SDK [on before event send](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"} callback.

1. Navigate to your **[!UICONTROL Tags]** property that contains the Adobe Experience Platform Web SDK extension and Adobe Content Analytics extension.
1. Select ![Plug](/help/assets/icons/Plug.svg) **[!UICONTROL Extensions]**.
1. Select the **[!UICONTROL Adobe Experience Platform Web SDK]** extension.
1. Select **[!UICONTROL Configure]**.
1. In the **[!UICONTROL SDK instances]** section, scroll down to **[!UICONTROL Data collection]** - **[!UICONTROL On before event send callback]**.

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. Select **[!UICONTROL </> Provide on before event send callback code]**.
1. Add the following code:

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);

   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![On before event send callback](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. Select **[!UICONTROL Save]** to save the code.
1. Select **[!UICONTROL Save]** to save the extension.
1. [Publish](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview) the updates for your Tags property.



   
  