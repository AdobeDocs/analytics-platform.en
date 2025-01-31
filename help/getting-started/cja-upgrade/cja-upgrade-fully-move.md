---
title: Evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics
description: Learn how to evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Fully move to Customer Journey Analytics"
>abstract="(Recommended) Customer Journey Analytics aims to be the primary Analytics tool for your organization. However, your organization might still require Adobe Analytics if it heavily relies on features exclusive to the tool and those workflows cannot be altered."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Keep both analytics products"
>abstract="(Not recommended) If you select this option, your contract with Adobe includes both Adobe Analytics and Customer Journey Analytics, which can be more expensive for your organization over time."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
>
>This documentation should be used as part of the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/).

Most organizations will eventually disable Adobe Analytics after upgrading to Customer Journey Analytics. This is due to the cost and complexity of maintaining two analytics environments. 

However, Adobe recommends that you keep your Adobe Analytics environment running for a period of time after implementing Customer Journey Analytics. The following sections describe the reasons for doing so as well as the suggested timing of disabling Adobe Analytics. 

## Uses of Adobe Analytics during and after the upgrade process

When deciding if and when your organization should disable Adobe Analytics, consider the following uses of Adobe Analytics during and after an upgrade to Customer Journey Analytics:

| Use of Adobe Analytics during and after upgrade | Explanation |
|---------|----------|
| Perform side-by-side data comparison | Adobe recommends that you keep your Adobe Analytics environment running for a period of time after your new Customer Journey Analytics environment is running and collecting data. This is the best way to compare your Customer Journey Analytics data side-by-side with your Adobe Analytics data.<p>Don't disable Adobe Analytics until you are comfortable with the data in your Customer Journey Analytics environment.</p><p>**Note:** Adobe recommends a new implementation of the Web SDK for your Customer Journey Analytics environment, in conjunction with the Analytics source connector for historical data. [Learn more](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p>  |
| Retain historical data from Adobe Analytics | After you have collected enough historical data in Customer Journey Analytics with your new Web SDK implementation, you can remove the Analytics source connector entirely. Do this when you can rely solely on the historical data in you collected with the new Customer Journey Analytics Web SDK implementation.<p>**Note:** Adobe recommends a new implementation of the Web SDK for your Customer Journey Analytics environment, in conjunction with the Analytics source connector for historical data. [Learn more](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p>   |
| Use Data Feeds or other Adobe Analytics features | A small set of features are not yet fully available in Customer Journey Analytics. If you need access to these features, it might be necessary to use Adobe Analytics in conjunction with Customer Journey Analytics until these features are available. <p>Features not fully available in Customer Journey Analytics include Data Feeds and Contribution Analysis. For a full list of features that aren't yet available, see [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md).</p> | 

## Timeline of disabling Adobe Analytics

Your existing Adobe Analytics implementation is a key part of a successful upgrade to Customer Journey Analytics, as described in the section above, [Uses of Adobe Analytics during and after the upgrade process](#uses-of-adobe-analytics-during-and-after-the-upgrade-process).

Consider the following upgrade milestones related to removing Adobe Analytics:

1. Stop collecting data with the Analytics source connector. 

   After you are satisfied with the side-by-side comparisons of your Adobe Analytics data and your Customer Journey Analytics data, you can stop collecting data with your Adobe Analytics implementation. New Adobe Analytics data will no longer flow to Customer Journey Analytics through the Analytics source connector. 
   
   However, data that you collected from your Adobe Analytics environment prior to now is still available as historical data through the Analytics source connector.

1. Remove the Analytics source connector entirely. 

   After you have collected enough historical data in Customer Journey Analytics with your new Web SDK implementation, you can remove the Analytics source connector entirely. 
   
   Do this when you no longer need the historical data from your Adobe Analytics environment through the Analytics source connector, and you can rely solely on the historical data you collected with the new Web SDK implementation. 

