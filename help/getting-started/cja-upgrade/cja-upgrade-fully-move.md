---
title: Evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics
description: Learn how to evaluate how long you need Adobe Analytics after upgrading to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 7142ef84-66a6-49eb-938b-b67c9b65bf93
---
# Evaluate when to disable Adobe Analytics after upgrading to Customer Journey Analytics {#evaluate-aa-needs}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-fully-move"
>title="Fully move to Customer Journey Analytics"
>abstract="(Recommended) Adobe recommends that you transition fully from Adobe Analytics to Customer Journey Analytics. During the transition period, you should plan to run Adobe Analytics alongside Customer Journey Analytics in order to perform side-by-side data comparisons. When you are comfortable with the data, you can disable Adobe Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-keep-aa"
>title="Keep both analytics products"
>abstract="(Not recommended) If you select this option, your contract with Adobe includes both Adobe Analytics and Customer Journey Analytics, which can be more expensive for your organization over time."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-source-connector"
>title="Disable the Analytics source connector to use data exclusively from the Web SDK"
>abstract="The Analytics source connector is used to provide side-by-side data comparison, historical data, and access to some features that aren't fully available in Customer Journey Analytics. When you no longer need Adobe Analytics for these purposes, you can disable the Analytics source connector."

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

Most organizations will eventually disable Adobe Analytics after upgrading to Customer Journey Analytics. This is due to the cost and complexity of maintaining two analytics environments. 

However, Adobe recommends that you keep your Adobe Analytics environment running for a period of time after implementing Customer Journey Analytics. The following sections describe the reasons for doing so as well as the suggested timing of disabling Adobe Analytics. 

## Uses of Adobe Analytics during and after an upgrade

When deciding if and when your organization should disable Adobe Analytics, consider the following uses of Adobe Analytics during and after an upgrade to Customer Journey Analytics:

| Uses of Adobe Analytics during and after upgrade | Explanation |
|---------|----------|
| Perform side-by-side data comparison | Adobe recommends that you keep your Adobe Analytics environment running for a period of time after your new Customer Journey Analytics environment is running and collecting data. This is the best way to compare your Customer Journey Analytics data side-by-side with your Adobe Analytics data.<p>Don't disable Adobe Analytics until you are comfortable with the data in your Customer Journey Analytics environment.</p><p>**Note:** Adobe recommends a new implementation of the Web SDK for your Customer Journey Analytics environment, in conjunction with the Analytics source connector for historical data. [Learn more](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p>  |
| Retain historical data from Adobe Analytics | Adobe recommends that you keep your Adobe Analytics environment in place with the Analytics source connector for a period of time after your new Customer Journey Analytics environment is running and collecting data. This is the best way to bring historical Adobe Analytics data into Customer Journey Analytics.<p>After you have collected enough historical data in Customer Journey Analytics with your new Web SDK implementation, you can remove the Analytics source connector entirely. Do this when you can rely solely on the historical data in you collected with the new Customer Journey Analytics Web SDK implementation.</p><p>**Note:** Adobe recommends a new implementation of the Web SDK for your Customer Journey Analytics environment, in conjunction with the Analytics source connector for historical data. [Learn more](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)</p>   |
| Use Data Feeds or other Adobe Analytics features | A small set of features are not yet fully available in Customer Journey Analytics. If you need access to these features, it might be necessary to use Adobe Analytics in conjunction with Customer Journey Analytics until these features are available. <p>Features not fully available in Customer Journey Analytics include Data Feeds and Contribution Analysis. For a complete list of features that aren't yet available, see [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md).</p> | 

## Process and timeline of disabling Adobe Analytics {#disable-adobe-analytics}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-appmeasurement-third-pary"
>title="Disable a third-party tag management system"
>abstract="With the Web SDK data fully functional, work with your tag admin to remove the AppMeasurement library from your third-party tag management system.<br><br>Estimated time to perform this step depends on the ease of disabling AppMeasurement from your tag management product, as well as the release cycle that your organization employs to deploy and manage tag code."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-tags"
>title="Disable the Analytics extension in tags"
>abstract="With Web SDK data fully functional, work with your tags administrator to remove the Adobe Analytics extension from the tag property. Before you do this, make sure that your users have transitioned from using Adobe Analytics to Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-disable-analytics-api"
>title="Disable API data collection for Adobe Analytics"
>abstract="With Web SDK data fully functional, work with the applicable engineering team to remove the Adobe Analytics code from the project. Before you do this, make sure that your users have transitioned from using Adobe Analytics to Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

Your existing Adobe Analytics implementation is a key part of a successful upgrade to Customer Journey Analytics, as described in the section above, [Uses of Adobe Analytics during and after an upgrade](#uses-of-adobe-analytics-during-and-after-an-upgrade).

When you no longer need Adobe Analytics for the purposes described in the section above, use the following information to remove Adobe Analytics:

1. Stop collecting data with Adobe Analytics. 

   After you are satisfied with the side-by-side comparisons of your Adobe Analytics data and your Customer Journey Analytics data, you can stop collecting data with your Adobe Analytics implementation. New Adobe Analytics data will no longer flow to Customer Journey Analytics through the Analytics source connector. 
   
   However, data that you collected from your Adobe Analytics environment prior to this point is still available as historical data in Customer Journey Analytics through the Analytics source connector.

   This process differs depending on the data collection method you used to implement Adobe Analytics:

      +++ AppMeasurement

      [Disable AppMeasurement data collection](/help/getting-started/cja-upgrade/cja-upgrade-disable-appmeasurement.md). 

      +++

      +++ Analytics extension (Tags)

      Disable the Analytics extension in tags. 

      +++

      +++ API

      Disable API data collection. 

      +++

      +++ Third-party

      Work with your tag admin to remove the AppMeasurement library from your third-party tag management system.

      +++

1. Remove Adobe Analytics as a service from the datastream.

   With Web SDK data fully functional, work with your Platform administrator to remove Adobe Analytics as a service from the datastream.
   
   Before removing Adobe Analytics as a service, make sure that your Analytics users are using Customer Journey Analytics and not Adobe Analytics.

1. Remove the Analytics source connector entirely. 

   After you have collected enough historical data in Customer Journey Analytics with your new Web SDK implementation, you can remove the Analytics source connector entirely. 
   
   Do this when you no longer need the historical data from your Adobe Analytics environment through the Analytics source connector, and you can rely solely on the historical data you collected with the new Web SDK implementation.

1. {{upgrade-final-step}}

