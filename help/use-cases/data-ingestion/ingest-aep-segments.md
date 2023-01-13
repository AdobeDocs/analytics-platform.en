---
title: Ingest AEP audiences into Customer Journey Analytics
description: Explains how to ingest AEP audiences into Customer Journey Analytics for further analysis.
solution: Customer Journey Analytics
feature: Use Cases
exl-id: cb5a4f98-9869-4410-8df2-b2f2c1ee8c57
---
# Ingest AEP audiences into Customer Journey Analytics (CJA)

This use case explores an interim, manual way of bringing Adobe Experience Platform (AEP) audiences into CJA. These audiences might have been created in the AEP Segment Builder, or Adobe Audience Manager, or other tools, and are stored in Real-time Customer Profile (RTCP). The audiences consist of a set of Profile IDs, along with any applicable attributes/events/etc. and we want to bring them into CJA Workspace for analysis.

## Prerequisites

* Access to Adobe Experience Platform (AEP), specifically Real-time Customer Profile.
* Access to create/manage AEP schemas and datasets.
* Access to AEP Query Service (and the ability to write SQL) or a different tool to perform some light transformations.
* Access to Customer Journey Analytics. You need to be a CJA product admin in order to create/modify CJA connections and data views.
* Ability to use the Adobe APIs (Segmentation, optionally others)

## Step 1: Choose audience(s) in Real-time Customer Profile {#audience}

Adobe Experience Platform [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCP) lets you see a holistic view of each individual customer by combining data from multiple channels, including online, offline, CRM, and third party. 

You likely already have audiences in RTCP that may have come from various sources. Pick one or more audiences to ingest into CJA.

## Step 2: Create a Profile Union dataset for the export

In order to export the audience to a dataset that can eventually be added to a connection in CJA, you need to create a dataset whose schema is a Profile [Union schema](https://experienceleague.adobe.com/docs/experience-platform/profile/union-schemas/union-schema.html?lang=en#understanding-union-schemas).

Union schemas are composed of multiple schemas that share the same class and have been enabled for Profile. The union schema enables you to see an amalgamation of all of the fields contained within schemas sharing the same class. Real-time Customer Profile uses the union schema to create a holistic view of each individual customer.

## Step 3: Export an audience to the Profile Union dataset via API call {#export}

Before you can bring an audience into CJA, you need to export it to an AEP dataset. This can only be done using the Segmentation API, and specifically the [Export Jobs API Endpoint](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/export-jobs.html?lang=en). 

You can create an export job using the audience ID of your choice, and put the results in the Profile Union AEP dataset you created in Step 2. Although you can export various attributes/events for the audience, you only need to export the specific profile ID field that matches the person ID field used in the CJA connection you will be leveraging (see below in Step 5).

## Step 4: Edit the export output 

The results of the export job need to be transformed into a separate Profile dataset in order to be ingested into CJA.  This transformation can be done with [AEP Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en), or another transformation tool of your choice. We only need the Profile ID (that will match the Person ID in CJA) and one or more audience ID(s) to do the reporting in CJA.

The standard export job, however, contains more data and so we need to edit this output to remove extraneous data, as well as move some things around.  Also, you need to create a schema/dataset first before you add the transformed data to it.

Here is an example of the export output in the Profile union dataset, **before** any editing:

![Unedited output](../assets/export-unedited.png)

Note the following:

* The audience ID is contained under `segmentmembership.ups.xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.status`.
* The status has to be "realized", or "entered", but not "exited".

This is the format of the Profile dataset that you can send into CJA.

![Edited output](../assets/export-edited.png)

Here are the data elements that need to be present:

* `_aresprodvalidation` string field: Refers to your Organization ID. Yours will be different.
* `personID` string field: This is the standard XDM schema field on Profile datasets to identity the person. Use the Profile ID from the export.
* `audienceMembershipId` string field: The audience ID from the export.  NOTE: This field can be named whatever you want (from your own schema).
* Add a friendly name for the audience (`audienceMembershipIdName`), such as

   ![Friendly audience name](../assets/audience-name.png)
   
* Add other audience metadata if you desire.

## Step 5: Add this Profile dataset to an existing connection in CJA

You could [create a new connection](/help/connections/create-connection.md), but most customers will want to add the Profile dataset to an existing connection. The audience IDs "enrich" the existing data in CJA.

## Step 6: Modify existing (or create new) CJA data view

Add `audienceMembershipId`, `audienceMembershipIdName` and `personID` to the data view.

## Step 7: Report in Workspace

You can now report on `audienceMembershipId`, `audienceMembershipIdName` and `personID` in Workspace.

## Additional notes

* You should  perform this process on a regular cadence, so that audience data is constantly refreshed within CJA.
* You can import multiple audiences within a single CJA connection. This adds additional complexity to the process, but it is possible. For this to work, you need to make a few modifications to the above process:
   1. Perform this process for each desired audience in your audience collection within RTCP.
   1. CJA supports arrays/object arrays in profile datasets. Using an [array of objects](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/object-arrays.html?lang=en) for the audienceMembershipId or audienceMembershipIdName is the best option. 
   1. In your data view, create a new dimension using the Substring transformation on the `audienceMembershipId` field to convert the comma-separated values string to an array. NOTE: there is currently a limit of 10 values in the array.
   1. You can now report on this new dimension `audienceMembershipIds` within CJA Workspace.
