---
description: Explains what factors influence the consistency of metrics and audience membership counts between Real-time Customer Data Platform (Real-time CDP) and Customer Journey Analytics.
title: Consistency of metrics and audience membership
role: Admin
feature: Basics
exl-id: 13d972bc-3d32-414e-a67d-845845381c3e
---

# Consistency of metrics and audience membership

In real-world scenarios, consistency of metrics and audience membership counts across Real-time Customer Data Platform (Real-time CDP) and Customer Journey Analytics cannot be guaranteed. This document explains why. 

When comparing audience membership counts between Real-time CDP and Customer Journey Analytics, it is important to keep in mind the different purposes of these two tools. Real-time CDP uses customer profile data to target digital experiences to individual consumers, while Customer Journey Analytics is designed to help users understand patterns in key business metrics and segments. While audience publishing from Customer Journey Analytics to Real-time CDP allows a user of these tools to easily and natively "activate" an insight, taking advantage of learnings obtained in Customer Journey Analytics, these tools nevertheless serve fundamentally different purposes. 

## Differences in identity configurations

Real-time CDP and Customer Journey Analytics do not share the same definition of a person today. Real-time CDP relies entirely on the information in the [Identity Graph](https://experienceleague.adobe.com/docs/platform-learn/tutorials/identities/understanding-identity-and-identity-graphs.html) to build a merged profile.

Customer Journey Analytics can be configured to use [Stitching](../stitching/overview.md) which extracts identifiers from datasets in the data lake and applies custom logic to link them together.

In the future, Customer Journey Analytics will be able to use Identity Graph.

## Differences in dataset configuration 

You can choose to put some data in Real-time CDP and some in Customer Journey Analytics; often, customers choose to put more historical data in Customer Journey Analytics than is relevant for Real-time CDP. Other datasets might be more relevant for Real-time CDP than for Customer Journey Analytics.

## Differences in processing configuration

Customer Journey Analytics allows for extensive data modification at query time, such as combining fields, splitting fields apart, and other manipulations like includes/excludes, substrings, value de-duplication, sessionization, and row-level filtering.

Real-time CDP offers a different set of data manipulation tools. It applies [merge policies](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html) to determine which data will be prioritized and what data will be combined to create a unified view of a person. 

## Differences in TTL (Time to Live) and data ingestion

Even if the datasets in Real-time CDP and Customer Journey Analytics are the same, Real-time CDP may only keep a very limited window of history. By contrast, Customer Journey Analytics likely has years' worth of data. In addition:

* Customer Journey Analytics and Real-time CDP customers can set custom retention windows for data, independent of each other. 

* Real-time CDP and Customer Journey Analytics have different logic for ingesting data. Customer Journey Analytics ignores records without a person ID or timestamp and has strict limits to the number of records a single profile/person may have.

* Real-time CDP customers get 7 days of access to data in the lake, primarily to facilitate data onboarding into profile and for ad-hoc querying.

* There are no TTLs for the data in the lake for Customer Journey Analytics customers. Customer Journey Analytics users however can themselves set a custom retention window in Customer Journey Analytics when creating a connection.

* Profile Store in Real-time CDP allows for customer-configurable TTLs. Customers can change this TTL to whatever they need to stay within their license entitlements.

## Differences in data ingestion latency

Customer Journey Analytics does not yet have the real-time capabilities of Real-time CDP and as a result, Customer Journey Analytics reporting includes some latency before data is available for reporting or audience creation. Real-time CDP processes data through different systems that have different latency.
