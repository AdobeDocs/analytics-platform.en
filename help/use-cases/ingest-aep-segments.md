---
title: Ingest AEP audiences into Customer Journey Analytics
description: Explains how to ingest AEP audiences into Customer Journey Analytics for further analysis.
solution: Customer Journey Analytics
feature: Use Cases
---

# Ingest AEP audiences into Customer Journey Analytics (CJA)

>[!NOTE]
>
>This topic is under construction.


(Brandon, fyi,  'Unified Profile' is an obsolete term for 'Real-time Customer Profile' - according to the AEP doc manager. You won't find any doc on UP in the AEP doc set.) 

This use case explores an interim, manual way of bringing Adobe Experience Platform (AEP) audiences into CJA. These audiences might have been created in the AEP Segment Builder, or Adobe Audience Manager, or other tools, and are stored in Real-time Customer Profile (RTCP). The audiences consist of lists of Person IDs, Profile IDs, etc. and we want to bring them into CJA Workspace for analysis.

## Prerequisites

* Access to Adobe Experience Platform (AEP), specifically Real-time Customer Profile.
* Access to Customer Journey Analytics
* Ability to write custom code?
* What else.

## Step 1: Choose audience(s) in Real-time Customer Profile {#audience}

Adobe Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP) lets you see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. You likely already have audiences in RTCP that may have come from various sources. Pick one or more audiences.

## Step 2: Create a Profile Union dataset for the export

In order to export the audience to a dataset that can then make a connection to CJA, you need to create a dataset whose schema is a Profile [Union schema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).
Union schemas are composed of multiple schemas that share the same class and have been enabled for Profile. The union schema enables you to see an amalgamation of all of the fields contained within schemas sharing the same class. Real-time Customer Profile uses the union schema to create a holistic view of each individual customer.

## Step 3: Export an audience to a dataset via API call {#export}

Before you can bring an audience into CJA, you need to export it to a dataset in AEP. This can only be done using the Segmentation API, and specifically the [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). You can create an export job and put the results in the Profile Union AEP dataset you created in Step 2.

## Step 4: Edit the export output 

When creating the export job for an audience, we only need the the Person ID and the Audience ID to do the reporting in CJA. The standard export job, however, contains more data and so we need to edit this output to remove extraneous data.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](assets/export-unedited.png)

Note the following:

* The audience ID is contained under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be "realized", or "entered", but not "exited". Replace "exited" with "blank".

This is the format of the Profile dataset that you can send into CJA.

![Edited output](assets/export-edited.png)

Here are the data elements that need to be present:

* `_aresprodvalidation`: Refers to your Organization ID. Yours will be different.
* `personID`: In this case, a friendly name
* `audienceMembershipIdList` string field: The audience ID
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Friendly audience name](assets/audience-name)

## Step 5: Create a connection in CJA to this Profile dataset

[Create a connection](/help/connections/create-connection.md)

## Step 6: Create a dataview

Add `audienceMembershipIdName` and `personID` to the dataview.

## Step 7: Report in Workspace

You can now report on `audienceMembershipIdName` and `personID` in Workspace.
Screenshot would be great.

To do:

write up more steps for when you are dealing with people who are members of multiple audiences.




