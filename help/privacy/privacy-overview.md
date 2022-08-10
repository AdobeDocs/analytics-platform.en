---
title: Customer Journey Analytics and Data Governance
description: Describes how data governance works in Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
---
# Customer Journey Analytics and Data Governance

Generally speaking, any data governance-related settings in Customer Journey Analytics are inherited from Adobe Experience Platform.

## Data Governance

The integration between CJA and [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) allows for labeling of sensitive CJA data and enforcement of privacy policies. 

Privacy labels and policies that were created on datasets consumed by Experience Platform can be surfaced in the CJA data views workflow. These labels stop or warn users who create metrics and/or dimensions from sensitive fields. 

In addition, when data is exported from CJA (via reporting, export, API, etc.), warnings or labels are added to notify users that a report contains sensitive information that needs to be treated in a specific way.

This integration allows you to manage compliance more easily. Data stewards in your organization can set policies to restrict usage. As a result, your CJA users can more confidently use data, knowing that it complies with policies defined by data stewards. 

## GDPR

Customer Journey Analytics will not subscribe to the General Data Protection Regulation (GDPR) Central Service directly and will instead inherit all dataset changes made in Experience Platform. We depend on Platform Data Lake to enforce GDPR deletion requests and notify us when they’ve been completed on Pipeline. We listen to Pipeline and synchronize all changes to affected batches in Customer Journey Analytics for event datasets. Profile and lookup datasets affected by GDPR deletion requests will be completely re-ingested after each delete request. We can guarantee deletion requests are executed within 7 days of a deletion event in Data Lake.

## CCPA

The California Consumer Privacy Act (CCPA) enhances privacy rights and consumer protection for residents of California, United States. This Act became effective on January 1, 2020.
The CCPA provides new data privacy rights to California residents, such as the right to access and delete their personal data, to know whether their personal data is sold or disclosed (and to whom), and to refuse the sale of their personal data.
In anticipation of the CCPA, the Privacy Service will support requests to opt out from the selling of personal data.
