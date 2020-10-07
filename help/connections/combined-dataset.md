---
title: Combined event datasets
description: Learn how CJA creates a connection by combining datasets.
---

# Combined event datasets

When you create a connection, CJA combines all schemas and datasets into a single dataset. This 'combined event dataset' is what CJA uses for reporting. When you include multiple schemas or datasets in a connection:

* Schemas are combined. Duplicate schema fields are merged.
* The 'Person ID' column of each dataset are merged into a single column, regardless of their name. This column is the foundation of identifying unique visitors in CJA.
* Rows are processed based on timestamp.

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

This combined event dataset is what is used in reporting. It does not matter which dataset a row comes from; CJA treats all data as if it is in the same dataset. If a matching Person ID appears in both datasets, they are considered the same unique visitor. If a matching Person ID appears in both datasets with a timestamp within 30 minutes, they are considered part of the same session.

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
