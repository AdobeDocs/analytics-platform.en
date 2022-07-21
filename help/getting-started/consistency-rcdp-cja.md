---
description: Explains what factors influence the consistency of metrics between Real-time Customer Data Platform (Real-time CDP) and CJA.
title: Consistency of metrics between Real-time CDP and CJA
role: Admin
feature: CJA Basics
---

# Consistency of metrics between Real-time CDP and CJA

In real-world scenarios, consistency of metrics across Real-time Customer Data Platform (Real-time CDP) and Customer Journey Analytics (CJA) cannot be guaranteed. This document explains why.

## CJA does not yet use Identity Graph

CDP and CJA do not share the same definition of a person today. CJA does not yet use [Identity Graph](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) to inform its definition of a person. Real-time CDP relies entirely on the information in the Identity Graph to build a merged profile.

CJA uses a method called [Field-Based Stitching](/help/connections/cca/overview.md) which extracts identifiers from datasets in the data lake and applies custom logic to link them together. In the intermediate future, CJA is expected to start making use of [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=en) exports to the data lake, allowing for a shared notion of identity across CDP and CJA.

>[!IMPORTANT]
>
>Making Adobe Experience Platform Identity Service the identity source of truth for all AEP (Adobe Experience Platform) applications does not automatically make metrics consistent across applications. Read on to learn why.

## Application data flexibility

Experience Platform does not apply strict enforcement to keep the data between Real-time Customer Profile and Data Lake the same. Some use cases work off data in [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/profile/profile-overview.html?lang=en) (activation), while others work off the [data lake](https://business.adobe.com/blog/basics/data-lake) (reporting and query service).

Real-time CDP customers typically do not have 100% of the data in the Adobe Experience Platform data lake going into Profile. This is by design - customers should specifically enable data in the lake for Profile. CJA allows data analysts to freely select what data they want to bring in for analysis from the data lake, independent of what is enabled for Real-time CDP.

## Application-specific modifiers

CJA allows for extensive data modification at query time, such as combining fields, splitting fields apart, and other manipulations like currency conversions, value de-duplication, sessionization, and row-level filtering. These capabilities are not available to CDP.

Similarly, Real-time CDP applies [merge policies](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en) to determine which data will be prioritized and what data will be combined to create a unified view of a person. These configurations sit firmly within each application’s logic and are not shared.

## Read-time vs write-time behavior

Real-time CDP requires point-in-time profile stitching using the latest ID graph.

* Real-time CDP is designed to assemble profile information in real time for activation.

* It can accommodate in real time all changes to the set identifiers for a given user.

* The lookback window is controlled by the segment definition.

CJA requires data to be stitched at write-time using ID Graph exports.

* CJA applies complex pre-processing steps like indexing, sharding, and grouping before the data is made ready for analysis.

* The person identifier for a given user is a critical input for the pre-processing stages; changing the person identifier afterwards has significant reprocessing cost.

* The lookback window is controlled at the application level.

## Differences in TTL (Time to Live) and data ingestion

Even if the datasets in Real-time CDP and CJA are the same, Real-time CDP may only keep a very limited window of history. By contrast, CJA likely has years' worth of data. In addition:

* CJA and Real-time CDP customers can set custom retention windows for data, independent of each other. 

* Real-time CDP and CJA have different logic for ingesting data. CJA ignores records without a person ID or timestamp and has strict limits to the number of records a single profile/person may have.

* Real-time CDP customers get 7 days of access to data in the lake, primarily to facilitate data onboarding into profile and for ad-hoc querying.

* There are no TTLs for the data in the lake for CJA customers. CJA users however can themselves set a custom retention window in CJA when creating a connection.

* Profile Store in Real-time CDP allows for customer-configurable TTLs. Customers can change this TTL to whatever they need to stay within their license entitlements.

## Differences in GDPR (General Data Protection Regulation) processing

Data processing logic for GDPR and data hygiene across Real-time CDP and data lake is quite different. We are working towards a single approach.

## Differences in data ingestion latency

CJA reporting includes some latency before data is available for reporting or audience creation. Real-time CDP processes data through different systems that have different latency.