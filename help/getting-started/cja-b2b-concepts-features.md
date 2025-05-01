---
title: Customer Journey Analytics B2B Edition concepts and features
description: Concepts and features for the B2B Edition of Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: yes
hidefromtoc: yes
badgePremium: label="B2B Edition"
exl-id: df2cc922-d214-49b9-8fdb-443cc1dac05b
---
# B2B Edition concepts and features

{{draft-b2b}}

This article explains concepts like connections, identifiers, containers, and datasets, commonly used in Customer Journey Analytics. And how the Customer Journey Analytics B2B Edition adds additional features to these concepts.


## Connections and identifiers

In Customer Journey Analytics, you pick a common identifier, known as Person ID, to connect your event data with other datasets like profile dataset and lookup datasets. This type of connection is known as a person-based connection which facilitates person-based reporting and analysis.

In Customer Journey Analytics B2B Edition, you can select between a person-based connection or an account-based connection. An account-based connection facilitates account-based reporting and analysis.

* For a person-based connection, you select Person as the primary identifier. You can then configure and set up your connection, data view and workspace projects for person-based reporting.
* For an account-based connection, you select Account as the primary identifier. You can then optionally add additional containers for Global Account, Buying Group and Opportunity. Based on whether you add a Global Account or not, your primary identifier is an account identifier or a global account identifier.


## Containers

In Customer Journey Analytics containers are generated as part of the configuration of a connection and data view. Containers store only identifiers to facilitate quick and performant execution of functionalities like segmentation, breakdowns, and more.

### Standard containers

Customer Journey Analytics is built around the concept of three containers: Person, Session, and Event. During a configuration, these containers are implicitly generated.

You can redefine how these containers are named when you configure a data view but the hierarchy and relationships between the containers is predetermined. The Session container is generated based on how you define a session in the [Session settings](/help/data-views/session-settings.md) in your data view.

![B2C](assets/b2c-containers.svg){zoomable="yes"}


### B2B containers

In Customer Journey Analytics B2B Edition, an Account container is added to the list of generated containers. And you have the option to configure the generation of additional containers, like Global Account, Buying Group, and Opportunity.

The hierarchy and relationships between the containers is predetermined. Opportunity, Buying Group and Person are all sibling containers of the Account container. In that hierarchy the Session container between the Person container and Event container is generated based on how you define a session in the [Session settings](/help/data-views/session-settings.md) in your data view. Additional session containers, for example between the Account container and Event container, are currently not generated and supported. See the table below for a description and basic usage of the B2B containers.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

| B2B container | Description<br/>Basic use case |
|---|---|
| Account | A company that is a customer or potential customer of your business. The company could be a subsidiary or division of a larger organization. Account represents the organization that you are selling to and want to track at that organization level. |
| Global Account (optional) | The top parent company of a group of related companies. A global account has no parent company, but may have subsidiaries or divisions belonging to the global account. When you have the Global Account container configured in your connection, an account that has no parent or subsidiaries should be listed in both the account field and global account field. |
| Opportunity (optional) | A collection of products and services that are sold together. An opportunity often involved various stages in the sales cycle up until the closure of the sale.<br>You would use data to measure the opportunity progression through the sales funnel. For example, a report that provides details on the top opportunities that moved from stage 3 to stage 4. |
| Buying group (optional) | A collection of people within an organization that is involved in the decision-making process to purchase a product or service. <br/>You would use buying group data to track buying groups through campaign management. For example, build an audience segment of key buying groups.<br/> You most likely want a lookup from the buying group to profile data, so you can report on the people in a buying group. |
| Person | An individual, often identified by a unique e-mail address that has interacted with the company. <br/>You would use the profile data to identify people who work for an account. For example: target all the people at an account that have signed-up for a conference. |

>[!IMPORTANT]
>
>* If you have **enabled** the Global Account container in an account-based connection, every record in your event datasets should contain an Account ID and Global Account ID. If not, the record is skipped.
>* If you have **not enabled** the Global Account container in an account-based connection, every record in your event datasets should contain an Account ID. If not, the record is skipped.

## Datasets

When you configure [datasets settings](/help/connections/create-connection.md#dataset-settings) for your account-based connection in Customer Journey Analytics B2B Edition, the options available for some of the settings depend on the [dataset type](/help/connections/create-connection.md#dataset-types). For example, you have to:

* Specify identifiers for each of the containers that you have configured for your event datasets.
* Define an account field or global account field for your profile datasets.
* Define keys and how to match these keys (by container of field) for lookup datasets.

## Match by container or field

You can define for each lookup dataset, whether you match the dataset by field or by container.

### Match by container

If a record dataset uses a match by container, the record dataset is treated as a profile dataset type and as a Profile dataset in the user interface. Use match by container on datasets that support your configured containers. For example, a Buying Group dataset. 

### Match by field

If a record dataset uses a match by field, the record dataset is treated as a lookup dataset type and as a Lookup dataset in the user interface. Use match by field on datasets that support additional details through lookup For example, a Marketing List Member dataset, or a Product Details dataset.
 

## Report on person and account based data

If you want to report on person-based containers (and person identities) and account-based containers (and account identities), you should set up two separate connection within Customer Journey Analytics. One connection where you select Person as the Primary ID, and one connection where you select Account as the Primary ID. Customer Journey Analytics does not support person-based and account-based reporting from a single container hierarchy. 
