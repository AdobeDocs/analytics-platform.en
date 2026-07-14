---
title: Customer Journey Analytics and Data Governance
description: Describes how data governance works in Customer Journey Analytics.
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
autotag-review: '2026-05-19T09:18:17.400Z'
TQID: 'https://experienceleague.adobe.com/oDdNRwjtEU2vmeDvQ3DcM8w6XKQTBoTaXAIhmgjSoBk'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
    internal-label: Privacy
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
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

## Consent Reporting and Filtering

Customer Journey Analytics can use the consent policy membership data in your Experience Platform Profile datasets to report on visitor consent and, optionally, exclude non-consenting visitors before their data is ingested. Consent reporting makes consent policies available as components in Analysis Workspace, and consent filtering excludes non-consenting visitors at ingest time based on the marketing actions that you configure.

[Learn more](/help/connections/consent-reporting-filtering/consent-overview.md)

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
