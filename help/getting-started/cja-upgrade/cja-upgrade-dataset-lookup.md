---
title: Create lookup datasets to classify data in Customer Journey Analytics
description: Learn how to create lookup datasets to classify data in Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: f5443ddd-81d0-43cc-99cb-215e7ddf5acf
---
# Create lookup datasets to classify data in Customer Journey Analytics {#upgrade-lookup-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-lookup-dataset-create"
>title="Create a lookup dataset for each dimension containing classification data"
>abstract="Similar to classifications data in Adobe Analytics, lookup datasets are the method for classifying data in Customer Journey Analytics."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Similar to classifications data in Adobe Analytics, lookup datasets are the method for classifying data in Customer Journey Analytics. 

When using the Analytics source connector, some standard lookup datasets are automatically applied at report time. For more information, see [Add standard lookups to your datasets](/help/connections/standard-lookups.md).

In order to classify data in Customer Journey Analytics when using the Experience Platform Web SDK, you need to create a custom schema and a lookup dataset for each dimension that contains data that you want to classify.

## Create a custom schema to use with the lookup dataset

Create a new custom schema for each dimension that contains data that you want to classify in Customer Journey Analytics. When you create the lookup dataset in a later step, it will reference this schema. 

Repeat this process for each dimension that contains data that you want to classify.

To create a schema for use with a lookup dataset in Customer Journey Analytics:

1. In Adobe Experience Platform, select **[!UICONTROL Schemas]** in the **[!UICONTROL Data Management]** section in the left rail.

1. Select **[!UICONTROL Create schema]**.

   ![Create schema button](assets/schema-create.png)

1. Select **[!UICONTROL Manual]**. This allows you to manually add fields and field groups to your schema. Choose **[!UICONTROL Select]** to proceed to the next page of the creation wizard.  

1. On the **[!UICONTROL Schema details]** page, select **[!UICONTROL Other]**, then select **[!UICONTROL Custom]**.

   ![Create custom](assets/schema-custom.png)

1. Select **[!UICONTROL Create class]**.

   <!-- add screenshot -->

1. In the **[!UICONTROL Create class]** dialog box, specify a name and description for the schema, select **[!UICONTROL Record]**, then select **[!UICONTROL Create]**.

1. Continue with [Create a lookup dataset](#create-a-lookup-dataset).

## Create a lookup dataset

After you [create a custom schema](#create-a-custom-schema-to-use-with-the-lookup-dataset) to use for a lookup dataset, you need to create the lookup dataset and map it to your schema.

Repeat this process for each dimension that contains data that you want to classify.

To create a lookup dataset for use with a schema in Customer Journey Analytics:

>[!NOTE]
>
>The following process uses a CSV file to create the dataset. You could also use any other method available for importing data into Experience Platform, such as setting up a datastream.

1. In Adobe Experience Platform, select **[!UICONTROL Workflows]** in the left rail. 

   ![Create custom](assets/lookup-dataset-workflows.png)

1. Select **[!UICONTROL Map CSV to XDM schema]**, then select **[!UICONTROL Launch]**.

1. In the **[!UICONTROL Dataset details]** section, select **[!UICONTROL New dataset]**.

1. Specify a name and description for your dataset.

1. In the **[!UICONTROL Schema]** field, select the schema that you created for lookup datasets, as described in [Create a schema for lookup datasets](#create-a-schema-for-lookup-datasets).

1. Select **[!UICONTROL Next]**.

1. On the **[!UICONTROL Map CSV to XDM schema page]**, in the **[!UICONTROL Upload files]** section, select **[!UICONTROL Choose files]**, then browse your file system for the file that contains the classification information for the dimension for which you want to apply classification data. For example, this might be a spreadsheet that lists the field IDs and corresponding field names. <!-- correct? How can I better explain what this file is?-->

   ![Map CSV file](assets/lookup-map-csv.png)

1. Select **[!UICONTROL Next]**

1. After the file uploads, review the mappings to make sure they are accurate. The columns of the CSV file are listed under **[!UICONTROL Source Data]** and their corresponding XDM schema fields are listed under **[!UICONTROL Target Field]**.

   Platform automatically provides intelligent recommendations for auto-mapped fields based on the target schema or dataset that you selected. You can manually adjust mapping rules to suit your use cases.

   For more information about the mapping process, see [Map a CSV file to an existing XDM schema](https://experienceleague.adobe.com/en/docs/experience-platform/ingestion/tutorials/map-csv/existing-schema) in the Experience Platform documentation.

1. Select **[!UICONTROL Finish]**.

1. Continue with [Add the lookup dataset to your connection in Customer Journey Analytics](#add-the-lookup-dataset-to-your-connection-in-customer-journey-analytics).

## Add the lookup dataset to your connection in Customer Journey Analytics 

After you [create a custom schema](#create-a-custom-schema-to-use-with-the-lookup-dataset) and you [create a lookup dataset](#create-a-lookup-dataset), you need to add the lookup dataset to your connection in Customer Journey Analytics.

Repeat this process for each dimension that contains data that you want to classify.

To add the lookup dataset to your connection in Customer Journey Analytics:

1. In Customer Journey Analytics, select the **[!UICONTROL Connections]** tab.

1. Select ![More icon](assets/More.svg) next to the connection where you want to add the lookup dataset, then select **[!UICONTROL Edit]**.

   <!-- add screenshot -->

1. Select **[!UICONTROL Add datasets]**.

1. In the **[!UICONTROL Add datasets]** dialog box, select the lookup dataset that you created, then select **[!UICONTROL Next]**. 

1. In the **[!UICONTROL Person ID]** field, select a person ID from the available identities defined in the your dataset schema that you configured in Experience Platform. <!-- fill out other fields? -->

1. Select **[!UICONTROL Add datasets]**, then select **[!UICONTROL Save]**.

   <!-- is there a step right in between here where you select the dataset -->

1. Using the **[!UICONTROL Key]** field and the **[!UICONTROL Matching key]** field, create a correlation between the field in your lookup dataset with that in your event or summary dataset. 

1. Repeat this process until all lookup datasets are added to your connection in Customer Journey Analytics.

1. {{upgrade-final-step}}

