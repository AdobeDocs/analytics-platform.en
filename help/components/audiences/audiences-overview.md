---
title: CJA Audiences publishing overview
description: Learn about the concept of audience publishing in Customer Journey Analytics
---

# CJA Audience publishing overview

>[!NOTE]
>
>This functionality is currently in [limited testing](/help/release-notes/releases.md).

You can now create and publish audiences discovered in Customer Journey Analytics (CJA) to [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) in Adobe Experience Platform for customer targeting and personalization. With Real-time Customer Profile, you can see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. Profile allows you to consolidate your customer data into a unified view offering an actionable, timestamped account of every customer interaction.

Publishing audiences provides a clear way to take action on insights found within CJA. These actions might include:

* Sending emails to this audience.
* Sending push messages to this audience.
* Using the audience for a journey in Adobe Journey Optimizer.
* Exporting the audience to a 3rd-party through an Experience Platform destination.

## Key terminology

**Audience**: A set or list of identities that have both a namespace and a specific ID related to that namespace. Audiences are transportable from the Adobe Experience Platform and applications that sit on top of it (such as CJA). Audiences can contain mixed namespaces.

**Filter**: A set of rules that, when evaluated over a set of data for a time period, produces a subset of data. A filter can be used in the process of creating an audience when coupled with other supporting services. Filters are defined and maintained in CJA.

**Filters** versus **Segments**: CJA does not use the concept of "segments" - instead, it uses "filters". While both are a set of rules that can contain similar logic, they produce different outputs. A filter is used to narrow down a dataset for analysis purposes. A segment is used to produce a list of identities that can be used for activation. Segments produce audiences in Real-time Customer Profile, whereas filters (alone) do not. CJA Audience Publishing is the process by which we use a CJA filter to create an audience that can be consumed by Real-time Customer Profile.

## Permissions

Admins are automatically granted the [!UICONTROL Audience Publishing] permission in Adobe Admin Console. They can grant this permission to individual users.

## Next steps

* [Create and publish audiences](/help/components/audiences/publish.md)
* [Manage audiences](/help/components/audiences/manage.md)


