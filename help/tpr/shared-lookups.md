---
title: Shared Lookups
description: Shared lookups in Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Connections
role: Admin
---

# Shared lookups

In Customer Journey Analytics, a lookup dataset enriches your event data with additional context. Ffor example, a product catalog dataset that adds product names, categories, and prices to your purchase events. Or a campaign metadata dataset that adds campaign details to your marketing events.

Lookups let you report on event data using attributes that aren't stored in the events themselves.
Traditionally, a lookup dataset is joined to events through a single, fixed path. A key field in the event dataset matched to one key field in the lookup dataset. This lookup works when there is only one way to relate the two datasets, but this simple link breaks down in common real-world scenarios:

* A product catalog joined to events on either product SKU or product ID, depending on the event source.
* A user attributes lookup joined to events on different identity namespaces, depending on the channel (email for web events, loyalty ID for in-store events).
* A profile dataset that needs to be joined to events both directly (by person) and indirectly (by account, for B2B reporting purposes)

Shared lookups solve this by allowing you to define multiple join paths between a lookup dataset and the events enriched by the lookup data. Each path describes one way to match rows in the lookup to rows in the events. Dimensions or metrics, built on the lookup, can choose which path to use. The same lookup dataset can now power multiple reporting scenarios from a single configuration.

Shared lookups are also the foundation for total population reporting, which uses shared lookups to connect profile datasets to events.

## Concepts

See below for an overview of  shared lookups concepts.

### Join paths

A join path is a single way to match rows between a lookup dataset and the events. Each path has:

* A path name. A human-readable label you choose, used to identify the path in the UI when building dimensions and metrics.
* A key field on the events side. This is the field that is used for matching event with lookup data.
* A matching key field on the lookup side.  This is the the field the key matches against.
* An optional namespace. The namespace is required when the key field is an identity map.

A single lookup dataset can have one or more join paths. Dimensions and metrics built on a field in that lookup can specify which path to use; if a path isn't specified, the default path for a dataset is used.

### Match by container

For profile datasets (used with total population reporting), shared lookups support a match by container setting that automatically configures the join based on the container type:

* Match by person container. The lookup is joined to events via the person identity, using the event dataset's identity map as the key.
* Match by account container [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}. The lookup is joined via the account identity.
* Match by global account container ([!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"} with global accounts enabled). The lookup is joined via the global account identity.

Match by container handles the common cases without requiring you to manually configure the key fields. The main advantage of match by container is that deduplications are automatically handled. The container stores unique identities (for person, account, or global account). 

## Match by field

Alternatively, you can match profile datasets by field. That match results in lookups for each event in the event data based. When you use match by field for metrics, results can contain duplicated data. See [Example](#example) for a more detailed explanation.

### Identity maps as key fields

When the key field on either side of the join is an identity map (a field containing multiple namespaced identities), additional configuration is needed:

* Primary key or namespace. You can match using the primary key of the identity map, or by selecting a specific namespace. Selecting a namespace is the more common choice; the primary key is not populated in all profile data sources.
* Secondary namespace. For cases where the primary namespace is not populated on a given row (whic is common with stitched datasets), you can specify a fallback namespace. The join uses the primary namespace when populated and falls back to the secondary otherwise.
* Consistency across paths. When the same identity map is used as the key field in multiple shared lookups on a connection, the namespace selections must be consistent across those lookups.

### Lookup on lookup paths

A lookup dataset can itself be joined to another lookup dataset. This lookup creates a two-level lookup chain: event → lookup A → lookup B.

Each level of the lookup chain can have its own join paths, and dimensions or metrics built on fields in the second-level lookup traverse the chain using the path configured at each step.
Chains deeper than two levels are not supported.


## When to use shared lookups

Use Shared Lookups when any of the following is true:

* You need to join the same lookup dataset to events in more than one way.
* You work with B2C identity data where different events use different identity namespaces.
* You configure a B2B connection that needs to relate events to both people and accounts.
* You add a profile dataset to a connection for total population reporting

If your lookup dataset has a single obvious join key and you only need one way to relate it to events, you can configure a single path. Shared lookups gracefully handles that simple case as well.

## Example

The example below illustrates shared lookups in general. 
Imagine you have, next to an event dataset, the following profile, opportunity profile, account, and opportunity lookup datasets set up in a connection, together with an event dataset.


>[!BEGINTABS]

>[!TAB Events]

| Timestamp | Person ID | Account ID | Global Account ID | Opportunity ID | Page |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | A-123 | A-123 | O-432 | Home |
| 2025-02-28 05:32:13 | P-ABC | A-123 | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | P-ABC | A-123 | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | A-123 | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | O-876 | Home |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | O-876 | Gadget |

>[!TAB Profile]

| Person ID | Name | Account ID | Global Account ID |
|---|---|---|---|
| P-ABC | John | A-123 | A-123 |
| P-EFG | Kate | A-123 | A-123 |
| P-HIJ | Dave | A-789 | A-789 |
| P-LMN | Vijay | A-456 | A-789 |

>[!TAB Account]

| Account ID | Name | Global Account ID | Country | Lifetime Value |
|---|---|---|---|---:|
| A-123 | Acme | A-123 | US | $122M |
| A-456 | BigCo | A-789 | JP | $23M |
| A-789 | Giant | A-789 | UK | $48M |

>[!TAB Opportunity Profile]

| Person ID | Opportunity ID | Global Account ID |
|---|---|---|
| P-ABC | O-432 | A-123 |
| P-ABC | O-543 | A-123 |
| P-EFG | O-543 | A-123 |
| P-LMN | O-876 | A-789 |

>[!TAB Opportunity]

| Opportunity ID | Name | Account ID | Global Account ID | Status | Value |
|---|---|---|---|---|---:|
| O-432 | Acme Express | A-123 | A-123 | Open | $2M |
| O-543 | Acme CC | A-123 | A-123 | Closed | $1M |
| O-765 | Acme DX | A-123 | A-123 | Open | $8M |
| O-876 | BigCo CC | A-456 | A-789 | Open | $7M |
| O-987 | BigCo DX | A-456 | A-789 | Open | $16M |
| O-888 | Giant DX | A-789 | A-789 | Open | $13M |


>[!ENDTABS]

When this connection is created, containers are set up as part of the functionality of Customer Journey Analytics.

![ERD](./assets/erd.png){zoomable="yes"}

You use these container as part of the pathing to report on the opportunity value for each account. Based on the container selected, you can have different results.

| Account name | Opportunity value<br/>(opportunity container) | Opportunity value<br/>(subdidiairy account container) | Opportunity value<br/>(person container) |
|---|---:|---:|---:|
| Acme | $3M | $11M | $4M |
| BigCo | $7M | $23M | $7M |


### Match by opportunity container

To match the opportunities with accounts use the opportunity container as the path from event to opportunity lookup data, which results in $3M for Acme and $7 for BigCo.

![ERD-OO](./assets/erd-oo.png)

>[!BEGINTABS]

>[!TAB Event Data]

| Timestamp | Person ID | Account ID | Global Account ID | Opportunity ID ![Link](/help/assets/icons/Link.svg) | Page |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | A-123 | A-123 | **O-432** | Home |
| 2025-02-28 05:32:13 | P-ABC | A-123 | A-123 | **O-432** | Widget |
| 2025-03-13 08:21:47 | P-ABC | A-123 | A-123 | **O-432** | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | A-123 | A-123 | **O-543** | Gadget |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | **O-876** | Home |
| 2025-04-01 05:32:13 | P-LMN | A-456 | A-789 | **O-876** | Gadget |

>[!TAB Opportunity ]

| Opportunity ID ![Link](/help/assets/icons/Link.svg) | Name | Account ID | Global Account ID | Status | Value |
|---|---|---|---|---|---:|
| **O-432** | Acme Express | A-123 | A-123 | Open | **$2M** |
| **O-543** | Acme CC | A-123 | A-123 | Closed | **$1M** |
| O-765 | Acme DX | A-123 | A-123 | Open | $8M |
| **O-876** | BigCo CC | A-456 | A-789 | Open | **$7M** |
| O-987 | BigCo DX | A-456 | A-789 | Open | $16M |
| O-888 | Giant DX | A-789 | A-789 | Open | $13M |

>[!ENDTABS]


### Match by subsidiairy account container

To match the opportunities with accounts use the subsidairy account container as the path from event to opportunity lookup data, which results in $11M for Acme and $23 for BigCo.

![ERD-SAO](./assets/erd-sao.png)

>[!BEGINTABS]

>[!TAB Events]

| Timestamp | Person ID | Account ID ![Link](/help/assets/icons/Link.svg) | Global Account ID | Opportunity ID | Page |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | **A-123** | A-123 | O-432 | Home |
| 2025-02-28 05:32:13 | P-ABC | **A-123** | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | P-ABC | **A-123** | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | **A-123** | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | O-876 | Home |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | O-876 | Gadget |

>[!TAB Opportunity]

| Opportunity ID | Name | Account ID ![Link](/help/assets/icons/Link.svg) | Global Account ID | Status | Value |
|---|---|---|---|---|---:|
| O-432 | Acme Express | **A-123** | A-123 | Open | **$2M** |
| O-543 | Acme CC | **A-123** | A-123 | Closed | **$1M** |
| O-765 | Acme DX | **A-123** | A-123 | Open | **$8M** |
| O-876 | BigCo CC | **A-456** | A-789 | Open | **$7M** |
| O-987 | BigCo DX | **A-456** | A-789 | Open | **$16M** |
| O-888 | Giant DX | A-789 | A-789 | Open | $13M |


>[!ENDTABS]


### Match by person container

![ERD-POPO](./assets/erd-popo.png)

To match the opportunities with accounts use the the person container as the path from event to the opportunity profile lookup data and opportunity lookup data, which results in $4M for Acme and $7M for BigCo.


>[!BEGINTABS]

>[!TAB Events]

| Timestamp | Person ID ![Link](/help/assets/icons/Link.svg) | Account ID | Global Account ID | Opportunity ID | Page |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | **P-ABC** | A-123 | A-123 | O-432 | Home |
| 2025-02-28 05:32:13 | **P-ABC** | A-123 | A-123 | O-432 | Widget |
| 2025-03-13 08:21:47 | **P-ABC** | A-123 | A-123 | O-432 | Doohickey |
| 2025-03-17 17:21:45 | **P-EFG** | A-123 | A-123 | O-543 | Gadget |
| 2025-04-01 05:32:13 | **P-LMN** | A-456 | A-789 | O-876 | Home |
| 2025-04-01 05:32:13 | **P-LMN** | A-456 | A-789 | O-876 | Gadget |

>[!TAB Person / Opportunity]

| Person ID ![Link](/help/assets/icons/Link.svg) | Opportunity ID  | Global Account ID |
|---|---|---|
| **P-ABC** | **O-432** | A-123 |
| **P-ABC** | **O-543** | A-123 |
| **P-EFG** | **O-543** | A-123 |
| **P-LMN** | **O-876** | A-789 |

>[!TAB Opportunity Lookup]

| Opportunity ID | Name | Account ID | Global Account ID | Status | Value |
|---|---|---|---|---|---:|
| **O-432** | Acme Express | A-123 | A-123 | Open | **$2M** |
| **O-543** (2x) | Acme CC | A-123 | A-123 | Closed | $1M x 2 = **$2M** |
| O-765 | Acme DX | A-123 | A-123 | Open | $8M |
|**O-876** | BigCo CC | A-456 | A-789 | Open | **$7M** |
| O-987 | BigCo DX | A-456 | A-789 | Open | $16M |
| O-888 | Giant DX | A-789 | A-789 | Open | $13M |

>[!ENDTABS]


### Other matches by containers

There are more join paths possible in the example. For example through the global account container or the buying group container. Each of the join paths do a lookup via a match by container.

### Match by field

Instead of match by container, you can also opt to match by field. You then directly match the opportunity ids

>[!TAB Events]

| Timestamp | Person ID | Account ID | Global Account ID | Opportunity ID | Page |
|---|---|---|---|---|---|
| 2025-01-29 07:01:57 | P-ABC | **A-123** | A-123 | **O-432** | Home |
| 2025-02-28 05:32:13 | P-ABC | **A-123** | A-123 | **O-432** | Widget |
| 2025-03-13 08:21:47 | P-ABC | **A-123** | A-123 | **O-432** | Doohickey |
| 2025-03-17 17:21:45 | P-EFG | **A-123** | A-123 | **O-543** | Gadget |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | **O-876** | Home |
| 2025-04-01 05:32:13 | P-LMN | **A-456** | A-789 | **O-876** | Gadget |

>[!TAB Opportunity]

| Opportunity ID | Name | Account ID | Global Account ID | Status | Value |
|---|---|---|---|---|---:|
| **O-432** (3x) | Acme Express | A-123 | A-123 | Open | $2M x 3 = **$6M** |
| **O-543** | Acme CC | A-123 | A-123 | Closed | **$1M** |
| O-765 | Acme DX | A-123 | A-123 | Open | $8M |
|**O-876** (2x)| BigCo CC | A-456 | A-789 | Open | $7M x 2 = **$14M** |
| O-987 | BigCo DX | A-456 | A-789 | Open | $16M |
| O-888 | Giant DX | A-789 | A-789 | Open | $13M |

### Total population reporting

![ERD-TPR](./assets/erd-tpr.png)

[Total population reporting](tpr.md) uses shared lookups but does not report on events. In our example, you can only report on account opportunity value metrics using match by account container (or global account container) as that is the only join possible from a person, account, or global account container directly to opportunity lookup data. 

>[!BEGINTABS]

>[!TAB Profile]

| Person ID | Name | Account ID | Global Account ID |
|---|---|---|---|
| P-ABC | John | **A-123** | A-123 |
| P-EFG | Kate | **A-123** | A-123 |
| P-HIJ | Dave | **A-789** | A-789 |
| P-LMN | Vijay | **A-456** | A-789 |


>[!TAB Opportunity]

| Opportunity ID | Name | Account ID | Global Account ID | Status | Value |
|---|---|---|---|---|---:|
| O-432 | Acme Express | **A-123** | A-123 | Open | **$2M** | 
| O-543 | Acme CC | **A-123** | A-123 | Closed | **$1M** |
| O-765 | Acme DX | **A-123** | A-123 | Open | **$8M** | 
| O-876 | BigCo CC |**A-456** | A-789 | Open | **$7M** |
| O-987 | BigCo DX | **A-456** | A-789 | Open | **$16M** |
| O-888 | Giant DX | **A-789** | A-789 | Open | **$13M** |

* 3 opportunities for account A-123 (Acme) with a total of **$13M**.
* 2 opportunities for account A-456 (BigCo) with a total of **$23M**.
* 1 opportunity for account A-789 (Giant) with a total of **$13M**.

>[!ENDTABS]
