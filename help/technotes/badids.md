---
title: Customer Journey Analytics Bad IDs
description: Learn about Bad IDs or BAVIDs in Customer Journey Analytics and how to identify Bad IDs in your data.
solution: Customer Journey Analytics
feature: Basics
role: Admin
---
# Bad IDs


>[!INFO]
>
>Bad IDs are also referred to as BAVIDs in the Customer Journey Analytics interface.

A Bad ID is a certain ID value (originating from either persistent ID or person ID field in a dataset) that is on more than one million events in the connection data, within a month. 

When an ID value is marked as a Bad ID, any future events that contain that ID value are discarded from the connection data and will not show up in the reporting.

