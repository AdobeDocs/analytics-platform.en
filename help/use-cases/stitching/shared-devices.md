---
title: Shared devices
description: Explanation of how to handle shared devices using stitching and other techniques.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: yes
hidefromtoc: yes
role: Admin
---

# Shared devices

This article provides context on shared devices, how to handle and mitigate data from shared devices using stitching, and understand shared device exposure in your data using Query Service. 

## What is a shared device? 

A shared device is a device that is used by more than one person. Common scenarios are devices like tablets, devices used in kiosks or computer equipment shared by agents in a call centers. 

When two people use the same device and both do make a purchase, sample event data might look like:

| Timestamp | Page name | Device ID | Email |
|---|---|---|---|
| 2023-05-12 12:01 | Home page | 1234 | | 
| 2023-05-12 12:02 | Product page  | 1234  | | 
| 2023-05-12 12:03 | Order success | 1234 | <ryan@a.com> |
| 2023-05-12 12:07 | Product page  | 1234  | | 
| 2023-05-12 12:08 | Order success | 1234 | <cassidy@a.com> | 

The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

## Improve person centric analysis

To improve person centric analysis of shared devices, you have two options: you can use stitching, or you can implement  ECID reset functionality. Both approaches are discussed in more details in the sections below.

### Stitching 

The stitching process addresses the shortcoming of the person centric approach. Stitching adds the selected person identifier (in the example data, the email) to events where that identifier does not exist. Stitching leverages a mapping between Device IDs and Person IDs to ensure that both authenticated and unauthenticated traffic can be used in analysis, keeping it person centric. See [Stitching](/help/stitching/overview.md) for more information.

Stitching can attribute shared device data using either last-auth attribution or device-split attribution. However, implementation changes via ECID reset can also address shared devices.


#### Last-auth attribution

Last-auth attributes all unknown activity from a shared device to the user who last authenticated. Last-auth is used in Audience Manager, and is the preferred approach for Real-Time Customer Data Profile use cases. The Experience Platform Identity Service builds the graph based on the last-auth attribution and, as such, is used in graph-based stitching. See [Identity graph linking rules overview](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) for more information.

When using last-auth attribution in stitching, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | 1234 | | <cassidy@a.com>| 
| 2023-05-12 12:02 | Product page  | 1234 | |<cassidy@a.com> | 
| 2023-05-12 12:03 | Order success | 1234 | <ryan@a.com> | <cassidy@a.com> |
| 2023-05-12 12:07 | Product page  | 1234  | | <cassidy@a.com> | 
| 2023-05-12 12:08 | Order success | 1234 |  <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Home page | 1234 | | <cassidy@a.com> |


#### Device-split 

Device-split attributes anonymous activity from a shared device to the user in closest proximity to the anonymous activity. Device-split is currently used in field-based stitching. Device-split is the preferred approach for analytical use cases since device-split gives credit for both unauthenticated and authenticated activity to the closest known person. Device-split is currently used in field-based stitching.

When using device-split attribution in stitching, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | 1234 | | <ryan@a.com>| 
| 2023-05-12 12:02 | Product page  | 1234 | |<ryan@a.com> | 
| 2023-05-12 12:03 | Order success | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Product page  | 1234  | | <ryan@a.com> | 
| 2023-05-12 12:08 | Order success | 1234 |  <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Home page | 1234 | | <cassidy@a.com> |


### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | 1234 | | <ryan@a.com>| 
| 2023-05-12 12:02 | Product page  | 1234 | |<ryan@a.com> | 
| 2023-05-12 12:03 | Order success | 1234 | <ryan@a.com> | <ryan@a.com> |
| 2023-05-12 12:07 | Product page  | 5678  | | <cassidy@a.com> | 
| 2023-05-12 12:08 | Order success | 5678 |  <cassidy@a.com> | <cassidy@a.com> |
| 2023-05-13 11:08 | Home page | 5678 | | <cassidy@a.com> |

## Shared device exposure 

Consider several factors to understand correctly how pervasive shared devices are in your organization. Additionally, understanding the overall contribution of events from shared devices can help you understand the impact on the overall event data used for analysis. 

To understand the shared device exposure, you can think about performing the following queries.

1. Understand the number of devices that are shared. You can use a query that counts the Device IDs that have two or more Person IDs associated with the Device ID. A sample query could look like:

   ```sql
   SELECT COUNT(*)
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
         COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
     FROM /* INSERT DATASET HERE */
     GROUP BY 1
   )
   WHERE transient_count > 1; 
   ```


2. For the shared devices, resulting from the first query, you need to understand how many events of the total events can be attributed to these shared devices. This attribution gives you a better sense of the impact of shared devices on your data and the impact when you perform analysis. A sample query could look like:

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

3. For the events attributed to shared devices (the result of the second query), you need to understand how many of these events do NOT have a Person ID. Otherwise stated, how many of the shared device events are anonymous events. Ultimately, the algorithm (last-auth, device-split, ECID-reset) you select to improve your data quality does impact these anonymous shared device events. A sample query could look like:

   ```sql
   SELECT COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) shared_persistent_ids_anon_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null))) * 100 AS shared_persistent_ids_anon_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```

4. Finally, you want to understand the exposure each customer would experience because of event misclassification. To get this exposure, you need to calculate, for each shared device, the percentage of anonymous events related to the total number of events. A sample query could look like:

   ```sql
   SELECT COUNT(*) AS total_events,
          COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL, 1, null)) shared_persistent_ids_events,
          (COUNT(IF(shared_persistent_ids.persistent_id IS NOT NULL AND events.transient_id IS NULL, 1, null)) /
           COUNT(*)) * 100 AS shared_persistent_ids_events_percent
   FROM (
     SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
            /* INSERT TRANSIENT FIELD HERE */ AS transient_id
     FROM /* INSERT DATASET HERE */ 
   ) events
   LEFT JOIN (
     SELECT persistent_id
     FROM (
       SELECT /* INSERT PERSISTENT FIELD HERE */ AS persistent_id,
              COUNT(DISTINCT /* INSERT TRANSIENT FIELD HERE */) AS transient_count
       FROM /* INSERT DATASET HERE */
       GROUP BY 1
     )
     WHERE transient_count > 1
   ) shared_persistent_ids 
   ON events.persistent_id = shared_persistent_ids.persistent_id; 
   ```


