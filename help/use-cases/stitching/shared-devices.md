---
title: Shared devices
description: Explanation of how to handle shared devices using stitching and other techniques.
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: yes
hidefromtoc: yes
role: Admin
exl-id: a7d14968-33a2-46a8-8e32-fb6716650d0a
---
# Shared devices

This article provides context on shared devices, how to handle and mitigate data from shared devices using [stitching](/help/stitching/overview.md), and understand shared device exposure in your data using Query Service. 

## What is a shared device? 

A shared device is a device that is used by more than one person. Common scenarios are devices like tablets, devices used in kiosks or computer equipment shared by agents in a call centers. 

When two people use the same device and both do make a purchase, sample event data might look like:

|Event | Timestamp | Page name | Device ID | Email |
|--:|---|---|---|---|
|1 | 2023-05-12 12:01 | Home page | `1234` | | 
|2 | 2023-05-12 12:02 | Product page  | `1234`  | | 
|3 | 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` |
|4 | 2023-05-12 12:07 | Product page  | `1234`  | | 
|5 | 2023-05-12 12:08 | Order success | `1234` | `cassidy@a.com` | 

As you can see from this table, once authentication happens on events 3 and 5, a link begins to form between a device id and a person id. To understand the impact of any marketing efforts on a person level, these unauthenticated events need to be attributed to the right person. 

<!--
The order success (purchase) events assign the data accurately to the correct email. How this assignment impacts your analysis depends on how you perform analysis:

- Device centric approach: analysis performed using the Device ID. With this approach, both authenticated and unauthenticated data are included in analysis. However, this approach does not allow for a more person based analysis. 
- Person centric approach: analysis performed using the email address or other person identifier. With this approach, only authenticated events are included in the analysis. This approach doesn't provide a complete picture of the customer journey, including acquisition

-->

## Improve person centric analysis

The stitching process addresses this attribution problem by adding the selected person identifier (in the example data, the email) to events where that identifier does not exist. Stitching leverages a mapping between Device IDs and Person IDs to ensure that both authenticated and unauthenticated traffic can be used in analysis, keeping it person centric. See [Stitching](/help/stitching/overview.md) for more information.

Stitching can attribute shared device data using either last-auth attribution or device-split attribution. All attempts to stitch unauthenticated events to a known user are non-deterministic.


### Last-auth attribution

Last-auth attributes all unknown activity from a shared device to the user who last authenticated. The Experience Platform Identity Service builds the graph based on the last-auth attribution and, as such, is used in graph-based stitching. See [Identity graph linking rules overview](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/identity-graph-linking-rules/overview) for more information.

When last-auth attribution is used in stitching, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `cassidy@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`cassidy@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `cassidy@a.com` |
| 2023-05-12 12:07 | Product page  | `1234`  | | `cassidy@a.com` | 
| 2023-05-12 12:08 | Order success | `1234` |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | `1234` | | `cassidy@a.com` |


### Device-split 

Device-split attributes anonymous activity from a shared device to the user in closest proximity to the anonymous activity. Device-split is the preferred approach for analytical use cases since device-split gives credit for both unauthenticated and authenticated activity to the closest known person. Device-split is currently used in field-based stitching.

When device-split attribution is used in stitching, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | `1234`  | | `ryan@a.com` | 
| 2023-05-12 12:08 | Order success | `1234` |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | `1234` | | `cassidy@a.com` |


<!--

### ECID reset 

As the name implies, ECID reset implements functionality that resets the ECID on a predetermined trigger, in most cases a login or logout event. With this implementation, a single device gets a new ECID every time the predetermined trigger fires. Essentially, this reset forces the device to become a *new device* over and again from a data perspective. The ECID reset also helps to prevent shared devices from even showing up in the data. No additional algorithms are required, but you have the responsibility to implement the ECID reset signal as part of your Adobe data collection implementation.


When using ECID reset, Stitched IDs resolve as shown in the table below. 

| Timestamp | Page name | Device ID | Email | Stitched ID |
|---|---|---|---|---|
| 2023-05-12 12:01 | Home page | `1234` | | `ryan@a.com`| 
| 2023-05-12 12:02 | Product page  | `1234` | |`ryan@a.com` | 
| 2023-05-12 12:03 | Order success | `1234` | `ryan@a.com` | `ryan@a.com` |
| 2023-05-12 12:07 | Product page  | 5678  | | `cassidy@a.com` | 
| 2023-05-12 12:08 | Order success | 5678 |  `cassidy@a.com` | `cassidy@a.com` |
| 2023-05-13 11:08 | Home page | 5678 | | `cassidy@a.com` |

-->

## Shared device exposure 

Consider several factors to understand correctly how pervasive shared devices are in your organization. Additionally, understanding the overall contribution of events from shared devices can help you understand the impact on the overall event data used for analysis. 

To understand the shared device exposure, you can think about performing the following queries.

1. **Identify shared devices**
   
   To understand the number of devices that are shared, perform a query that counts the Device IDs with two or more Person IDs associated. This helps identify devices used by multiple individuals.

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


2. **Attribution of events to shared devices**
    
   For the shared devices identified, determine how many events out of the total can be attributed to these devices. This attribution provides insight into the impact shared devices have on your data and the implications for analysis.

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

3. **Identify anonymous events on shared devices**
    
   Among the events attributed to shared devices, identify how many lack a Person ID, indicating anonymous events. The algorithm you choose (for example last-auth, device-split, or ECID-reset) to enhance data quality affects these anonymous events.

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

4. **Calculate exposure from event misclassification**
    
   Finally, assess the exposure each customer might face due to event misclassification. Calculate the percentage of anonymous events over the total events for each shared device. This helps understand the potential impact on customer data accuracy.

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
