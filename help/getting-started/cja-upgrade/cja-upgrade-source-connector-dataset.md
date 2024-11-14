---
title: Add the Analytics source connector dataset to the connection
description: Learn how to add the Analytics source connector dataset to the connection
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
---
# Add the Analytics source connector dataset to the connection

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

After you [create an Analytics source connector for historical data](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md), a dataset is automatically created for the Analytics data. 

You need to add this automatically created dataset to the same connection that you created for your Web SDK implementation. Doing so brings the Analytics data into the same data view in Customer Journey Analytics as your Web SDK data. 

To add the automatically created dataset to the same connection that you created for your Web SDK implementation:

1. In Customer Journey Analytics, select the **[!UICONTROL Connections]** tab.

1. Select the connection that you [created for your Web SDK implementation](/help/getting-started/cja-upgrade/cja-upgrade-connection.md).

1. Select **[!UICONTROL Edit]**.

   ![Edit connection](assets/connection-add-dataset.png)

1. Select **[!UICONTROL Add datasets]** in the upper-right.

   ![Edit connection](assets/connection-add-dateset2.png)

1. Scroll to or search for the dataset that was automatically created when you created the Analytics source connector. 

   The name of this dataset is the name of your report suite, followed by `midValues`. For example: `My report suite midValues`

1. Select the checkbox next to the dataset name, then select **[!UICONTROL Next]**.

   ![Edit connection](assets/connection-add-dataset3.png)

1. 

1. They will have to edit their Web SDK connection that they already set up, and add the midvalues dataset (The Analytics source connector. This is typically named _the name of the report suite_ with midvalues suffix.) They'll add Datasets to the Connection and select the midvalues dataset. Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped. 

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).

