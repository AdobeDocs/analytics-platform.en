---
title: Labels and policies
description: Learn how data labels and policies defined in AEP affect data views and reporting in CJA.
exl-id: 1de5070f-a91c-4fe6-addb-a89d59a280b7
---
# Labels and policies

>[!NOTE]
>
>This functionality is currently in [limited testing](/help/release-notes/releases.md).

When you create a dataset in Experience Platform, you can create [data usage labels](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/reference.html?lang=en) for some or all of the elements in the dataset. Until now, these labels were not exposed in CJA. With this release, you can view these labels in CJA. Of special interest to CJA are these labels:

* The `C8` label - **[!UICONTROL No measurement]**. This label signifies that data cannot be used for analytics on your organization’s websites or apps.

* The `C12` label - **[!UICONTROL No General Data Export]**. Schema fields labeled this way cannot be exported or downloaded from CJA (via reporting, export, API, etc.)

Labeling in itself does not mean that these data usage labels are enforced. That’s what policies are used for. You create your policies via the [Policy Service API](https://experienceleague.adobe.com/docs/experience-platform/data-governance/api/overview.html?lang=en) in Experience Platform.

Two Adobe-defined policies are surfaced in CJA and affect reporting and download/sharing:

* **[!UICONTROL Enforce Analytics]** policy
* **[!UICONTROL Enforce Download]** policy

## View data labels in CJA data views

Data labels that were created in Experience Platform are shown in three locations in the data views user interface:

| Location | Description |
| --- | --- |
| Info button on a schema field | Clicking this button indicates which Data Usage Labels currently apply to a field:<p>![](assets/data-label-left.png) |
| Right rail under [Component settings](/help/data-views/component-settings/overview.md) | Any Data Usage Labels are listed here:<p>![](assets/data-label-right.png) |
| Add Data Labels as a column | You can add Data Labels as a column to the Included Components columns in data views. Just click the column selector icon and select Data Usage Labels:<p>![](assets/data-label-column.png) |

{style="table-layout:auto"}

## Filter on Data Governance labels in data views

In the data views editor, click the Filter icon in the left trail and filter the data views components by data governance label/s:

![](assets/filter-labels.png)

Click **[!UICONTROL Apply]** to see which components have labels attached to them.

## Filter on Data Governance policies in data views

You can check to see if a policy is turned on that blocks the use of certain CJA data view elements for analytics or export purposed. 

Again, click the Filter icon in the left rail and under Data Governance, click Policies:

![](assets/filter-policies.png)

Click **[!UICONTROL Apply]** to see which policies that are enabled _for this data view?_

## How the [!UICONTROL Enforce Analytics] policy affects Workspace projects

If this policy is turned on, those schema fields that have certain data labels (such as C8) associated with them cannot be used for analytics purposes within CJA Workspace. 

For reporting, this means that 

* You cannot add these fields to data views, and they are greyed out in the left rail [!UICONTROL Schema fields] list. 
* You cannot save a data view that has blocked fields in it.

If you try to perform Workspace analysis on data views that contain items prohibited for analytics, you will get a notice similar to this:

![](assets/policy-enforce.png)

On individual components, the message would be similar to this:

![](assets/policy-enforce2.png)

## How the [!UICONTROL Enforce Download] policy affects Workspace projects

If this policy is turned on, any export or download (such as emailing or sharing pdfs) of Workspace projects will hash the sensitive fields. You can still do analysis on these fields in Workspace, but if you try to email or otherwise share a project, the blocked fields will appear as hashed items in the .pdf file.

Add a screenshot here.

## View labels in Report Builder

See _this section_ for more information. (link to Christine's doc)
