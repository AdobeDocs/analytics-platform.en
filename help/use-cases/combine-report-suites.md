---
title: Combine report suites with different schemas
description: Learn how to use Data Prep to combine report suites with different schemas
exl-id: 2656cc21-3980-4654-bffb-b10908cb21f5
---
# Combine Report Suites with different schemas

The [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) brings report suite data from Adobe Analytics into the Adobe Experience Platform (AEP) for use by AEP applications, such as Real-time Customer Data Platform and Customer Journey Analytics (CJA). Each report suite brought into AEP is configured as an individual source connection dataflow, and each dataflow lands as a dataset within the AEP data lake. The Analytics Source Connector creates one dataset per report suite.

CJA customers use [connections](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en) to integrate datasets from AEP data lake into CJA's Analysis Workspace. However, when combining report suites within a connection, schema differences between report suites need to be resolved using AEP's [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) functionality. The purpose is to ensure that Adobe Analytics variables such as props and eVars have a consistent meaning in CJA.

## Schema differences between report suites are problematic

Suppose your company wants to bring data from two different report suites into AEP for use by CJA, and assume the schemas for the two report suites have differences:

| Report Suite A | Report Suite B |
| --- | --- |
| eVar1 = Search term | eVar1 = Business unit |
| eVar2 = Customer category | eVar2 = Search term |

For the sake of simplicity, let's say these are the only defined eVars for both report suites.

Further, suppose you perform the following actions:

- Create an Analytics source connection (without use of data prep) that ingests **Report Suite A** into AEP data lake as **Dataset A**.
- Create an Analytics source connection (without use of data prep) that ingests **Report Suite B** into AEP data lake as **Dataset B**.
- Create a [CJA connection](/help/connections/create-connection.md) called **All Report Suites** that combines Dataset A and Dataset B.
- Create a [CJA data view](/help/data-views/create-dataview.md) called **Global View** that is based on the All Report Suites connection.

Without the use of Data Prep to resolve the schema differences between Dataset A and Dataset B, the eVars in the Global View data view will contain a mixture of values:

| Global View data view in CJA |
| --- |
| eVar1 => a mix of search terms and business units |
| eVar2 => a mix of customer categories and search terms |

This situation results in meaningless reports for eVar1 and eVar2:

- The eVar fields contain a mixture of values with different semantic meanings. 
- Search terms are distributed between eVar1 and eVar2.
- It is not possible to use different attribution models for each of search terms, business units, and customer categories.

## Use AEP Data Prep to resolve schema differences between report suites

The Experience Platform Data Prep functionality is integrated with the Analytics Source Connector and can be used to resolve the schema differences described in the scenario above. This results in eVars with consistent meanings in the CJA data view. (The naming conventions used below can be customized to suit your needs.)

1. Before creating the source connection dataflows for Report Suite A and Report Suite B, [Create a new schema](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/overview.html?lang=en) in AEP (we'll call it **Unified Schema** in our example.) Add the following to the schema:

   | "Unified Schema" |
   | --- |
   | **XDM ExperienceEvent** class |
   | **Adobe Analytics ExperienceEvent Template** field group |

1. Add another field group to the schema or [create a custom field group](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/field-groups.html?lang=en#:~:text=To%20create%20a%20new%20field,section%20in%20the%20left%20rail) and add it to the schema. We'll create a new field group and call it **Unified Fields**. Then we'll add the following fields to the new field group:

   | "Unified Fields" custom field group |
   | --- |
   | Search term |
   | Business unit |
   | Customer category|

1. Create the source connection dataflow for **Report Suite A**, selecting **Unified Schema** for use in the dataflow. Add custom mappings to the dataflow as follows:

   | Report Suite A source field | Destination field from Unified Fields field group | 
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\<path>_.Search_term | 
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\<path>_.Customer_category |
  
   >[!NOTE]
   >
   >The XDM path for your destination fields will depend on how you set up your custom field group.

1. Create the source connection dataflow for **Report Suite B**, again selecting **Unified Schema** for use in the dataflow. The workflow shows that two fields have a descriptor name conflict. This is because the descriptors for eVar1 and eVar2 are different in Report Suite B than they were in Report Suite A. But we already know this, so we can safely ignore the conflict and use custom mappings as follows:

   | Report Suite B source field | Destination field from Unified Fields field group |
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | _\<path>_.Business_unit |
   | _experience.analytics.customDimensions.eVars.eVar2 | _\<path>_.Search_term |

1. Now create an **All Report Suites** connection for CJA, combining Dataset A and Dataset B.

1. Create a **Global view** data view in CJA. Ignore the original eVar fields and include only the fields from the Unified Fields field group.

   **Global View** data view in CJA: 

   | Source field | Include in data view? |
   | --- | --- | 
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\<path>_.Search_term | Yes |
   | _\<path>_.Customer_category | Yes |
   | _\<path>_.Business_unit | Yes | 

You have now mapped eVar1 and eVar2 from the source report suites to three new fields. Note that another advantage of using Data Prep mappings is that the destination fields are now based on semantically meaningful names (Search term, Business Unit, Customer category) instead of the less meaningful eVar names (eVar1, eVar2.)

   >[!NOTE]
   >
   >The Unified Fields custom field group, and associated field mappings can be added to existing Analytics Source Connector dataflows and datasets at any time. However, this impacts going-forward data only.

## More than just report suites

The capabilities of Data Prep to combine datasets with different schemas goes beyond Analytics report suites. Suppose you have a two datasets containing the following data:

| Dataset A = Analytics report suite via Analytics Source Connector | 
| --- |
| `eVar1` => Customer Category |

| Dataset B = Call center data | 
| --- |
| Some_field => Customer Category | 

Using Data Prep, you can combine the Customer Category in eVar 1 in the Analytics data with the Customer Category in Some_field in the call center data. Here is one way you might do that. Again, the naming convention can be altered to suit your needs.

1. Create a schema in AEP. Add the following to the schema:

   |"Extended Schema" | 
   | --- | 
   | **XDM Experience Event** class | 
   | **Adobe Analytics Experience Event Template** field group | 

1. Create a new field group and add it to the schema. Add fields to the field group:

   | "Customer Info" custom field group |
   | --- |
   | Customer_category | 

1. Create the dataflow for **Dataset A**, selecting **Extended Schema** as your schema. Add custom mappings to the dataflow as follows:

   | Dataset A source field | Destination field from Customer Info field group |
   | --- | --- |
   | \_experience.analytics.customDimensions.eVars.eVar2 | _\<path>_.Customer_category | 

1. Create the dataflow for **Dataset B**, again selecting **Extended Schema** as your schema. Add custom mappings to the dataflow as follows:

   | Dataset B source field | Destination field from Customer Info field group |
   | --- | --- |
   | _\<path>_.Some_field | _\<path>_.Customer_category |

1. Create a CJA connection which combines Dataset A and Dataset B. 

1. Create a data view in CJA, using the CJA connection you just created. Ignore the original eVar fields and include only the fields from the Customer Info field group.

   Data view in CJA:

   | Source field | Include in data view? | 
   |---|---|
   | \_experience.analytics.customDimensions.eVars.eVar1 | No |
   | \_experience.analytics.customDimensions.eVars.eVar2 | No |
   | _\<path>_.Customer_category | Yes |
  
## Data Prep vs. Component ID

As described above, Data Prep allows you to map different fields together across multiple Adobe Analytics report suites. This is helpful in CJA when you want to combine data from multiple datasets into a single CJA connection. However, if you intend to keep the report suites in separate CJA connections but you want to use one set of reports across those those connections and data views, changing the underlying Component ID in CJA provides a way to make reports compatible even if schemas are different. See [Component Settings](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/overview.html?lang=en) for more information.

Changing the Component ID is a CJA-only function and does not impact data from the Analytics Source Connector that is sent to Real-time Customer Profile and RTCDP.
