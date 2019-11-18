---
title: Customer Journey Analytics privacy overview
description: Describes how privacy settings work in Customer Journey Analytics.
---

# Customer Journey Analytics privacy overview

Generally speaking, any privacy-related settings in Customer Journey Analytics are inherited from Adobe Experience Platform.

## GDPR

Customer Journey Analytics will not subscribe to the GDPR Central Service directly and will instead inherit all dataset changes made in Experience Platform. We depend on Platform Data Lake to enforce GDPR deletion requests and notify us when they’ve been completed on Pipeline. We listen to Pipeline and synchronize all changes to affected batches in Customer Journey Analytics for event datasets. Profile and lookup datasets affected by GDPR deletion requests will be completely re-ingested after each delete request. We can guarantee deletion requests are executed within 7 days of a deletion event in Data Lake.

## CCPA

The California Consumer Privacy Act (CCPA) enhances privacy rights and consumer protection for residents of California, United States. This Act is set to become effective on January 1, 2020.
The CCPA provides new data privacy rights to California residents, such as the right to access and delete their personal data, to know whether their personal data is sold or disclosed (and to whom), and to refuse the sale of their personal data.
In anticipation of the CCPA, the Privacy Service will support requests to opt out from the selling of personal data. 
