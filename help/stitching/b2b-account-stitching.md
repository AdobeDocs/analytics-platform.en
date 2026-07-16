---
title: B2B Account Stitching
description: Learn how B2B account stitching in Customer Journey Analytics enriches event datasets with account information and enables complete journey analysis across your B2B data.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: true
role: Admin
autotag-review: '2026-05-19T11:01:07.331Z'
TQID: 'https://experienceleague.adobe.com/-7rHOhYVCp-nSMqdE7YlAlCJ0zRQYvPOViMHSCNuKV8'
product_v2:
  - id: d3f42e9e-bb51-4077-a732-358b801d8b29
    internal-label: Customer Journey Analytics B2B
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: faea9abd-7024-4c5e-a5b4-87919e09b24b
    internal-label: Stitching
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
---
# B2B account stitching

B2B account stitching enriches your event datasets with account information and enables complete analysis across the full customer journey in Customer Journey Analytics. When events lack an account ID, which Customer Journey Analytics B2B edition requires for ingestion, account stitching derives and adds that information automatically using a [person-to-account mapping dataset](#prerequisites) you provide.

Without account stitching, any event that does not contain an account ID is dropped during ingestion. Account stitching resolves this limitation by looking up the account associated with the person on each event, adding the account ID both as the event is ingested and retroactively.

>[!NOTE]
>
>B2B account stitching requires that you are entitled to the [Customer Journey Analytics B2B edition](/help/getting-started/cja-b2b-edition.md) in your environment before you can configure the functionality.

Account stitching performs the following operations on your datasets:

* **Elevate person identity**: The person ID on each event is elevated to the configured identity namespace using the identity graph.
* **Add missing account information**: For events that contain a person ID, the [person-to-account mapping](#prerequisites) is used to derive and add the account information. Any account information on the event itself is used as a fallback method.

## Prerequisites

Before you enable B2B account stitching, prepare the following datasets in Adobe Experience Platform:

| Dataset | Required | Description |
|---|---|---|
| **person-to-account dataset** | Required | A lookup (record, non-time series) dataset that contains at a minimum a person ID (with namespace) and an account ID. These IDs are used to derive the person-to-account relationship map. |

>[!IMPORTANT]
>
>The person ID field in your **[!UICONTROL person-to-account]** dataset must be marked as an identity in your schema.

## Enable account stitching {#enable-account-stitching}

You enable and configure B2B account stitching at the connection level, and then activate account stitching on individual event datasets within that connection.

### Configure B2B stitching settings {#configure-b2b-stitching-settings}

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_open_configuration"
>title="Configure B2B account stitching"
>abstract="Select **[!UICONTROL Open B2B stitching configuration]** to configure B2B account stitching. If the connection is not saved yet, the configuration is labeled with **[!UICONTROL _Unsaved changes_]**."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_identifier_namespace"
>title="Person identifier namespace"
>abstract="Select the most relevant person identity namespace for your reporting. For example, Email."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person_to_account_dataset"
>title="Person to account dataset"
>abstract="Select the field in the dataset that contains person IDs. This field's namespace can either differ from or be the same as the selected Person Identifier Namespace (B2B stitching configuration). If the two namespaces differ, link the namespaces in the Identity Graph."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_person"
>title="Person"
>abstract="Select the field in the dataset that contains the person ID. That field must be marked as an identity and cannot be the same as the **[!UICONTROL Account]** field or **[!UICONTROL Start time]** field."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_account"
>title="Account"
>abstract="Select the field in the dataset that contains the unique account identifier values. The account ID info will be made available on the rows of any event datasets with stitching enabled."

>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_start_time"
>title="Start time"
>abstract="Select a timestamp field that indicates when the person-to-account relationship became active."
>additional-url="url"
>additional-url="url"


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
      | **[!UICONTROL Person]** | ![Required](/help/assets/icons/Required.svg) | Select the field in the dataset that contains the person ID. That field must be marked as an identity and cannot be the same as the **[!UICONTROL Account]** field or **[!UICONTROL Start time]** field. |
      | **[!UICONTROL Account]** | ![Required](/help/assets/icons/Required.svg) | Select the field in the dataset that contains the account ID. That field cannot be the same as the **[!UICONTROL Person]** field or **[!UICONTROL Start time]** field. |
      | **Start time** | | Select a timestamp field that indicates when the person-to-account relationship became active. |

      >[!NOTE]
      >
      >If an error occurs while loading the field options, the drop-down menus will appear empty and an error indicator appears underneath each affected field. Verify your dataset schema and try again.

   1. Select **[!UICONTROL Save]** to close the **[!UICONTROL B2B stitching configuration]** dialog and return to the connection settings.

   1. The **[!UICONTROL _Unsaved changes_]** indicator appears next to the **Open B2B stitching configuration** button until you [save](#save) the connection.


### Enable B2B stitching on event datasets


>[!CONTEXTUALHELP]
>id="connection_b2b_stitching_enable_person_to_account"
>title="Enable person to account stitching"
>abstract="If enabled, this dataset uses B2B Person to Account stitching. The **[!UICONTROL Person ID]** values will be elevated to the ones from the configured Person Identifier Namespace, then used to lookup the account ID based on the Person to Account dataset (B2B stitching configuration interface). The Account ID field is optional for the current dataset, and to be used as secondary source of data. If disabled, this dataset does not use B2B Person to Account stitching and you have to select a required Account ID instead."

After configuring B2B stitching at the connection level, you must enable B2B account stitching individually for each event dataset that you want stitched.

1. In Connection settings, select **[!UICONTROL Add datasets]** or open the settings for an existing event dataset.<br/>See [Add datasets](/help/connections/create-connection.md#add-datasets) or [Edit a dataset](/help/connections/create-connection.md#edit-a-dataset) for more information.

1. For the specific event dataset for which you want to configure B2B account stitching, switch **[!UICONTROL Enable Person to Account stitching]** on.

>[!BEGINTABS]

>[!TAB On]

When **[!UICONTROL Enable Person to Account stitching]** is **on**, you have configured B2B account stitching for the dataset.

* The configuration of a person ID is required. That person ID is used to look up the account ID based on the [person-to-account dataset](#prerequisites).
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
>Once a connection is saved, the B2B stitching configuration becomes immutable. To view your settings after saving, select **Open B2B stitching configuration**. All fields appear in a read-only state. Additionally, if the dataset used for [person-to-account mapping](#prerequisites) is deleted in Experience Platform, this connection is deleted.

## Data update schedule

Account stitching derives the identity map from your [person-to-account dataset](#prerequisites) daily and uses this information to update datasets enabled for stitching on the following schedule:

| Replay | Frequency | Data window |
|---|---|---|
| Short-term  | Weekly | Last 7 days |
| Long-term  | Monthly | Last 3 months |

## Privacy and data hygiene

Account stitching honors standard privacy and hygiene requests for person identities, consistent with B2C stitching behavior. If a person ID is later removed through a Privacy or Hygiene request, the associated stitching performed using the identity graph is reversed.

B2B entities like accounts, account IDs, and global account IDs added to events through stitching are not removed during privacy or hygiene requests. These values do not contain personally identifiable information, so no legal obligation exists to remove these values.

>[!MORELIKETHIS]
>
>* [Stitching overview](overview.md)
>* [Configure a connection for B2B](../connections/create-connection.md)
>* [Frequently asked questions about stitching](faq.md)

