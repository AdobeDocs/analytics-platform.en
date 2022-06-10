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

When creating the source connection dataflow for Report Suite A, select **Unified Schema** for use in the dataflow. Add custom mappings as follows:

| Report Suite A source field | Destination field from Unified Fields field group | 
| --- | --- |
| _experience.analytics.customDimensions.eVars.eVar1 | <path>.Search_term | 
| _experience.analytics.customDimensions.eVars.eVar2 | <path>.Search_term |
  
