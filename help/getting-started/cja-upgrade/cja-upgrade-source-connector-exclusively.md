---
title: Use the Analytics source connector exclusively to upgrade to Customer Journey Analytics
description: Learn how to create the Analytics source connector and map fields
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: 34e5f97b-c936-4de6-acc9-5774bc908655
---
# Use the Analytics source connector exclusively to upgrade to Customer Journey Analytics {#use-source-connector-exclusively}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-exclusively"
>title="Solely use the Analytics source connector"
>abstract="(Not recommended) You cannot integrate with other Adobe Experience Platform services or move off of Adobe Analytics with the Analytics source connector. Tying data from other sources likely requires stitching. Meet all of these requirements in the questionnaire to select this option."

<!-- markdownlint-enable MD034 -->

>[!NOTE]
> 
>Use the information on this page when answering questions in the [Customer Journey Analytics upgrade checklist](https://gigazelle.github.io/cja-ttv/).

Though it is not recommended, you can use the Analytics source connector as the sole implementation path for Customer Journey Analytics. However, because of the inherent disadvantages associated with this type of upgrade, Adobe recommends using the Analytics source connector in conjunction with a new implementation of the Experience Platform Web SDK. For more information about this recommended upgrade path, see [Recommended path when upgrading from Adobe Analytics to Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md). 

Use the information in the table below to understand the advantages and disadvantages of using the source connector exclusively. 

If you decide to use the Analytics source connector as the sole implementation path for Customer Journey Analytics, follow the implementation steps described in [Ingest and use data using source connectors](/help/data-ingestion/sources.md).

| Advantages | Disadvantages |
|----------|---------|
| <ul><li>Least time-consuming and demanding upgrade path. <p>Data is migrated to Customer Journey Analytics quickly and easily.</p></li></ul> | <ul><li>**Data is not sent to Edge Network**: <p>This results in the following disadvantages:</p><ul><li>Highest level of [latency](/help/technotes/guardrails.md#latencies) in reporting across all upgrade paths; not optimized for real-time personalization use cases.</li><li>Data cannot be shared with other Adobe Experience Platform applications; it is constrained to Customer Journey Analytics only</li><li>Reliant on Adobe Analytics nomenclature (prop, eVar, event, and so forth)</li></ul><li>**Difficult to move to the Web SDK in the future**: Eventually, you will likely want access to the advantages provided by the Experience Platform Web SDK. In order to start using the Experience Platform Web SDK, you must do a new implementation.</li><li>**Uses the Analytics Experience Event field group in your schema**: This field group adds many Adobe Analytics events that are not needed in your Customer Journey Analytics schema.  This can lead to a more cluttered, complex schema than what is otherwise needed for Customer Journey Analytics.</li><li>**Requires licenses for both Adobe Analytics and Customer Journey Analytics**: Using the Analytics source connector requires that you pay for both Adobe Analytics and Customer Journey Analytics.</li></ul> | 

{style="table-layout:auto"}
