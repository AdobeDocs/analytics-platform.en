---
title: Add the Analytics source connector dataset to the connection
description: Learn how to add the Analytics source connector dataset to the connection
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 71b9da74-3597-4536-9e47-f18097dd917b
---
# Disable Adobe Analytics {#disable-appmeasurement}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement"
>title="Disable AppMeasurement data collection"
>abstract="With Web SDK data fully functional, work with your developer team to remove AppMeasurement.js from your website or property.<br><br>The act of removing AppMeasurement from a website takes only a few minutes, but requires time from your engineering team to complete. However, make sure that your Analytics users are using Customer Journey Analytics and not Adobe Analytics; this announcement process to move everyone over might take significantly longer if you haven't already done this."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

Before disabling Adobe Analytics, review the information in [Evaluate when to disable Adobe Analytics after upgrading to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-fully-move.md).

* **Tags:** Disable the Adobe Analytics extension

* **AppMeasurment:** Replace the AppMeasurement.js library s=newobject
