---
title: Map Analytics Data From Multiple IMS Organizations
description: Learn how you can request to map data from report suites from multiple source IMS organizations to report suites and ultimately datasets in a destination IMS organization.
role: Admin
solution: Customer Journey Analytics
feature: Adobe Analytics Integration,Administration
exl-id: c109742b-c1c5-45b3-971f-f8dcf814ec37
---
# Cross-IMS data mapping

This article outlines how to map data from reports suites in multiple IMS organisations to report suites, and ultimately datasets, in one IMS organization.

The Analytics source connector ingests data from Adobe Analytics report suites within a single organization by default. *Cross-IMS data mapping* is a feature to map Analytics data from multiple IMS organizations and provides a solution for this limitation. The process to enable this feature is outlined in this article.


## Scenario

You are provisioned with multiple IMS organizations and do have Analytics data in multiple report suites across these IMS organizations. This setup could be the results of:

* acquisitions or mergers
* organizational structure requirements
* regional deployment constraints

Out of the box, you are not able to report on the combination of data from multiple report suites across multiple IMS organizations in Customer Journey Analytics. The reason for this limitation is that data ingestion from Adobe Analytics into Experience Platform through the Analytics source connector supports only the ingestion of data owned by a single IMS organization. The IMS organization for which you are provisioned and which you use to log in to Adobe Analytics, Experience Platform and Customer Journey Analytics.

With the *Cross-IMS data mapping* feature, you can request Adobe to map data. The feature uses the Analytics source connector to map data from report suites that reside across multiple *source* IMS organizations to report suites (and ultimately datasets) that are part of one *destination* IMS organization. For example:

| Illustration | Explanation  |
|---|---|
| ![Map data across multiple IMS organizations](/help/getting-started/assets/map-data-across-ims-orgs.svg) | This mapping allows you to report on report suites that exist in IMS organization 1, IMS organization 2, and IMS organization 3 from one connection in Customer Journey Analytics that is provisioned within IMS organization 3. |

{style="table-layout:fixed"}

## How to use

To configure and enable the *Cross-IMS data mapping* feature, you have to request the mapping through your Adobe account manager. To do so:

1. As destination IMS organization administrator, request approval emails from all source IMS organization administrator for which you want to map report suites. You can use the following text as a template for the email to request approval from the source IMS organization administrators.
   
   | Sample email template |
   | --- |
   | *Company name representative*, to grant the selected destination org access to the following IMS orgs (list of source IMS orgs), we need to ensure that an administrator for each IMS org submits their approval to allow access to their data. This helps ensure we have respected data access permissions from any impacted IMS org. To ensure we have proper approval, please have a registered Adobe admin for each admin org reply to this email with their name and IMS org that they represent, saying, "I approve" to indicate they give their approval to have this IMS org's data appear in the destination org [list destination IMS org]. Please note, this admin needs to be an admin that is registered in the Adobe system as an admin for that IMS org. |

1. Send an email to the Adobe account manager on behalf of the destination IMS organization administrator that requests the mapping from report suites within multiple source IMS organizations to the destination IMS organization. Attach the approval emails you have received from the source IMS organization administrators.

Once the Adobe account manager receives the email with the request to map Analytics data from multiple orgs, the request is reviewed within Adobe. The Adobe account manager contacts you for any additional questions, optional training, and other information. 

Once approved, the requested mapping is created and you are notified. The source IMS organization name is appended to the name of the report suite in the [list of the Analytics report suites](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#select-data) in Experience Platform.


## Limitations

The following limitations do apply for the *Cross-IMS data mapping* feature:

* You can connect a report suite only once across organizations.
* You have to delete all connections for an IMS organization that is defined as the destination IMS organization in a mapping before you can request to delete the mapping.
* ECIDs are not compatible between mapped source IMS organizations and not compatible with the destination IMS organization.


## Considerations

You might want to consider the following topics before you request the *Cross-IMS data mapping* feature:

### Profiles

Once the *Cross-IMS data mapping* feature is approved, you can add data to Experience Platform for one or more of the report suites in the destination IMS organization. You do this through the configuration of the [Analytics source connector](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics). Target datasets are then created in Experience Platform. As part of this configuration and process, you have the option to send profile data from one or more report suites to the Profile service.
   
Estimate the total number of profiles that are the result from the configuration and process, as outlined above. Ensure that total number is within the number of profiles you are contractually entitled to for the destination organization. Apply [filtering rules and conditions](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics#filtering-for-profile){target="_blank"} to include or exclude data selectively from ingestion to the Profile service. Or disable the option to send profile data to the Profile service for relevant report suites.


#### Stitching

You can use both [field-based](/help/stitching/fbs.md) and [graph-based](/help/stitching/gbs.md) stitching on the target datasets. When you use graph-based stitching on one or more of these target datasets, ensure you stay within your contractual entitlements for the number of profiles, as outlined in the [Profiles](#profiles) section. 

If you are not licensed for Real-Time Customer Profile, but you still want to use graph-based stitching on one or more target datasets, ensure you only enable the [Identity Service](/help/stitching/faq.md#enable-a-dataset-for-the-identity-service) for these target datasets.


### Permissions

A user with sufficient permissions to configure the Analytics source connector in the destination IMS organization has the ability to ingest Analytics data from any mapped source IMS organization. No permissions are checked for that user for any of the source IMS organizations.

### Report on data

The *Cross-IMS data mapping* feature is only a first step to ensure you can use the data as part of a Customer Journey Analytics [connection](/help/connections/overview.md), one or more [data views](/help/data-views/data-views.md) and [workspace projects](/help/analysis-workspace/home.md). You carefully need to inspect the data you have now available in one IMS organization. And consider features like data prep, derived fields, additional lookup tables, and more before you are able to properly report on this data.

