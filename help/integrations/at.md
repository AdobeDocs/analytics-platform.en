---
title: Target reporting in Adobe Customer Journey Analytics
description: Integrate Adobe Target with Customer Journey Analytics
feature: Experience Platform Integration
role: User
exl-id: 0b52af5b-b65c-4929-9ca3-547a640936f3
---
# Target reporting in Adobe Customer Journey Analytics

Target Reporting in Customer Journey Analytics enables you to measure and report on Adobe Target activities directly in Customer Journey Analytics. This functionality is comparable to what is being performed in Adobe Analytics (AA) via Analytics for Target (A4T), but with the connectivity to Adobe Experience Platform (AEP). 

By adding the Target Classification lookup dataset (that is available by default in Experience Platform) into a Customer Journey Analytics Connection, users now have proper exposure to Target reporting tools, Target order attribution, and other features. With only some minor preparation and adjustments made within the Customer Journey Analytics data view, these activities can be made immediately available for any user who wishes to send Target data directly into CJA. 

## Primary benefits

* Marketers can dynamically apply Customer Journey Analytics success metrics to Target activity reports at any time. It is not required to specify everything before running the activity.
* Marketers can take advantage of Customer Journey Analytics features, such as the Experimentation Panel, to analyze their website personalization further.
* Marketers can have a single source of reporting for Adobe Journey Optimizer and Target. Both personalization products can be connected to Customer Journey Analytics for a more holistic view of your web personalization.

## Notes and Considerations

Once the Target Classification Event Dataset has been added to a CJA Connection, there are a few minor adjustments to be made within the CJA Data View once these components have been added as dimensions, including:

* Setting persistence to be similar to how it is tracked in Target (check with a Target consultant or the customer to ensure proper settings).

* Setting persistence to ALL, which allows for multiple Target activities to be tracked simultaneously and not overwritten by future or previous activities.

## More detailed information

See [Target reporting in Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja) in the Target documentation for more information.

See the [Experimentation panel](../analysis-workspace/c-panels/experimentation.md) for more information on how analysts can compare different user experience, marketing, or messaging variations to determine which is best at driving a specific outcome. You can evaluate the lift and confidence of any A/B experiment from any experimentation platform - online, offline, from Adobe solutions like Target or Journey Optimizer, and even BYO (bring-your-own) data.
