---
title: CJA Audiences publishing overview
description: Learn about the concept of audience publishing in Customer Journey Analytics
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
---
# CJA Audience publishing overview

You can now create and publish audiences discovered in Customer Journey Analytics (CJA) to [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP) in Adobe Experience Platform for customer targeting and personalization. 

Publishing audiences provides a clear way to activate and to take action on insights found within CJA. These actions might include:

* Using the audience for a journey in Adobe Journey Optimizer.
* Exporting the audience to a 3rd-party through an Experience Platform destination.
* Enriching the Real-time customer profile with useful attributes derived from event-based data in CJA.
* Doing all this with minimal latency after publishing the audience. [Learn more](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#latency)
* Publishing one-time audiences or recurring audiences

## Key terminology

**Audience**: A set or list of identities that have both a namespace and a specific ID related to that namespace. Audiences are transportable from the Adobe Experience Platform and applications that sit on top of it (such as CJA). Audiences can contain mixed namespaces.

**Filter**: A set of rules that, when evaluated over a set of data for a time period, produces a subset of data. A filter can be used in the process of creating an audience when coupled with other supporting services. Filters are defined and maintained in CJA.

**Filters** versus **Segments**: CJA does not use the concept of "segments" - instead, it uses "filters". While both are a set of rules that can contain similar logic, they produce different outputs. A filter is used to narrow down a dataset for analysis purposes. A segment is used to produce a list of identities that can be used for activation. Segments produce audiences in Real-time Customer Profile, whereas filters (alone) do not. CJA Audience Publishing is the process by which we use a CJA filter to create an audience that can be consumed by Real-time Customer Profile.

## Permissions

* Admins are automatically granted the **[!UICONTROL Audience Publishing]** permission in Adobe Admin Console. 

* Admins can grant this permission to individual users.

* Admins also need the **[!UICONTROL Manage Profiles]** permission in Adobe Experience Platform.

## Data Governance and Consent

When you publish an audience in CJA, the Data Governance labels and policies attached to the fields used in the audience are recorded.  When the audience is activated in any Adobe Experience App, all associated Data Governance labels and policies are available for that audience and appropriate enforcement can be applied. [Learn more about consent](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=en#consent-policy).

## Next steps

* [Create and publish audiences](/help/components/audiences/publish.md)
* [Manage audiences](/help/components/audiences/manage.md)
