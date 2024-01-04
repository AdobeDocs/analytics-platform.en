---
title: Combined event datasets
description: Learn how Customer Journey Analytics creates a connection by combining datasets.
exl-id: 9f678225-a9f3-4134-be38-924b8de8d57f
solution: Customer Journey Analytics
feature: Connections
role: Admin
---

# Combined event datasets

When you create a connection, Customer Journey Analytics combines all schemas and datasets into a single dataset. This 'combined event dataset' is what Customer Journey Analytics uses for reporting. When you include multiple schemas or datasets in a connection:

* Schemas are combined. Duplicate schema fields are merged.
* The 'Person ID' column of each dataset are merged into a single column, regardless of their name. This column is the foundation of identifying unique persons in Customer Journey Analytics.
* Rows are processed based on timestamp.
* Events are resolved down to the millisecond level.

## Example

Consider the following example. You have two event datasets, each with different fields containing different data.

>[!NOTE]
>
>Adobe Experience Platform typically stores timestamp in Unix milliseconds. For readability in this example, date and time is used.

| `example_id` | `timestamp` | `string_color` | `string_animal` | `metric_a` |
| --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | |
| `user_310` | `1 Jan 7:04 AM` | | | `2` |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | `3` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | `4` |
| `user_847` | `2 Jan 12:44 PM` | | | `2` |

| `different_id` | `timestamp` | `string_color` | `string_shape` | `metric_b` |
| --- | --- | --- | --- | --- |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | `Circle` | `8.5` |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | `Square` | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | `Triangle` | `3.1` |

When you create a connection using these two event datasets, the following table is used for reporting.

| `id` | `timestamp` | `string_color` | `string_animal` | `string_shape` | `metric_a` | `metric_b` |
| --- | --- | --- | --- | --- | --- | --- |
| `user_310` | `1 Jan 7:02 AM` | `Red` | `Fox` | | | |
| `user_310` | `1 Jan 7:04 AM` | | | | `2` | |
| `user_310` | `1 Jan 7:08 AM` | `Blue` | | | `3` | |
| `user_847` | `2 Jan 12:26 PM` | `Yellow` | | `Circle` | | `8.5` |
| `user_847` | `2 Jan 12:31 PM` | | `Turtle` | | `4` | |
| `user_847` | `2 Jan 12:44 PM` | | | | `2` | |
| `user_847` | `2 Jan 1:01 PM` | `Red` | | | | |
| `alternateid_656` | `2 Jan 8:58 PM` | `Red` | | `Square` | | `4.2` |
| `alternateid_656` | `2 Jan 9:03 PM` | | | `Triangle` | | `3.1` |

This combined event dataset is what is used in reporting. It does not matter which dataset a row comes from; Customer Journey Analytics treats all data as if it is in the same dataset. If a matching Person ID appears in both datasets, they are considered the same unique person. If a matching Person ID appears in both datasets with a timestamp within 30 minutes, they are considered part of the same session.

This concept also applies to attribution. It does not matter which dataset a row comes from; attribution works exactly as if all events came from a single dataset. Using the above tables as an example:

If your connection only included the first table and not the second, pulling a report using the `string_color` dimension and `metric_a` metric using last touch attribution would show:

| string_color | metric_a |
| --- | --- |
| Unspecified | 6 |
| Blue | 3 |
| Red | 2 |

However, if you included both tables in your connection, attribution changes since `user_847` is in both datasets. A row from the second dataset attributes `metric_a` to 'Yellow' where they were previously unspecified:

| string_color | metric_a |
| --- | --- |
| Yellow | 6 |
| Blue | 3 |
| Red | 2 |

## Cross-channel analysis

The next level of combining datasets is cross-channel analysis, where datasets from different channels are combined, based on a common identifier (person ID). Cross-channel analysis can benefit from stitching functionality, allowing you to rekey a dataset's person ID so the dataset is properly updated to enable a seamless combination of multiple datasets. Stitching looks at user data from both authenticated and unauthenticated sessions to generate a stitched ID.

Cross-channel analysis allows you to answer questions such as:

* How many people begin their experience in one channel, then finish it in another?
* How many people interact with my brand? How many and what types of devices do they use? How do they overlap?
* How often do people begin a task on a mobile device and then later move to a desktop PC to complete the task? Do campaign click-throughs that land on one device, lead to conversion somewhere else?
* How does my understanding of campaign effectiveness change if I consider cross-device journeys? How does my funnel analysis change?
* What are the most common paths users take from one device to another? Where do they drop out? Where do they succeed?
* How does the behavior of users with multiple devices differ from the users with a single device?


For a more information on cross-channel analysis, refer to the specific use case:

* [Cross-channel analysis](../use-cases/cross-channel/cross-channel.md)

For a more in-depth discussion stitching functionality, go to:

* [Stitching overview](/help/stitching/overview.md)
* [How stitching works](../stitching/explained.md)
* [Frequently Asked Questions](/help/stitching/faq.md)

