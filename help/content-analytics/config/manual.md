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

>[!WARNING]
>
>This article is a preliminary unofficial draft version of a forthcoming final version and is part of the Content Analytics documentation. All content is subject to change and no legal obligations whatsoever can be derived from the current version of this article.  
>

{{release-limited-testing}}

This article details the manual actions that are required to activate or de-activate a Content Analytics configuration or to edit your Content Analytics implementation.

The following manual configuration actions are available:

## Activate

To activate a new configuration or changes you made to an existing configuration, you need to [publish](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} the associated Tag property. Only when you publish your Content Analytics Tag property, Content Analytics data is collected for the domains, experience and assets that you have configured.


## Deactivate

To deactivate collecting content analytics data, [unpublish](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"} the associated Tag property for you Content Analytics configuration.



## Modify 

In general, you should use the [guided configuration wizard](guided.md) to make changes to your implementation.

Alternatively, you can use the Adobe Content Analytics extension in the Tag property associated with your Content Analytics configuration to make changes to the following artefacts:

* [Sandbox and datastream](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}. 

  >[!CAUTION]
  >
  >You must verify that the sandbox and datastream you configure in the Adobe Content Analytics extension are already configured for Content Analytics using the [guided configuration](guided.md) at an earlier stage. This configuration ensures all required artefacts are available.<br/><br/>You must also verify that you updates for sandbox or datastreams do not interfere with another Content Analytics configuration that is configured to use the same sandbox or datastreams.
  >

* [Event filtering](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}.

  You can edit regular expressions to modify how you filter pages and assets.


After you make changes in the Adobe Content Analytics extension, ensure your [activate](#activate) your changes. 



>[!MORELIKETHIS]
>
>[Guided configuration](guided.md)
>[Data collection Tags publishing overview](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>