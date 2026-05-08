---
title: Create a custom schema for Customer Journey Analytics
description: Learn how to create a custom schema for Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 902e5890-f970-4f1a-b091-9c3e51a987db
---
# Create a custom schema to use with Customer Journey Analytics {#create-custom-schema}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create"
>title="Create the desired custom schema in Adobe Experience Platform"
>abstract="Use the Adobe Experience Platform UI to create a schema so that Adobe knows the correct format to store your data.<br><br>This step involves the actual creation of the schema agreed upon by your organization. The estimated time to create your schema in the Adobe Experience Platform interface is approximately one week, depending on the number of dimensions and metrics that need to be created."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-create-default-aa"
>title="Create a schema using the Adobe Analytics ExperienceEvent field group"
>abstract="Use the 'Adobe Analytics ExperienceEvent' field group to create a schema in Adobe Experience Platform containing all fields used by Adobe Analytics.<br><br>Creating a schema based on the Adobe Analytics ExperienceEvent field group is simple, taking only a few minutes to complete."

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-profile"
>title="Enable your schema for profile"
>abstract="Enable profile in your schema for use in Adobe Real-time CDP. This step appears because you selected the desire to integrate with Adobe Real-time CDP.<br><br>Since this step involve clicking a single box, this step only takes a few minutes."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}} 

>[!IMPORTANT]
>
>Before you begin creating your custom schema, work with your data team and other stakeholders throughout your organization to identify your organization's ideal schema design for Customer Journey Analytics and the other Adobe Experience Platform applications you use. For more information, see [Architect your schema for use with Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-architect.md).

The following sections describes how to create a schema that can be used with Customer Journey Analytics. The following schema options are available:

* **Custom XDM schema:** (Recommended) Allows for a streamlined schema that is tailored to the needs of your organization and the specific Platform applications that you use. Any required future changes are straightforward.

* **Adobe Analytics schema that uses the Adobe Analytics ExperienceEvent field group:** Requires the addition of thousands of unneeded fields. Any required future changes are more difficult. 

For more information about these schema options, see [Choose your schema for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

## Create the schema

The custom schema you define for your Web SDK implementation represents the model of the data that you collect into Adobe Experience Platform. 

To create a custom schema:

<!-- Should we single source this instead of duplicate it? The following steps were copied from: /help/data-ingestion/aepwebsdk.md-->

1. In Adobe Experience Platform, in the left rail, select **[!UICONTROL Schemas]** within [!UICONTROL DATA MANAGEMENT].

1. Select **[!UICONTROL Create schema]**. 
 
1. In the **[!UICONTROL Select a class]** step of the Create schema wizard: 

   1. Select **[!UICONTROL Experience Event]**.

      ![Create a schema highlighting Experience Event](assets/create-ee-schema-wizard-step-1.png)

      >[!INFO]
      >
      >    An Experience Event schema is used to model the _behavior_ of a profile (like scene name, push button to add to cart). An Individual Profile schema is used to model the profile _attributes_ (like name, email, gender).

   1. Select **[!UICONTROL Next]**.


1. In the [!UICONTROL Name and review step] of the [!UICONTROL Create schema] wizard:

   1. Enter a **[!UICONTROL Schema display name]** for your schema and (optional) a **[!UICONTROL Description]**.

      ![Create schema window showing the Name your schema fields](assets/create-ee-schema-wizard-step-2.png)

   1. Select **[!UICONTROL Finish]**.

1. Add all field groups that contain any fields that you want to include in your schema.

   Field groups are reusable collections of objects and attributes that allow you to easily extend your schema.

   1. In the **[!UICONTROL Field groups]** section, select **[!UICONTROL + Add]**.

      ![Add field group](assets/add-field-group-button.png)

   1. In the [!UICONTROL Add fields groups] dialog, select the **[!UICONTROL AEP Web SDK ExperienceEvent]** field group from the list. 

      ![AEP Web SDK ExperienceEvent fieldgroup](assets/select-aepwebsdk-experienceevent.png)
    
      You can select the preview button, to see a preview of the fields that are part of this field group, like `web > webPageDetails > name`. 

      ![AEP Web SDK ExperienceEvent fieldgroup preview](assets/aepwebsdk-experiencevent-preview.png)

      Select **[!UICONTROL Back]** to close the preview.   

   1. (Optional) Select any additional field groups that you want to include.   

      If you chose to use the default Adobe Analytics schema rather than creating a custom XDM schema, you can add the Adobe Analytics ExperienceEvent field group now. However, Adobe recommends creating a custom XDM schema rather than adding this field group.

      For more information about these schema options, see [Choose your schema for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md).

   1. Select **[!UICONTROL Add field groups]**.

1. (Optional) If you have custom fields that you want to include in your schema, create a custom field group and add the custom fields to the field group. 

   1. In the **[!UICONTROL Field groups]** section, select **[!UICONTROL + Add]**.

      ![Add field group](assets/add-field-group-button.png) 

   1. In the [!UICONTROL Add fields groups] dialog, select **[!UICONTROL Create new field group]**.

   1. Specify a display name and optional description, then select **[!UICONTROL Add field groups]**. 

1. Select **[!UICONTROL +]** next to your schema name in the [!UICONTROL Structure] panel.

   ![Example Schema Add Field button](assets/example-schema-plus.png)

1. In the [!UICONTROL Field Properties] panel, enter `Identification` as the name, **[!UICONTROL Identification]** as the [!UICONTROL Display name], select **[!UICONTROL Object]** as the [!UICONTROL Type] and select **[!UICONTROL ExperienceEvent Core v2.1]** as the [!UICONTROL Field Group].

   >[!NOTE]
   >
   >If that field group is not available, look for another field group containing identity fields. Or [create a new field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html) and [add new identity fields](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/identity.html#define-a-identity-field) (like `ecid`, `crmId`, and others you need) to the field group and select that new field group.

    ![Identification Object](assets/identification-field.png)

    The identification object adds identification capabilities to your schema. In your case, you want to identify profiles visiting your site using the Experience Cloud ID and email address. There are many other attributes available to track your person's identification (for example customer id, loyalty id).

    Select **[!UICONTROL Apply]** to add this object to your schema.

1. Select the **[!UICONTROL ecid]** field in the identification object you just added, and select **[!UICONTROL Identity]** and **[!UICONTROL Primary Identity]** and **[!UICONTROL ECID]** from the [!UICONTROL Identity namespace] list in the right panel.

   ![Specifiy ECID as identity](./assets/specify-identity.png)

   You are specifying the Experience Cloud Identity as the primary identity the Adobe Experience Platform Identity service can use to combine (stitch) the behavior of profiles with the same ECID.

   Select **[!UICONTROL Apply]**. You see that a fingerprint icon appears in the ecid attribute.

1. Select the **[!UICONTROL email]** field in the identification object you just added, and select **[!UICONTROL Identity]** and **[!UICONTROL Email]** from the [!UICONTROL Identity namespace] list in the [!UICONTROL Field Properties] panel. 

   ![Specifiy email as identity](./assets/specify-email-identity.png)

   You are specifying the email address as another identity the Adobe Experience Platform Identity service can use to combine (stitch) the behavior of profiles.

   Select **[!UICONTROL Apply]**. You see that a fingerprint icon appears in the email attribute.

    Select **[!UICONTROL Save]**.

1. (Optional) If you want to integrate Customer Journey Analytics with RTCDP, select the root element of your schema displaying the name of the schema, then select the **[!UICONTROL Profile]** switch.

   You are prompted to enable the schema for profile. Once enabled, when data is ingested into datasets based on this schema, that data is merged into the Real-Time Customer Profile. 
    
   See [Enable the schema for use in Real-Time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html#profile) for more information.

   >[!IMPORTANT]
   >
   >After you enable a schema for profile, it cannot be disabled for profile.

   ![Enable schema for profile](./assets/enable-for-profile.png)

1. Select **[!UICONTROL Save]** to save your schema.

   You have created a minimal schema that models the data you can capture from your website. The schema allows profiles to be identified using the Experience Cloud Identity and email address. By enabling the schema for profile, you ensure data captured from your website is added to the Real-Time Customer Profile.

   Next to behavior data, you can also capture profile attribute data from your site (for example details of profiles subscribing to a newsletter). 

   To capture this profile data, you would:

   * Create a schema based on the XDM Individual Profile class.

   * Add the Profile Core v2 field group to the schema.

   * Add an identification object based on the Profile Core v2 field group.

   * Define Experience Cloud ID as primary identifier and email as identifier.

   * Enable the schema for profile

   See [Create and edit schemas in the UI](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html) for more information on adding and removing field groups and individual fields to a schema.

{{upgrade-final-step}}
