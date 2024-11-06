---
title: Create a schema for Customer Journey Analytics
description: Learn about the recommended path when upgrading from Adobe Analytics to Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Create lookup datasets to classify data in Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended steps or the dynamically generated upgrade steps. 

Similar to classifications data in Adobe Analytics, lookup datasets are the method for classifying data in Customer Journey Analytics. 

When using the Analytics source connector, some standard lookup datasets are automatically applied at report time. For more information, see [Add standard lookups to your datasets](/help/connections/standard-lookups.md).

In order to classify data with a new implementation of the Experience Platform Web SDK, you need to create a lookup dataset for each dimension that contains data that you want to classify.

To create lookup datasets for use in Customer Journey Analytics:

1. In AEP, create a new schema. This is a new schema that is specific for lookup datasets. You cannot use an existing schema.

1. You have to create a new schema class that is for lookups. 

1. Create a lookup dataset off of that. 

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/). 
