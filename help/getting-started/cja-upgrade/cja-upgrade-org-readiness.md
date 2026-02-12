---
title: Upgrade from Adobe Analytics to Customer Journey Analytics
description: Learn about the recommended steps when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bd19250e-91c0-49f6-b6dc-3abd641344aa
---
# Prepare your organization to upgrade to Customer Journey Analytics

Part of a successful upgrade (as described in [Upgrade from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md)) is to prepare your organization by focusing on certain operational considerations. To prepare your organization, it's recommended that you:

* Obtain buy-in and alignment from key stakeholders
  
* Define and document your goals

* Set realistic and thoughtful timelines 

* Define clear responsibilities for contributors

## Stakeholder buy-in and alignment

The key stakeholders and decision-makers in your organization need to align on your upgrade to Customer Journey Analytics. 

The following sections describe ways that you can gain stakeholder alignment.

### Focus on value

Focus on the value that Customer Journey Analytics will bring to your organization, and how it will accelerate reaching your business objectives. 

The following table covers some key features that you might want to highlight.

| Feature | Benefit | Example |
|---------|----------|---------|
| **[Accommodation for all kinds of data](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home)** | Customer Journey Analytics is combined with Experience Platform's ability to hold all kinds of data schemas and types. | A retail organization could provide visibility to the complete customer journey by integrating the following kinds of data into a single view: <ul><li>Web clickstream transactions</li><li>Mobile app transactions</li><li>In-store transactions</li><li>CRM and loyalty data</li></ul> |
| **[Cross-channel analysis](/help/use-cases/cross-channel/cross-channel.md)** | Enables a single consolidated view of customer behavior across various channels by unifying data from various web, mobile, and offline properties. | A retail organization that is gathering data from multiple channels could perform the following kind of analysis:<p>A shopper clicks a paid search ad, browses jeans online, receives a push notification, then purchases in-store two days later. This unified perspective enables accurate cross-channel attribution, showing how digital touchpoints contribute to in-store sales. It also supports more precise segmentation, such as targeting "browsed online, purchased in-store" customers with tailored offers. Furthermore, it delivers clear, all-channel revenue reporting in one dashboard, replacing fragmented, siloed insights with a holistic understanding of customer behavior. |
| **[Report-time processing](/help/getting-started/aa-to-cja.md#get-comfortable-with-report-time-processing)** | Apply settings that are retroactive and create multiple versions of variable persistence without needing to change how the underlying data is collected. | Because Customer Journey Analytics allows you to create and adjust metrics, dimensions, and attribution models on the fly without reingesting or reprocessing data, a retail organization could see how a recent social campaign influenced both online and in-store sales without needing to ask engineering to rebuild datasets. They could instantly change the attribution model from last touch to first touch or custom rules-based attribution.  |
| **[Content Analytics](/help/content-analytics/content-analytics.md)** | Helps marketers understand how content impacts the key performance indicators that a business has defined. On top of the behavioral data, Content Analytics collects data on how content is consumed and how content drives impact. | By integrating web, app, email, and even in-store data, a retail organization could see exactly how each piece of digital content they create contributes to the customer journey and conversion. <p>The retail organization could see that a "Summer Denim Style Guide" on a popular social media platform drives high engagement among loyalty members, and that those members are 40% more likely to purchase denim in-store within a week.</p>  |

### Appoint an executive sponsor

Find and appoint an executive sponsor within your organization. This executive sponsor needs to understand how Customer Journey Analytics will accelerate reaching your business objectives. 

The executive sponsor is crucial as they:

* Champion Customer Journey Analytics within the organization

* Remove roadblocks

* Approve resources

### Secure support from key leaders throughout your organization

With the help of your executive sponsor, secure support from other key leaders throughout your organization. It's critical that leaders from the following areas of your organization understand the benefits of Customer Journey Analytics and that they are willing to contribute to a successful implementation:

* Analytics

* Marketing

* IT

* Legal and compliance

* Individual business units

## Develop an upgrade and communication plan

### Develop an upgrade plan and distribute it to stakeholders

An upgrade plan might include the following information:

* A clear description about why the upgrade is happening. For example, describe the benefits for users and for the organization or business as a whole. For more information about the benefits, see [Focus on value](#focus-on-value).

* A general timeline, such as when the upgrade is planned to begin, an outline of key milestones, and an estimate on when the upgrade is scheduled to complete.

* An indication of when users can begin taking official trainings to learn how to use Customer Journey Analytics. For more information, see [Train end-users throughout your organization](#train-end-users-throughout-your-organization).

* Information about who is leading the upgrade and how or when people can reach out with questions.

### Create a communication plan 

A communication plan might include the following considerations:

* A defined cadence on when communications will be sent to stakeholders and users

* An outline of the type of information that will be sent

* A plan for who will send communications

* Defined feedback loops to allow stakeholders and users to ask questions or provide feedback

## Assess and audit your Adobe Analytics implementation

Perform a thorough assessment and audit of your Adobe Analytics implementation, focusing on the following key areas:

* Current users

* User access

* Projects

* Business processes

* Custom components

See the following resources to help gather this information:

* [Analytics inventory](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/analytics-inventory)

  Provides information on the number of projects, segments, calculated metrics, report suites, and users within your organization.

* [Prepare to migrate components and projects from Adobe Analytics to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/component-migration/prepare-component-migration)

  Provides information about how you can prepare to migrate components, projects, and users.

## Identify champions and early adopters

Identify Champions throughout your organization. These champions should be:

* Adobe Analytics power users 

* Capable of quickly gaining proficiency in Customer Journey Analytics

* Available to be a help and coach to others as Customer Journey Analytics is rolled out more broadly

## Train end-users throughout your organization

* Provide hands-on training that focuses on the differences in data models, reporting paradigms, and new features within Customer Journey Analytics.

* Offer both live sessions (workshops or office hours) and on-demand resources (video tutorials, dynamic wiki pages, and internal documentation).

* Direct users to relevant trainings, tutorials, and documentation on Experience League.

  The following resources can help you get started:

  * [Customer Journey Analytics tutorials](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/overview)

  * [What is Customer Journey Analytics?](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/what-is-customer-journey-analytics)

  * [Introduction to Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/understanding-customer-journey-analytics)

  * [Customer Journey Analytics feature support](/help/getting-started/aa-vs-cja/cja-aa.md)

## Follow the recommended upgrade steps

When you're ready to begin the upgrade process, follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the dynamically generated upgrade steps in the Customer Journey Analytics Upgrade Guide. To access the guide from Customer Journey Analytics, select the **[!UICONTROL Workspace]** tab, then select **[!UICONTROL Upgrade to Customer Journey Analytics]** in the left panel. Follow the on-screen instructions.
