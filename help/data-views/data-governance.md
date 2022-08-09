---
title: CJA support for Adobe Experience Platform Data Governance
description: 
---

# CJA support for Adobe Experience Platform Data Governance

The integration between CJA and [Adobe Experience Platform Data Governance](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=en) allows for labeling of sensitive CJA data and enforcement of privacy policies. 

Privacy labels and policies that were created on datasets consumed by Experience Platform can be surfaced in the CJA data views workflow. These labels stop or warn users who create metrics and/or dimensions from sensitive fields. 

In addition, when data is exported from CJA (via reporting, export, API, etc.), warnings or labels are added to notify users that a report contains sensitive information that needs to be treated in a specific way.

This integration allows you to manage compliance more easily. Data stewards in your organization can set policies to restrict usage. As a result, your CJA users can more confidently use data, knowing that it complies with policies defined by data stewards. 

## Labeling and policies in Adobe Experience Platform

When you create a dataset in Experience Platform, you can create [data usage labels](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) for some or all of the elements in the dataset. Until now, these labels were not exposed in CJA. With this release, you can view these labels in CJA. Of special interest to CJA is the C8 label, which says “Data cannot be used for measurement of your organization’s websites or apps”.

Labeling in itself does not mean that these data usage labels are enforced. That’s what policies are used for. You create your policies via the [Policy Service API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) in Experience Platform.

Policies have two components: the data label and a marketing action which data consumers can take within the context of restricted data usage policies. In the context of CJA, two Adobe-defined [marketing actions](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=en#appendix ) are important:

* Analytics – using data for analytics purposes, such as measuring, analyzing, and reporting on consumer usage of your organization’s sites or apps.

* Exporting this data out of the Adobe environment, such as exporting data to a third party.

You tie labels and marketing actions together with a policy and then turn on the policy. The policy takes the label and the marketing action and says: enforce this restriction. Two Adobe-defined policies are surfaced in CJA:

* Analytics policy
* Download policy

## View data labels in CJA data views

Data labels that were created in Experience Platform display in three locations in the data views user interface:

| Location | Description |
| --- | --- |
| Info button on a schema field | Clicking this button indicates which Data Usage Labels currently apply to a field:<p>![](assets/data-label-left.png) |
| Right rail under [Component settings](/help/data-views/component-settings/overview.md) | Any Data Usage Labels are listed here:<p>![](assets/data-label-right.png) |
| Add Data Labels as a column | You can add Data Labels as a column to the Included Components columns in data views. Just click the column selector icon and select Data Usage Labels:<p>![](assets/data-label-column.png) |

### Filter on Data Governance labels in CJA

In the data views editor, click the Filter icon in the left trail and filter the data views components by data governance labels:

![](assets/filter-labels.png)

### Filter on Data Governance policies in CJA

You can check to see if a policy is turned on that blocks the use of certain CJA data view elements for analytics or export purposed. 

Again, click the Filter icon in the left rail and under Data Governance, click Policies:

![](assets/filter-policies.png)

If the policy is turned on, those schema fields that have certain data labels (such as C8) associated with them, cannot be used for analytics or download (such as emailing or sharing pdfs) purposes within CJA Workspace. 

Note that 

* You are not allowed to add them to data views. These fields will be greyed out in the left rail Schema fields list. 
* You cannot save a data view that has blocked fields in it.


