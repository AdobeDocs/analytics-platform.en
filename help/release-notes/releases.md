---
description: Explains the continuous feature release strategy for Customer Journey Analytics
title: Customer Journey Analytics feature release strategy
exl-id: aebe709a-4cc7-4197-86e9-b26ab2874375
feature: Release Notes
---
# Customer Journey Analytics feature release strategy

Customer Journey Analytics releases operate on a continuous delivery model which allows for a scalable, phased approach to feature deployment.

## Release strategy

[!UICONTROL Analysis Workspace] uses feature flags (also known as "toggles") to control the visibility of new features, allowing for controlled scale testing prior to full release. This release strategy includes the following phases:

* **Limited Testing**: A phased release begins with testing by internal Adobe users. It is then made available to a small group of customer accounts to ensure that the feature meets customer needs and expectations. 

* **Start of Rollout**: Rollout of a phased release begins with the Limited Testing phase. The release is then scaled from 0% to 100% availability to customers over the course of a couple months. Phased rollout happens at the Experience Cloud Organization level, so all entitled users in an organization receive the same experience.

* **General Availability (GA)**: The feature is available to 100% of entitled Experience Cloud organizations, and feature release is complete.

With each feature release, the timeline from RTP to GA may vary. The goal is to keep releases short, so that within 2 months of release start (RTP), a feature will be GA.

## Feature flags

Feature flags are used to control the visibility of new features during release. Adobe recommends allowing `app.launchdarkly.com` through your organization's firewall for an optimal experience during releases. These flags are removed after a feature is released to everyone. See [Domains used by Customer Journey Analytics](../technotes/domains.md) for more information.

You can view your active feature flags at any time under **Help > About Workspace > Active feature flags**.

## Benefits

Phased releases enable Adobe to better scale the software deployment process and ensure features are fully hardened before General Availability. It also allows features to be released as soon as they are available, rather than adhering to a fixed monthly release window.

## FAQs

| Question | Answer |
| --- | --- |
| Can I request early access to a feature? | No. Early access will not be granted.<br>If you want to test early Analytics concepts, we encourage you to try [Adobe Analytics Labs](https://experienceleague.adobe.com/docs/analytics/analyze/labs.html) to provide feedback on our industry-leading innovations. |
| Does this release strategy affect my access to features? | No. Once a feature has reached GA, you will have access to the feature if it is included in your Analytics package. |
