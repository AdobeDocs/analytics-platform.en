---
title: CJA privacy overview
seo-title: Privacy settings in [!UICONTROL Customer Journey Analytics] (CJA).
description: Describes how privacy settings work in CJA.
seo-description: Describes how to configure privacy settings in [!UICONTROL Customer Journey Analytics].
---

# CJA privacy overview

Intro sentence here.

## GDPR

* CJA will not subscribe to the GDPR Central Service directly and will instead inherit all dataset changes made in Data Lake (our source of truth).
* We will depend on Platform Data Lake to enforce GDPR deletion requests and notify us when they’ve been completed on Pipeline.
* We listen to Pipeline and sync all changes to affected batches in CJA for event datasets.
* Profile and lookup datasets affected by GDPR deletion requests will be completely re-ingested after each delete request.
* We can guarantee deletion requests are executed within 7 days of a deletion event in Data Lake.

## CCPA

More detail here.
