---
title: Customer Journey Analytics and Data Governance
description: Describes how data governance works in Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
TQID: https://experienceleague.adobe.com/MoyMEIxDZoKqztW3A0o2aOM4I-F4i7LOuHD09ahsaQc
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Adobe Customer Journey Analytics and Data Governance

Generally speaking, any data governance-related settings in Customer Journey Analytics are inherited from Adobe Experience Platform.

## Data Governance

The integration between Adobe Customer Journey Analytics and [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html) allows for labeling of sensitive Customer Journey Analytics data and enforcement of privacy policies. 

Privacy labels and policies that were created on datasets consumed by Experience Platform can be surfaced in the Customer Journey Analytics data views workflow. These labels stop or warn users who create metrics and/or dimensions from sensitive fields. 

In addition, when data is exported from Customer Journey Analytics (via reporting, export, API, etc.), warnings or labels are added to notify users that a report contains sensitive information that needs to be treated in a specific way.

This integration allows you to manage compliance more easily. Data stewards in your organization can set policies to restrict usage. As a result, your Customer Journey Analytics users can more confidently use data, knowing that it complies with policies defined by data stewards. 

[Learn more](/help/data-views/data-governance.md)

## Privacy Requests

Adobe handles privacy requests in accordance with applicable local and international laws. 

Because Customer Journey Analytics uses data that is available in Adobe Experience Platform, Adobe offers the [Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html) to submit data access and deletion requests. The requests apply to both the original and rekeyed datasets.

## GDPR

Customer Journey Analytics will not subscribe to the General Data Protection Regulation (GDPR) Central Service directly and will instead inherit all dataset changes made in Experience Platform. Customer Journey Analytics depends on Platform Data Lake to enforce GDPR deletion requests and notify Customer Journey Analytics when requests are complete. All changes to affected batches in Customer Journey Analytics for event datasets are synchronized with Platform data. Profile and lookup datasets affected by GDPR deletion requests are fully re-ingested after each delete request. Deletion requests are typically finished within 7 days of a deletion event in Data Lake.

## CCPA

The California Consumer Privacy Act (CCPA) enhances privacy rights and consumer protection for residents of California, United States. This Act became effective on January 1, 2020.
The CCPA provides new data privacy rights to California residents, such as the right to access and delete their personal data, to know whether their personal data is sold or disclosed (and to whom), and to refuse the sale of their personal data.
In accordance with the CCPA, the Privacy Service supports requests to opt out from the selling of personal data.

>[!MORELIKETHIS]
>
>* [Blog: How to Maintain Effective Governance In Adobe Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4)
