---
title: Labels And Policies
description: Learn how data labels and policies defined in Adobe Experience Platform affect data views and reporting in Customer Journey Analytics.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
feature: Data Views, Data Governance
role: Admin
hold: true
autotag-review: '2026-05-19T08:59:31.818Z'
TQID: 'https://experienceleague.adobe.com/SoIHLRSx90B4j8EkHWBVt3rVtt-968TN8ocWU2zuYN4'
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
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
    internal-label: Governance
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Labels, policies, and marketing actions

When you create a dataset in Experience Platform, you can create [data usage labels](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/labels/reference) for some or all elements in the dataset. You can view these labels and policies in Customer Journey Analytics. 

The following labels and marketing actions are of special interest to Customer Journey Analytics:


| Label | Marketing action | Definition |
|---------|----------|---------|
| `C2` | [!UICONTROL Export to third parties] | The label and associated marketing action signify that data cannot be exported to a third party, if the corresponding DULE policy is enabled. |
| `C3` | [!UICONTROL Combine with directly identifiable data] | The label and associated marketing action signify that data cannot be combined or otherwise used with directly identifiable information, if the corresponding DULE policy is enabled. |
| `C8` | [!UICONTROL Analytics] | The label and associated marketing action signify that data cannot be used for analytics on your organization's websites or apps, if the corresponding DULE policy is enabled. |
| `C9` | [!UICONTROL Data Science] | The label and associated marketing action signify that data cannot be used in data science workflows, if the corresponding DULE policy is enabled. |
| `C12` | [!UICONTROL Data Export] | The label and associated marketing action signify that schema fields labeled this way cannot be exported or downloaded from Customer Journey Analytics (via reporting, export, API, and so forth), if the corresponding DULE policy is enabled. |

>[!NOTE]
>
>Data usage labels are not automatically propagated to stitched datasets. They can, however, be added manually.

Labeling in itself does not mean that these data usage labels are enforced. That's what policies are used for. You can create your policies using the [Experience Platform UI](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/policies/user-guide) or via the [Policy Service API](https://experienceleague.adobe.com/en/docs/experience-platform/data-governance/api/overview) in Experience Platform.

Five Adobe-defined policies are available in Experience Platform that can surface in Customer Journey Analytics and affect reporting and data export:


| Policy | Label | 
|---------|----------|
| [!UICONTROL Restrict third-party data export] | `C2` |
| [!UICONTROL Restrict directly identifiable data combination] | `C3` |
| [!UICONTROL Restrict usage analytics and user based measurement] | `C8` |
| [!UICONTROL Restrict data science] | `C9` |
| [!UICONTROL Restrict data export] | `C12` |


## View data labels in Customer Journey Analytics data views

Data labels that you or others created in Experience Platform are shown in three locations in the data views user interface:

| Location | Description |
| --- | --- |
| Info button on a schema field | Clicking this button indicates which [!UICONTROL Data Usage Labels] currently apply to a field:<p>![](assets/data-label-left.png) |
| Right rail under [Component settings](/help/data-views/component-settings/overview.md) | Any [!UICONTROL Data Usage Labels] are listed here:<p>![](assets/data-label-right.png) |
| Add Data Labels as a column | You can add [!UICONTROL Data Usage Labels] as a column to the [!UICONTROL Included Components] columns in data views. Just select the column selector icon and select **[!UICONTROL Data Usage Labels]**:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filter on Data Governance labels in data views

In the data views editor, select the [!UICONTROL filter] icon in the left trail and filter the data views components by **[!UICONTROL Data Governance]** and type of **[!UICONTROL Label]**:

![](assets/filter-labels.png)

Click **[!UICONTROL Apply]** to see which components have labels attached to them.

## Filter on Data Governance policies in data views

You can check to see if a policy (for example, a policy you created, named **[!UICONTROL Enforce Analytics]**) is turned on. And whether that policy blocks the use of certain Customer Journey Analytics data view elements for analytics or data export. 

Again, select the [!UICONTROL filter] icon in the left rail and under **[!UICONTROL Data Governance]**, select **[!UICONTROL Policies]**:

![Filter included components by list showing Restrict usage analytics and user based measurement selected](assets/filter-policies.png)

Click **[!UICONTROL Apply]** to see which policies are enabled.

## How enabled policies affect data views

If one or more policies are turned on with C1, C2, C3, C8, C9, or C12 labels, those schema components that have certain data labels applied cannot be added to data views. 

These components are grayed out in the left rail [!UICONTROL Schema fields] list:

![Greyed out components and the Policies message indicating policies have been applied to this field restricting use of the data](assets/component-greyed.png)

You also cannot save a data view that has blocked fields in it.

Be cautious to try to apply access and data governance labels (through policies) on fields or field groups in Experience Platform, for which you already have components defined in your data view. You might see this dialog.

![Violation](assets/violation.png)

You first need to resolve the violation (for example remove the components from the data view).


>[!MORELIKETHIS]
>
>[Download sensitive data](/help/analysis-workspace/export/download-send.md)

>[!MORELIKETHIS]
>
>[What are restricted labels in Report Builder?](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-reportbuilder/restricted-labels)


