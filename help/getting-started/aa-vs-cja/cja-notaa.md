---
title: CJA features not available in AA
description: Customer Journey Analytics features not available in Adobe Analytics.
solution: Customer Journey Analytics
feature: CJA Basics
---
# Customer Journey Analytics features not available in Adobe Analytics

The following table lists wich features are available in Customer Journey Analytics (CJA), and which are not supported or available in Adobe Analytics (AA).


| Feature | More Details |
| --- | --- |
| Any kind of data | CJA is combined with Experience Platform's ability to hold all kinds of data schemas and types. Using [Experience Data Model (XDM)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html), data can be uniformly represented and organized, ready for combination and exploration. AA is predominantly focused on web and mobile analytics data with some capabilities to [import data](https://experienceleague.adobe.com/docs/analytics/import/home.html). |
| PII data | The data schemas and types CJA can hold and will most likely include **PII data**. CJA stores its data as part of an individual customer based and provisioned Adobe Experience Platform infrastructure. This is fundamentally different to AA which should only collect **non-PII data**, which is stored collectively in Adobe's global regional data centers. |
| Unlimited Customer Dimensions | CJA dimensions are unlimited; values can be numeric, text, objects, lists, or mixtures of all. Dimensions can be nested or hierarchical.AA supports up to a maximum of 75 props and 250 eVars. This removes the current measurement limitations using dimensions and events. |
| Unlimited cardinality / unique values | CJA supports unlimited unique values or dimension items that can be reported on within a single dimension. AA is limited to 500K unique values. This removes reporting and analysis limitations currently existing with large scale AA implementation. |
| Data Views | Data Views in CJA allow you to further interpret data from a connection. You can alter or remove data without re-implementation; use substrings to manipulate dimensions; create metrics from any value; filter sub-events. And this can all be done non-destructively. Adobe Analytivs provides limited capabilities through virtual report suites and sessionization. |
| Experimentation Analysis | CJA can evaluate the lift and confidence of any experiment from any data source defined as part of a connection. This allows you to understand cause and effect relationships between customer interactions spanning any channel. AA is limited to experimentation analytics through the Analytics for Target (A4) integration. |
| Cross-Device Analytics | CJA supports the seamless combination of device specific data sets from unauthenticated and authenticated sessions. You can also backfill historical data to known devices. In AA this is limited to a single report suite and the use of a device graph. |
| SQL Access | Using the Data Distiller option, CJA can remove the limitations of data collected or Adobe's backend processing. You can modify your data with SQL, create new values and datasets unique to your business and continue to explore. AA does not support any kind of SQL access to its data. |
| HIPAA & Data Residency global compliance | CJA is compliant for HIPAA and global data residency. As a result, it has the ability to ingest and analyze a broad range of personal data, including sensitive data, with confidence. AA is not HIPAA or global Data Residency compliant. |



 


