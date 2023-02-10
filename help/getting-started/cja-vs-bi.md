---
title: Compare CJA to BI tools
description: Compare the workflow of Customer Journey Analytics to a typical BI workflow
role: User
solution: Customer Journey Analytics
feature: CJA Basics
---

# Compare CJA to BI tools

With the current focus on customer experience, brands require advanced solutions to better understand the holistic customer journey. Understanding this full customer journey allows you to analyze and gain valuable insights into how online and offline channels engage customers and lead to increasing conversion, retention, and loyalty. A customer journey in this context can range from the straightforward online order of a meal at a sushi food chain to the purchase of a new car, combinining online research with visits to the dealer showroom, and a final in-person purchase.

Many organizations have consolidated their omnichannel data into a data lake or data warehouse. Business intelligence (BI) tools are used on top of these to provide the reports, visualizations, and insights that the business requires to understand the customer journey. Often, this combination of solutions and tools is general-purpose by nature and design, and not explicitly focusing on the customer. Customer Journey Analytics focuses on empowering those responsible for the customer experience, such as marketers, data analysts, data scientists. The tool allows them to visualize the customer journey in full context across all channels in real-time without limitations that many other BI tools have.

This section of the documentation explains the fundamental differences between CJA and commonly used BI tools, first by looking at the general workflow used to accomplish the objective mentioned above: understanding that customer journey. Then it provides more details on how data is stored, collected and queried differently between CJA and BI tools. Finally, it explains the differences in visualization capabilities.

## Traditional BI workflow

A frequent obstacle with traditional approaches to analyzing customer journeys is that it is not customer centric. Each team collects data in siloes, analyzing and optimizing experiences based on the data that they have access to.

![Typical BI workflow](./assets/biworkflow.png)

If you want to understand how a specific digital campaign affects an offline action stored in a different data silo, you issue a request to the BI team's queue. The BI team writes the required query to acquire and transform the data. Once the raw data is retrieved, the BI team creates the visualization. The data is shared with you and you spend time combing through the insights and extracting data for activation in other systems. 

Each of these steps can take hours, days, or even weeks. If there are follow up questions or issues with the queried data, it can take yet even more time before those questions are addressed and the cycle continues. For ongoing analyzing, exploring and understanding the customer journey, this process is inefficient and isn't built for scale. Additionally, BI teams typically address more than just customer journey related questions.

## CJA: Democratized workflow for online and offline data

CJA is a solution that provides an environment to connect online and offline cross-channel data at the overarching customer level for the sole purpose of understanding the customer journey. It does require initial setup to connect and define views to the data you qualify as relevant. However, once completed, that data is then readily available for ongoing analysis and exploration, resulting in progressively gaining insights into and understanding of customer journeys. By democratizing combined online and offline data, you will be able to answer customer journey related questions in seconds.

![CJA workflow](./assets/cjaworkflow.png)

You can use CJA to ask questions using the visual analysis workspace environment and obtain insights in seconds. The cross-channel data and reports are immediately available, with no SQL code required. Additional queries and analysis can be done with a simple drag & drop in the UI, with fully correlated data. You can continue to ask questions, progressively exploring more and more details as you require. You can then take immediate actions on the insights you discover, like sharing audiences out for activation and orchestration.

## CJA's powerful reporting engine

<!--(*add bullets to the individual strengths of the reporting engine, and a catchy summary at the beginning. I took a stab...but feel free to change them*)

CJA is based on the data that is ingested in Adobe Experience Platform as datasets. You can use an Adobe Analytics dataset coming from Adobe Analytics data streaming into Adobe Experience Platform through the Analytics source connector. Or you can use a CRM dataset resulting from configuring a Microsoft Dynamics source connector to your Microsoft Dynamics instance. See the [Data Ingestion](../data-ingestion/data-ingestion.md) section for more information on how to ingest data into Adobe Experience Platform and use it in Customer Journey Analytics.-->

CJA uses a powerful proprietary architecture that distributes analysis across hundreds or even thousands of servers to display data in Analysis Workspace within seconds. Some notable properties of this processing architecture include:

* **Optimized for individual customer-related queries**: Technically, CJA does not directly use datasets from AEP, but replicates all data from datasets that are defined in a [Connection](../connections/overview.md). It stores the data in a distributed reporting engine that makes extensive use of caching. That engine is fine-tuned for responsive queries on individual-level time series data, so it is perfectly optimized for individual customer-related queries. The reporting engine stores data in column-oriented bitmap indices that permit rapid on-the-fly calculation of aggregate metrics. It has an extensive filtering engine that permits powerful segmentation/audience analysis. And it has a core understanding of the sequence among data points that is particularly useful in analyzing behavior across those data points (the order that things occurred) and for assigning attribution using various, complex models.

* **Fast application of complex pathing and filters**: The reporting engine works on partially-ordered, hierarchical datasets (e.g. person -> sessions -> events), and all data for a particular top-level object (individual profiles) resides on a single processing node for accurate results. This partitioning allows for fast application of complex pathing and filters.

* **Efficient query of complex data streams**: One of the reporting engine's biggest differences from traditional SQL and NoSQL databases is its ability to determine predicates based on sequence-oriented relationships at a fundamental level. These fundamental querying operations can look at the record stream, which is composed of many interleaved (and even nested) sequences, and perform a query against all of these intertwined streams of data with the efficiency of a single, contiguous sequence operation. 

* **Designed to rapidly answer very large queries**: Although the reporting engine is not as general purpose as other, more familiar big data systems, it is specifically designed to answer queries spanning millions or even billions of records (time-series data/experience events), generally in under a second. Unlike other big data systems, it doesn't do this by sampling the data or by precomputing the answers to all questions it thinks you may ask, but it is instead able to compute the answers quickly enough to support interactive querying use cases. This specific design of CJA's reporting engine facilitates the data being readily available and at high speed for ongoing analysis and exploration, therefore allowing you to progressively gain insights and understanding of customer journeys.

## Unique visualization capabilities

The reporting engine is fundamental for CJA to allow you to progressively interact with and act on all the customer journey data within that reporting engine. CJA comes with an extensive set of components that empower you to do this visually and through drag-and-drop rather than by composing SQL-type of queries. 

Progressively is a key concept here: contrary to most visualizations in typical BI tools, the visualization components in CJA allow you to continuously breakdown your data in unlimited ways for your specific needs: build queries using relevant metrics, dimensions, filters, time lines, and other analysis breakdown values. 

Built-in with these visualization components are smart capabilities like 

* **Virtual analyst** features such as Anomaly Detection that use predictive algorithms and machine learning to deliver insights into what is driving unusual behaviors in your data.

* **Advanced analysis features** that are specifically focused on customer journey insights, like flow diagrams, attribution IQ, fallout diagrams and dimension breakdowns.

* **Segmentation capability at every step of your progressive exploration**: whenever you think it makes sense you can publish your audience back into Experience Platform and from there to any of the supported destinations, 

* **Sessionization** that is fully customizable: you determine when a session, as part of a channel in a customer journey, starts and ends.

* **Curation**: The dashboards you build in CJA can be easily curated to other individuals in the organization for continous exploration and also be shared in various formats to those who are only interested in the final reports and/or visualizations.

Comparing the visualization capabilities of CJA to those of BI tools is not straightforward due to the diversity of visualizations between all solutions available in this domain. It is fair to say that some BI tools do offer more advanced visualizations than what CJA offers. CJA, however does offer a number of visualizations focusing very specifically on the customer journey and do allow for continuous breakdown. These kind of interactive customer journey visualizations are often not found in BI solutions.

## Summary

< Here I have to come up with a summary, e.g. showing table that does compare CJA vs BI on a couple of line items; still in progress...>
