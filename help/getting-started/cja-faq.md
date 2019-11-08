---
title: Customer Journey Analytics FAQ
description: Customer Journey Analytics - Frequently Asked Questions.
---

# Frequently asked questions

|Question|Answer|
|---|---|
|Do you need Device Graph or Device Coop for CJA?|No, Private Device Graph or Device Coop are not required for Customer Journey Analytics. In fact, they are not yet supported.|
|Do you need Experience Cloud ID (ECID) for CJA?|No, Customer Journey Analytics supports any ID in a dataset, whether ECID, or any other ID you choose.|
|Can Customer Journey Analytics "stitch" across devices or across datasets?|No. CJA is a "bring-your-own-ID" analytics system. Plans for a good stitching approach are in the works.|
|If I am an existing [!DNL Data Workbench] customer, can I move to Customer Journey Analytics right now?|It depends. If you rely heavily on the Unified Customer Process (UCP), you will want to wait until we have stitching implemented. If you already have hight customer authentication rates, or if you want all your data in one place, or would like to get rid of eVars, CJA might be a good fit.|
|Can I share segments from CJA to AEP or other solutions?|Not yet. We’re looking at new, innovative ways to share segments from CJA to AEP in the future that don’t have such a long delay. That said, you can share the output of Query Services to Unified Profile as a potential workaround.|
|How do you connect online data to offline data in CJA?|Customer Journey Analytics is a "bring your own ID" analytics system. As long as the person ID matches between datasets, CJA can connect segments, attribution, flow, fallout, etc. across datasets.|
|How does CJA handle `Uniques Exceeded` limitations?|Customer Journey Analytics has no unique value limitations, so no need to worry about them!|
|How do customers bring their offline data into CJA?|Customers must first bring any data to AEP before they can use it with Customer Journey Analytics. The Platform data onboarding team can help provide recommendations or consulting for customers if needed.|
|How do customers get Analytics data into CJA?|Analytics data can be connected to AEP through the Analytics Data Connector. Most Analytics fields are brought over in XDM format, but other fields are not yet available (like Marketing Channels dimensions).|
|What if you need to ETL your data prior to CJA?|Today, you need to work with an ETL partner (Unifi or Informatica) if you need to transform your data before putting it into AEP. If you need ETL after the data’s already been ingested, AEP Query Services provides some limited options.|
|Where are all my session and variable persistence settings now?|Customer Journey Analytics applies all of these settings at report time, and these settings now live in Data Views. Changes to these settings are now retroactive, and you can have multiple versions by using multiple Data Views!|
|What happens to our existing segments/calculated metrics?|Customer Journey Analytics no longer uses eVars, props, or events and instead uses any AEP schema. This means none of the existing segments or calc metrics are compatible with CJA.|
|What does this mean for our traditional Adobe Analytics product?|Customer Journey Analytics is our next generation analytics product. Evolving from our current products to CJA will take years and a lot of coordination together. This release is one big step of many in this direction.|
|Is stitching from anonymous behavior to authenticated behavior supported?|No, not yet.|
|Is it necessary to bring PII data to establish connections between the data?|No, you can use any ID, including a hash of a customer ID, which is not PII.|
|What happened to my old eVar setting?|eVars, props, and events in the traditional Adobe Analytics sense no longer exist in CJA. You have unlimited schema elements (dimensions, metrics, list fields). So all of the attribution settings you used to apply during the data collection process are now applied at query time.|
|How long does it take to assemble dataset elements into a data view?| A few hours to get started, and a few days to backfill the last 13 months of data.|

 