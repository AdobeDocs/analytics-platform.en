---
title: Restricted Labels In Report Builder
description: Learn about restricted labels in Report Builder.
role: User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
TQID: https://experienceleague.adobe.com/MeHO7A9KWAjG8TyiOn9taPbtPhD47JGl88KSCoQwdMI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: f2ef16dc-055a-4bb7-baa5-7039653f3966
    internal-label: Report Builder
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
    internal-label: Privacy
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
---
# Restricted labels in Report Builder

Generally data governance-related settings in Customer Journey Analytics are inherited from Experience Platform. The integration between Customer Journey Analytics and Experience Platform Data Governance allows for labeling of sensitive Customer Journey Analytics data and enforcement of privacy policies.

Privacy labels and policies that are created on datasets consumed by Experience Platform can be surfaced in the Customer Journey Analytics data views workflow. These labels stop or warn users who create metrics and dimensions from sensitive fields. For information about datasets, see [Datasets overview](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)

In addition, when data is exported from Customer Journey Analytics (via reporting, export, API, etc.), warnings or labels are added to notify users that a report contains sensitive information that needs to be treated in a specific way.

This integration allows you to manage compliance. Data stewards in your organization can set policies to restrict usage. As a result, your Customer Journey Analytics users can more confidently use data, knowing that it complies with policies defined by data stewards.

For more information, see [Customer Journey Analytics and Data Governance](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-privacy/privacy-overview)

## View restricted data

Two Adobe-defined policies are surfaced in Customer Journey Analytics that affect reporting, downloading, and sharing:

* Enforce Analytics policy
* Enforce Download policy

Components subject to these policies are grayed out and do have an ![InfoOutline](/help/assets/icons/InfoOutline.svg) icon. When you hover over the info icon, a note is displayed to indicate the following: **[!UICONTROL Policies have been applied to this field prohibiting use of this data]**. 

For more information, see [Labels and policies](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-governance).


![The policy note indicating prohibited use of data.](assets/restricted-label.png){zoomable="yes"}


## Update reports that contain restricted data

In cases where a user created a Report Builder report with data elements that are later restricted, when the report is refreshed, an error message is displayed.

![The error message displayed after data elements are later restricted.](assets/error-restricted-data.png){width="100%" zoomable="yes"}
