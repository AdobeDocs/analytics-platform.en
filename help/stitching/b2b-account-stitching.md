---
title: B2B Account Stitching
description: Learn how B2B account stitching in Customer Journey Analytics enriches event datasets with account information and enables complete journey analysis across your B2B data.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
    internal-label: Stitching
---
# B2B account stitching

B2B account stitching enriches your event datasets with account information and enables complete analysis across the full customer journey in Customer Journey Analytics. When events lack an account ID, which Customer Journey Analytics B2B edition requires for ingestion, account stitching derives and adds that information automatically using a [person-to-account mapping dataset](#prerequisites) you provide.

Without account stitching, any event that does not contain an account ID is dropped during ingestion. ccount stitching eliminates this barrier by looking up the account associated with the person on each event, adding the account ID both as the event is ingested and retroactively.

>[!NOTE]
>
>B2B account stitching requires that the functionality is available in your environment before you can configure the functionality.

Account stitching performs the following operations on your datasets:

* **Elevate person identity**: The person ID on each event is elevated to your desired identity namespace using the identity graph.
* **Add missing account information**: For events that contain a person ID, the [person-to-account mapping](#prerequisites) is used to derive and add the account information. Any account information on the event itself is used as a fallback method.

## Prerequisites

Before you enable B2B account stitching, prepare the following datasets in Adobe Experience Platform:

| Dataset | Required | Description |
|---|---|---|
| **person-to-account dataset** | Required | A lookup (record, non-time series) dataset that contains at a minimum a person ID (with namespace) and an account ID. These IDs are used to derive the person-to-account relationship map. |

>[!IMPORTANT]
>
>The person ID field in your **[!UICONTROL person-to-account]** dataset must be marked as an identity in your schema.

## Enable account stitching

You enable and configure B2B account stitching at the connection level, and then activate account stitching on individual event datasets within that connection.

### Configure B2B stitching settings

1. In Customer Journey Analytics, navigate to **[!UICONTROL Connections]** and [create a new connection](/help/connections/create-connection.md#create-a-connection) or [edit an existing connection](/help/connections/create-connection.md#edit-a-connection).

1. In **[!UICONTROL Connection settings]**, set the **[!UICONTROL Primary ID]** to ![Building](/help/assets/icons/Building.svg) **[!UICONTROL Account]**.

1. Select **[!UICONTROL Open B2B stitching configuration]**.

   ![B2B saccount titching configuration](assets/b2b-account-stitching-configuration.png)

   >[!NOTE]
   >
   >A previously configured B2B stitching configuration for an unsaved connection is indicated with **[!UICONTROL _Unsaved changes_]**. You cannot modify **[!UICONTROL Optional containers]** for a previously configured B2B stitching configuration.

1. In the **[!UICONTROL B2B stitching configuration]** dialog:

   ![B2B stitching configuration](assets/b2b-stitching-configuration.png)

   1. Configure the **[!UICONTROL Person]** section:
      
      * Select a **[!UICONTROL Person Identifier Namespace]**, for example **[!UICONTROL Email]**, to which you want any person ID elevated. This field is required.

   1. Configure the **[!UICONTROL Account]** section underneath **[!UICONTROL Person to Account]**. 

      | Field | Required | Description |
      |---|:---:|---|
      | **[!UICONTROL Person to Account dataset]** | ![Required](/help/assets/icons/Required.svg) | Select the lookup (record or non-time series dataset) that maps persons to accounts. |
      | **[!UICONTROL Person field]** | ![Required](/help/assets/icons/Required.svg) | Select the field in the dataset that contains the person ID. That field must be marked as an identity and cannot be the same as the **[!UICONTROL Account]** field or **[!UICONTROL Start time]** field. |
      | **[!UICONTROL Account field]** | ![Required](/help/assets/icons/Required.svg) | Select the field in the dataset that contains the account ID. That field cannot be the same as the **[!UICONTROL Person]** field or **[!UICONTROL Start time]** field. |
      | **Start time field** | | Select a timestamp field that indicates when the person-to-account relationship became active. |

      >[!NOTE]
      >
      >If an error occurs while loading the field options, the drop-down menus will appear empty and an error indicator appears underneath each affected field. Verify your dataset schema and try again.

   1. Select **[!UICONTROL Save]** to close the **[!UICONTROL B2B stitching configuration]** dialog and return to the connection settings.

   1. The **[!UICONTROL _Unsaved changes_]** indicator appears next to the **Open B2B stitching configuration** button until you [save](#save) the connection.


### Enable B2B stitching on event datasets

After configuring B2B stitching at the connection level, you must enable B2B account stitching individually for each event dataset that you want stitched.

1. In Connection settings, select **[!UICONTROL Add datasets]** or open the settings for an existing event dataset.<br/>See [Add datasets](/help/connections/create-connection.md#add-datasets) or [Edit a dataset](/help/connections/create-connection.md#edit-a-dataset) for more information.

1. For the specific event dataset for which you want to configure B2B account stitching, switch **[!UICONTROL Enable Person to Account stitching]** on.

   >[!BEGINTABS]

   >[!TAB On]

   When **[!UICONTROL Enable Person to Account stitching]** is **on**, you have configured B2B account stitching for the dataset.
   
   * The configuration of a person ID is required. That person ID is used to lookup the account ID based on the [Person-to-Account dataset](#prerequisites).
   * The configuration of an account ID is optional.

   ![B2B account stitching on event dataset on](assets/b2b-event-dataset-stitching-on.png)

   >[!TAB Off]

   When **[!UICONTROL Enable Person to Account stitching]** is **off**, you have *not* configured B2B account stitching for the dataset.

   * The configuration of an account ID is required. 
   * The configuration of a person ID is optional.

   ![B2B account stitching on event dataset off](assets/b2b-event-dataset-stitching-off.png)


   >[!ENDTABS]




### Save

After you have configured the B2B stitching configuration and have finished adding or editing datasets, select **[!UICONTROL Save]** to save the connection.

>[!IMPORTANT]
>
>Once a connection is saved, the B2B stitching configuration becomes immutable. To view your settings after saving, select **Open B2B stitching configuration**. All fields will be shown in a read-only state. Additionally, if the dataset that is used for [person-to-account mapping](#prerequisites) is deleted in Experience Platform, this connection will be deleted.

## Data update schedule

Account stitching derives the identity map from your [person-to-account dataset](#prerequisites) daily and uses this information to update datasets enabled for stitching on the following schedule:

| Replay | Frequency | Data window |
|---|---|---|
| Short-term  | Weekly | Last 7 days |
| Long-term  | Monthly | Last 3 months |

## Privacy and data hygiene

Account stitching honors standard privacy and hygiene requests for person identities, consistent with B2C stitching behavior. If a person ID is later removed through a Privacy or Hygiene request, the associated stitching performed using the identity graph is reversed.

B2B entities such as accounts, account IDs and global account IDs that are added to events through stitching are not removed as part of privacy or hygiene requests. These values do not contain personally identifiable information, so no legal obligation exists to remove these values.

>[!MORELIKETHIS]
>
>* [Stitching overview](overview.md)
>* [Configure a connection for B2B](../connections/create-connection.md)
>* [Frequently asked questions about stitching](faq.md)

