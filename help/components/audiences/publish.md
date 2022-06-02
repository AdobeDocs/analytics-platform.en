---
title: Create and publish audiences to Real-time Customer Profile
description: Learn how to publish audiences from Customer Journey Analytics
---

# Create and publish audiences

This topic discusses how to publish audiences discovered in Customer Journey Analytics (CJA) to [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) in Adobe Experience Platform for customer targeting and personalization.

## Create audience

1. To create audiences, you have three ways to get started:

   | Creation method | Details |
   | --- | --- |
   | From **[!UICONTROL Components] > [!UICONTROL Audiences]** | The Audiences Manager page opens. Click **[!UICONTROL Create audience]** and the [!UICONTROL Audience builder] opens. |
   | From within a Freeform table | Right-click an item in a Freeform table and select **[!UICONTROL Create an audience from selection]**. Using this method pre-populates the filter with the dimension or dimension item you selected in the table. |
   | From the filter editing UI | Check the box that says **[!UICONTROL Create an audience from this filter]**. Using this method pre-populates the filter. |

   {style="table-layout:auto"}

1. Configure the audience.

   | Setting | Description |
   | --- | --- |
   | [!UICONTROL Name] | The name of the audience. |
   | [!UICONTROL Tags] | Any tags that you want assigned to the audience for organizational purposes. You can use a pre-existing tag or enter a new one.|
   | [!UICONTROL Description] | Add a good description of the audience, to differentiate it from others. |
   | [!UICONTROL Refresh frequency] | The frequency at which you want to refresh the audience.<ul><li>You can choose to create a one-time audience (default) that needs no refreshing, which would be helpful for specific one-time campaigns, for example.</li><li>You can select other refresh intervals. For the 4-hour frequency, there is a limit of 150 audiences, since this refresh rate is very processing intensive. For other intervalls, there is no maximum number of audiences.</li></ul> |
   | Expiration date | When the audience will stop refreshing. The default is 1 year from the creation date. |
   | Refresh lookback window | Specifies how far back in your data window you want to go when creating this audience. The max. is 90 days. Expiring audiences are treated similarly to expiring scheduled reports - the admin gets an email a month before the schedule expires. |
   | [!UICONTROL One-time date range] | Date range when you want the one-time audience to be published. |
   | [!UICONTROL Filter] | Filters are the main input to the audience. You can add up to 20 filters. These filters can be joined with `And` or `Or` operators.  |

   {style="table-layout:auto"}

1. Interpret the data preview.

   The audience preview appears in the right rail.

   | Preview setting | Description |
   | --- | --- |
   | Data preview window | The date range for the audience. |
   | Total people in the audience | A summary number that can go as high as 100 Million. |
   | Audience size limit | Shows how far from the 100 Million limit this audience is. |
   | Estimated audience return |  |
   | Estimated to return | A summary number...  |
   | Preview metrics |  |

   {style="table-layout:auto"}


