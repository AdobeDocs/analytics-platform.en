---
description: How to set up users to use the Adobe Analytics dashboard mobile app
title: Set up executives to use dashboards
feature: Analytics Dashboards
role: User, Admin
exl-id: 647f192a-e317-4011-92bc-a8bb8494a3c7
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/78Bp5YSZg7Qs-qBnCfIoS6mjxda7CAglDG19Qq07Fw4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b743a5d9-dc51-41ed-8b2f-86a1f8de430f
    internal-label: Analytics dashboards
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b21c7889-c659-4a99-a779-de1bae57e47e
    internal-label: Scorecards
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments, Segments (CJA)
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Set up executive users to use dashboards

In some cases, executive users may need some additional assistance to access and use the app. This section provides information to help curators provide that assistance.

## Ensure app users have Adobe Analytics access

1. Set up new users in the [CX Enterprise Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html).

1. To be able to share scorecards, you must grant app users permissions to access scorecard components such as Analysis Workspace, the data views that scorecards are based on, as well as segments, metrics and dimensions.

## App users' system prerequisites

To ensure that executive users have access to your scorecards on the app, make sure that:

* The minimum mobile OS requirements on their devices are iOS version 10 or higher, or Android version 4.4 (KitKat) or higher
* They have a valid login into Customer Journey Analytics.
* You have correctly created mobile scorecards for them and have shared these scorecards with them.
* They have access to the Components that the scorecard includes. Note that you can select an option when sharing your scorecards to **[!UICONTROL Share embedded components]**.

## Help executives download and install app

>[!NOTE]
>
>Although the mobile app is named Adobe Analytics dashboard in the app store, the app can be equally used with Customer Journey Analytics mobile scorecards. 

**For executive users on iOS:**

Click the following link (it is also available in Customer Journey Analytics under **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (mobile opp)]**) and follow the prompts to download, install, and open the app:

`[iOS link](https://apple.co/2zXq0aN)`

**For executive users on Android:**

Click the following link (it is also available in Customer Journey Analytics under **[!UICONTROL Tools]** > **[!UICONTROL Analytics dashboards (mobile app)]**) and follow the prompts to download, install, and open the app:

`[Android link](https://bit.ly/2LM38Oo)`

Once downloaded and installed, executive users can sign into the app using their existing Customer Journey Analytics credentials; we support both Adobe and Enterprise/Federated IDs.

![Adobe Analytics dashboards welcome screen](assets/welcome.png)

## Help executives access your scorecard 

1. Have executive users sign into the app.

   The **[!UICONTROL Choose a company]** screen appears. This screen lists the login companies to which the executive user belongs.

1. Have them tap the name of the login company or CX Enterprise Org that applies to the scorecard you shared. 

   The Scorecard list then shows all scorecards that have been shared with the executive under that login company.

1. Have them sort this list by **[!UICONTROL Most recently modified]**, if applicable.

1. Have them tap the name of the Scorecard to view it.

    ![Choose a company](assets/accesscard.png)


### Explain scorecard UI

Explain to the executive user how tiles appear in the scorecards you share.

![Explain tiles including the date range, segment, and metrics and dimensions selected](assets/newexplain.png)

![Example Scorecard](assets/intro_scorecard.png)

Additional information on tiles:

* The granularity of the sparklines is dependent on the length of the date range:
* One day shows an hourly trend
  * More than one day and less than a year shows a daily trend
  * One year or more shows a weekly trend
  * Percent value change formula is metric total (current date range) – metric total (comparison date range) / metric total (comparison date range).
  * You can pull the screen down to refresh the Scorecard.


1. Tap a tile to show how a detailed breakdown for the tile works.

    ![Breakdown view](assets/sparkline.png)

    * Tap any point on a sparkline to see data associated with that point on the line.

    * A table is included to display data of dimensions added to the tile. Tap the down arrow to select dimensions. If no dimension was added to the tile, the table displays chart data.

1. To change date ranges for your Scorecard, tap the Date header and select the primary and comparison date range combination you want to view.

    ![Change dates](assets/changedate.png)

## Change app preferences

To change preferences, tap the **[!UICONTROL Preferences]** option shown above. In preferences, you can turn on biometric login or you can set the app for dark mode as shown below:

![Dark mode](assets/darkmode.png)

## Troubleshooting

If the executive user logs in and sees a message saying that nothing has been shared:

![Nothing shared](assets/nothing.png)

* The executive user may have selected the wrong Customer Journey Analytics sandbox, or
* The scorecard may not have been shared with the executive user. 

Verify that the executive user can log into the right Customer Journey Analytics sandbox and that the scorecard has been shared.
