---
title: Map Analytics data from multiple IMS organizations
description: Learn how you can request to map data from report suites from multiple source IMS organizations to a destination IMS organization.
role: Admin
solution: Customer Journey Analytics
feature: Advanced
---
# Map Analytics data from multiple IMS organizations

The Analytics source connector can only ingest data from Adobe Analytics report suites that belong to the same organization for which you are entitled to use Customer Journey Analytics. The feature to map Analytics data from multiple IMS organizations provides a solution for this limitation. The process to enable this feature is outlined in this article.


## Scenario

You are provisioned with multiple IMS organizations and do have Analytics data in multiple report suites across these IMS organizations. This setup could be the results of:

* acquisitions or mergers
* organizational structure requirements
* regional deployment constraints

Out of the box, you are not able to report on the combination of data from multiple report suites across multiple IMS organizations in Customer Journey Analytics. The reason for this limitation is that data ingestion from Adobe Analytics into Experience Platform through the Analytics source connector supports only the ingestion of data owned by a single IMS organization. The IMS organization for which you are provisioned and which you use to log in to Adobe Analytics, Experience Platform and Customer Journey Analytics.

With the *map Analytics data from multiple IMS organizations* feature, you can request Adobe to map data. The feature uses the Analytics source connector to map data from report suites that reside across multiple *source* IMS organizations to datasets that are part of one *destination* IMS organization. For example:

| Illustration | Explanation  |
|---|---|
| ![Map data across multiple IMS organizations](/help/getting-started/assets/map-data-across-ims-orgs.svg) | This mapping allows you to report on report suites that exist in IMS organization 1, IMS organization 2, and IMS organization 3 from one connection in Customer Journey Analytics that is provisioned within IMS organization 3. |

{style="table-layout:fixed"}

## How to use

To configure and enable the *map Analytics data from multiple IMS organizations* feature, you have to request the mapping through your Adobe account manager. To do so:

1. As destination IMS organization administrator, request approval emails from all source IMS organization administrator for which you want to map report suites. You can use the following text as a template for the email to request approval from the source IMS organization administrators.
   
   | Sample email template |
   | --- |
   | *Company name representative*, to grant the selected destination org access to the following IMS orgs (list of source IMS orgs), we need to ensure that an administrator for each IMS org submits their approval to allow access to their data. This helps ensure we have respected data access permissions from any impacted IMS org. To ensure we have proper approval, please have a registered Adobe admin for each admin org reply to this email with their name and IMS org that they represent, saying, "I approve" to indicate they give their approval to have this IMS org's data appear in the destination org [list destination IMS org]. Please note, this admin needs to be an admin that is registered in the Adobe system as an admin for that IMS org. |

1. Send an email as the destination IMS organization administrator to the Adobe account manager that requests the mapping from report suites within multiple source IMS organizations to the destination IMS organization. Attach the approval emails you have received from the source IMS organization administrators.

Once the account manager receives the email with the request to map Analytics data from multiple orgs, the request is reviewed within Adobe. The account manager contacts you for any additional questions, optional training, and other information. 

Once approved, the requested mapping is created and you are notified. In the list of the Analytics source connectors that you have defined in Experience Platform, the destination IMS organization is listed with the source IMS organizations appended to the name.

## Limitations and risks

The following limitations do apply for the *map Analytics data from multiple IMS organizations* feature:

* You can connect a report suite only once across organizations.
* You have to delete all connections for an IMS organization that is defined as the destination IMS organization in a  mapping before you can request to delete the mapping.
* ECIDs are not compatible between mapped source IMS organizations and not compatible with the destination IMS organization.
* A user with sufficient permissions to configure the Analytics source connector in the destination IMS organization has the ability to ingest Analytics data from any mapped source IMS organization. No permissions are checked for that user for any of the source IMS organizations.
