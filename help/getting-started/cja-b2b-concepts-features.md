---
title: Customer Journey Analytics B2B Edition concepts and features
description: Concepts and features for the B2B Edition of Customer Journey Analytics.
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
hide: yes
hidefromtoc: yes
badgePremium: label="B2B Edition"

---
# B2B Edition concepts and features

{{draft-b2b}}

This article explains general concepts and features on datasets and containers and how these differ between the standard and the B2B Edition of Customer Journey Analytics.

Datasets are the sources of a connection. As part of setting up a connection, you define datasets to be part of that connection. 

Containers are a used in Customer Journey Analytics to to support and facilitate features like filters, calculated metrics, and advanced analytics capabilities. 




## Standard containers

The *standard* version of Customer Journey Analytics is build around the concept of three containers: Person, Session, and Event. In a standard Customer Journey Analytics setup, these relevant containers are implicitly generated based on your setup.

You can redefine how these containers are named when you configure a Data view but conceptually the standard version uses a person-based container hierarchy.

![B2C](assets/b2c-containers.svg){zoomable="yes"}

In the connection, you add Event, Profile and Lookup datasets and you select identities to use to define the connection between these datasets. As part of the connection, a person-based container hierarchy is generated automatically. In that hierarchy the Session container is defined by the [Session settings](/help/data-views/session-settings.md) in your Data view.


## B2B containers

In Customer Journey Analytics B2B Edition, an Account container is added to the list of generated containers.  And you have the option to configure the generation of additional containers, like Global Account, Buying Group, and Opportunity.

![B2B](assets/b2b-containers.svg){zoomable="yes"}

In the connection, you add Event, Account, Global Account, Opportunity, Buying Group and other Lookup datasets. You select Account as the primary ID for the connection so you can use account-based identities to define the connection between the datasets. As part of the connection, an account-based container hierarchy is generated automatically. In that hierarchy the Session container between the Person container and Event container is defined by the [Session settings](/help/data-views/session-settings.md) in your Data view. Additionally Session containers, for example between Account and Event, are currently not supported.

Opportunity, Buying Group and Person are all sibling containers of the Account container. See the table below for a description and basic usage.

| B2B container | Description<br/>Basic use case |
|---|---|
| Account | A company that is a customer or potential customer of your business. This could be a subsidiary or division of a larger organization. Account represents the organization that you are selling to and want to track at that organization level. |
| Global Account (otional) | The top parent company of a group of related companies. A global account has no parent company, but may have subsidiaries or divisions belonging to the global account. An account that has no parent or subsidiaries should be listed in both the account field and global account field, if both are enabled as part of setting up a connection. |
| Opportunity (optional) | A collection of products and services that are sold together. An opportunity often involved various stages in the sales cylce to close as a sale.<br>You would use opportunity data to measure the opportunity progression through the sales funnel. For example, a report that provide details on the top opportunities that moved from opportunity stage 3 to stage 4. |
| Buying group (optional) | A collection of people within an organization that is involved in the decision-making process to purchase a product or service. <br/>You would use buying group data to track buying groups through campaign management. For example, buikd an audience segment of key buying groups.<br/> You most likely want a lookup from the buying group to profile data, so you can report on the people in a buying group. |
| Person | An individual, often identified by a unique e-mail address that has interacted with the company. <br/>You would use the profile data to identify people who work for an account. For example: target all the people at an account that have signed-up for a conference. |


## Match by container or field

When you define a connection in Customer Journey Analytics, you can define for each record (profile or lookup) dataset, whether that dataset is matched by container or matched by field.

### Match by container

If a record dataset is matched by container, for example Buying Group, the record dataset is treated as a profile dataset type and as a Profile dataset in the user interface.

### Match by field

If a record dataset is matched by field, for example Marketing List Member, the record dataset is treated as a lookup dataset type and as a Lookup dataset in the user interface.
 


## Report on person and account based data

If you want to report on person-based containers (and person identities) and account-based containers (and account identiies), you should set up two separate connection within Customer Journey Analytics. One connection where you select Person as the Primary ID, and one connection where you select Account as the Primary ID. Customer Journey Analytics does not support person-based and account-based reporting from the same container. You can 
