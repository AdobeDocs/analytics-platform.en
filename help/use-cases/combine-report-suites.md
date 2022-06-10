# Combining Report Ruites Having Different Schemas
## Overview

The [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) provides a means to bring report suite data from Adobe Analytics into the Adobe Experience Platform for use by AEP applications such as RTCDP and CJA. Each report suite brought into AEP is configured as an individual source connection dataflow, and each dataflow lands as a dataset within the AEP data lake. (The Analytics Source Connector will create one dataset per report suite.)

CJA customers use [connections](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en) to integrate datasets from AEP data lake into CJA's Analysis Workspace. *However, when combining report suites within a connection, schema differences between report suites need to be resolved using AEP's [Data Prep](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=en) functionality in order to ensure Adobe Analytics variables such as props and eVars have a consistent meaning in CJA.*

## How schema differences between report suites are problematic

Suppose your company wants to bring data from two different report suites into AEP for use by CJA, and assume the schemas for the two report suites have differences:

| Report Suite A | Report Suite B |
| --- | --- |
| eVar1 => Search term | eVar1 => Business unit |
| eVar 2 => Customer category	| eVar2 => Search term |

For the sake of simplicity we will say these are the only defined eVars for both report suites.

Further, suppose you perform the following actions:

- Create an Analytics source connection (without use of data prep) that ingests **Report Suite A** into AEP data lake as **Dataset A**.
- Create an Analytics source connection (without use of data prep) that ingests **Report Suite B** into AEP data lake as **Dataset B**.
- Create a CJA connection called **All Report Suites** that combines Dataset A and Dataset B.
- Create a CJA data view called **Global View** that is based on the All Report Suites connection.

Without the use of Data Prep to resolve the schema differences between **Dataset A** and **Dataset B**, the eVars in the Global View data view will contain a mixture of values:

| Global View data view in CJA |
| --- |
| eVar1 => a mix of search terms and business units |
| eVar2 => a mix of customer categories and search terms |

This situation will result in meaningless reports for eVar1 and eVar2:

- The eVar fields will contain a mixture of values with different semantic meanings.
- Search terms will be distributed between eVar1 and eVar2.
- It will not be possible to use different attribution models for search terms, business units, and customer categories.

## Using AEP Data Prep to resolve schema differences between report suites for use in CJA

AEP's Data Prep functionality is integrated with ADC and can be used to resolve the schema differences described in the scenario above, resulting in eVars with consistent meanings in the CJA data view. What follows is a description of how this might be accomplished. The naming conventions used below can be customized to suit your needs.

Before creating the source connection dataflows for Report Suite A and Report Suite B, create a custom field group in AEP (we'll call it **Unified Fields** in our example) which contains the following fields:

| Unified Fields custom field group |
| --- |
| Search term |
| Business unit |
| Customer category|

Create a new schema in AEP (we'll call it **Unified Schema** in our example.) Add the following field groups to the schema:

| Field groups for Unified Schema |
| --- |
| XDM Experience Event |
| Adobe Analytics Experience Event Template |
| Unified Fields |

When creating the source connection dataflow for **Report Suite A**, select **Unified Schema** for use in the dataflow. Add custom mappings as follows:

| Report Suite A source field | Destination field from Unified Fields field group | 
| --- | --- |
| \_experience.analytics.customDimensions.eVars.eVar1 | _\<path>_.Search_term | 
| \_experience.analytics.customDimensions.eVars.eVar2 | _\<path>_.Customer_category |
  
Note: The XDM path for your destination fields will depend on how you set up your custom field group.

When creating the source connection dataflow for **Report Suite B**, again select **Unified Schema** for use in the dataflow. The workflow will show that two fields have a descriptor name conflict. This is because the descriptors for eVar1 and eVar2 are different in Report Suite B than they were in Report Suite A. But we already know this so we can safely ignore the conflict and use custom mappings as follows:

| Report Suite B source field	| Destination field from Unified Fields field group | 
| --- | --- |
| \_experience.analytics.customDimensions.eVars.eVar1	| _\<path>_.Business_unit | 
| _experience.analytics.customDimensions.eVars.eVar2	| _\<path>_.Search_term | 

Now Create an **All Report Suites** connection for CJA, combining Dataset A and Dataset B.

Create a **Global view** data view in CJA. Ignore the original eVar fields and include only the fields from the Unified Fields field group.

Global View data view in CJA: 

| Source field | Include in data view? |
| --- | --- | 
| \_experience.analytics.customDimensions.eVars.eVar1 | No |
| \_experience.analytics.customDimensions.eVars.eVar2 | No |
| _\<path>_.Search_term | Yes |
| _\<path>_.Customer_category | Yes |
| _\<path>_.Business_unit | Yes | 

In essence you have now mapped eVar1 and eVar2 from the source report suites to three new fields. Note that another advantage of using Data Prep mappings is that the destination fields are now based on semantically meaningful names (Search term, Business Unit, Customer category) instead of the less meaningful eVar names (eVar1, eVar2.)

Note: The Unified Fields custom field group, and associated field mappings can be added to existing ADC dataflows and datasets, however this will impact going-forward data only.

## More than just report suites

The capabilities of Data Prep to combine datasets with different schemas goes beyond Analytics report suites. Suppose you have a two datasets containing the following data:

| Dataset A = Analytics report suite via ADC | 
| --- |
| eVar1 => Customer Category |

| Dataset B = Call center data | 
| --- |
| Some_field => Customer Category | 

Using Data Prep you can combine the Customer Category in eVar 1 in the Analytics data with the Customer Category in Some_field in the call center data. Here is one way you might do that. Again, the naming convention can be altered to suit your needs.

Create a custom field group:

| Customer Info custom field group |
| --- |
| Customer_category | 

Create a schema in AEP. Add the following field groups to the schema:

| Field groups for Extended Schema | 
| --- | 
| XDM Experience Event | 
| Adobe Analytics Experience Event Template | 
| Customer Info | 

When creating the dataflow for **Dataset A**, select **Extended Schema** as your schema. Add custom mappings as follows:

| Dataset A source field | Destination field from Customer Info field group |
| --- | --- |
| \_experience.analytics.customDimensions.eVars.eVar2 | _\<path>_.Customer_category | 

When creating the dataflow for **Dataset B**, again select **Extended Schema** as your schema. Add custom mappings as follows:

| Dataset B source field | Destination field from Customer Info field group |
| --- | --- |
| _\<path>_.Some_field | _\<path>_.Customer_category |

Create a CJA connection which combines Dataset A and Dataset B. Create a data view in CJA, using the CJA connection you just created. Ignore the original eVar fields and include only the fields from the Customer Info field group.

Data view in CJA:

| Source field	| Include in data view? | 
| ---  | --- |
| \_experience.analytics.customDimensions.eVars.eVar1	| No |
| \_experience.analytics.customDimensions.eVars.eVar2	| No |
| _\<path>_.Customer_category |	Yes |
  
## Data Prep vs. Component ID

As described above, Data Prep allows you to map different fields together across multiple Adobe Analytics report suites. This is helpful in CJA when you want to combine data from multiple datasets into a single CJA connection. However, if you intend to keep the report suites in separate CJA connections but you want to use one set of reports across those those connections and data views, changing the underlying Component ID in CJA provides a way to make reports compatible even if schemas are different. See Component Settings for more information.

Changing the Component ID is a CJA-only function and does not impact data from ADC that is sent to RTCDP.
