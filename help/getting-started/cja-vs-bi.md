---
title: Compare CJA to BI solutions
description: Compare Customer Journey Analytics to BI solutions
role: User
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: ae66cd06-7ec1-4174-a3cf-939c3a66b840
---
# Compare CJA to BI solutions

With the current focus on customer experience, brands require advanced solutions to better understand the holistic customer journey. Understanding this full customer journey allows you to analyze and gain valuable insights into how online and offline channels engage customers and lead to increasing conversion, retention, and loyalty. A customer journey in this context can be the straightforward online order of a meal at a sushi food chain. Or the purchase of a new car, where the customer combines online research with visits to the dealer showroom, and a final in-person purchase.

Many organizations have consolidated their omni-channel data into a data lake or data warehouse. Business intelligence (BI) tools are used on top of these data stores to provide the reports, visualizations, and insights that the business requires to understand the customer journey. Often, this combination of solutions and tools is general purpose by nature and design, and not explicitly focused on the customer. Customer Journey Analytics (CJA) focuses on empowering those responsible for the customer experience, such as marketers, data analysts, data scientists. The tool allows them to visualize the customer journey in full context across all channels in real time without limitations that many other BI tools have.

This section of the documentation explains the fundamental differences between CJA and commonly used BI tools, first by looking at the general workflow used to accomplish the objective mentioned above: understanding that customer journey. Then it provides more details on how data is stored, collected, and queried differently between CJA and BI tools. Finally, it explains the differences in visualization capabilities.

## Traditional BI workflow

A frequent obstacle with traditional approaches to analyzing customer journeys is that it is not customer centric. Each team collects data in siloes, analyzing and optimizing experiences based on the data that they have access to.

![Typical BI workflow](./assets/biworkflow.png)

If you want to understand how a specific digital campaign affects an offline action stored in a different data silo, you issue a request to the BI team's queue. The BI team writes the required query to acquire and transform the data. Once the raw data is retrieved, the BI team creates the visualization. The data is shared with you and you spend time combing through the insights and extracting data for activation in other systems. 

Each of these steps can take hours, days, or even weeks. If there are follow-up questions or issues with the queried data, it can take even more time before those questions are addressed and the cycle continues. For ongoing analysis, exploration and understanding of the customer journey, this process is inefficient and not scalable. Also, BI teams typically address more than just customer journey-related questions.

## CJA: Democratized workflow for online and offline data

CJA provides an environment to connect online and offline cross-channel data at the overarching customer level for the sole purpose of understanding the customer journey. It does require initial setup to [connect](/help/connections/overview.md) and [define views](/help/data-views/data-views.md) to the data you qualify as relevant. However, once completed, that data is readily available for ongoing analysis and exploration. You can progressively gain insights into and understand the customer journeys. By democratizing combined online and offline data, you are able to answer customer-journey-related questions in seconds.

![CJA workflow](./assets/cjaworkflow.png)

You can use CJA to ask questions using the visual Analysis Workspace environment and obtain insights almost instantaneously. Cross-channel data and reports are immediately available, with no SQL code required. Additional queries and analysis can be done with a simple drag & drop in the UI, with fully correlated data. You can continue to ask questions, progressively exploring more details as you require. You can then take immediate actions on the insights you discover, like sharing out audiences for activation and orchestration.

## CJA's powerful reporting engine

CJA uses a powerful proprietary architecture that distributes analysis across hundreds or even thousands of servers to display data in Analysis Workspace within seconds. Some notable properties of this processing architecture include:

*   **Optimized for individual customer-related queries**: Technically, CJA stores the data in a distributed reporting engine that makes extensive use of caching. That engine is fine tuned for responsive queries on individual-level event data, and as such perfectly optimized for customer-related queries. The reporting engine stores data in column-oriented bitmap indices that permit rapid on-the-fly calculation of aggregate metrics. It has an extensive filtering engine that permits powerful segmentation/audience analysis. And it has a core understanding of the sequence among data points that is useful in analyzing behavior across those data points (the order that things occurred) and for assigning attribution using various, complex models.

*   **Fast application of complex pathing and filters**: The reporting engine works on partially ordered, hierarchical datasets (for example, person -> sessions -> events). All data for a top-level object (individual profiles) resides on a single processing node for accurate results. This partitioning allows for fast application of complex pathing and filters. Complex operations such as sessionization, attribution, stateful persistence of data attributes, and complex data manipulation options are executed at scale with fast reporting time. In the BI world, those types of operations typically require new OLAP cubes to be created for each use case. CJA's reporting engine allows unfettered access to the entire dataset on every query, resulting in fully correlated data without requiring any cubing ahead of time.

*   **Efficient query of complex data streams**: One of the reporting engine's biggest differences from traditional SQL and NoSQL databases is its ability to determine predicates based on sequence-oriented relationships at a fundamental level. These fundamental querying operations can look at the record stream, which is composed of many interleaved (and even nested) sequences. They perform a query against all of these intertwined streams of data with the efficiency of a single, contiguous sequence operation.

*   **Designed to rapidly answer large queries**: The reporting engine is not as general purpose as traditional big data systems. However, it is specifically designed to answer queries spanning millions or even billions of records (event data / experience events), generally in under a second. Unlike other big data systems, it doesn't do this by sampling the data or by precomputing the answers to all questions it thinks you may ask. Instead, it is able to compute the answers quickly enough to support interactive querying use cases. This specific design of CJA's reporting engine facilitates the data being readily available and at high speed for ongoing analysis and exploration, therefore allowing you to progressively gain insights and understanding of customer journeys.

*   **Acts as a headless BI solution**: You define your dimensions, metrics, filters in one place, and then any CJA client (including our public CJA API) can access those components. This abstracts complex queries away from end users and guarantees that results are the same, no matter which reporting or visualization client you use. 

## CJA's unique visualization capabilities

The reporting engine is fundamental for CJA to allow you to progressively interact with and act on all the customer journey data within that reporting engine. CJA comes with an extensive set of components that empower you to do this visually and through drag-and-drop. BI visualization tools allow you to explore within the boundaries of SQL-prepared data (as defined by IT). CJA allows you to break down and slice-and-dice as much as you want, without having to go back to IT to build yet another SQL view.  

"Progressively" is a key concept here: contrary to most visualizations in BI tools, the visual drag-and-drop UI in CJA allows you to continuously break down your data for your specific needs: you can interactively build visual queries using relevant metrics, dimensions, filters (segments), calculations, time lines, annotations, and other analysis values.

Built into these visualization components are smart capabilities like:

*   **Virtual analyst features** such as [Anomaly Detection](/help/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) that use predictive algorithms and machine learning to deliver insights into what is driving unusual behaviors in your data.

*   **Advanced analysis features** that are specifically focused on customer journey insights, like [flow diagrams](/help/analysis-workspace/visualizations/c-flow/flow.md), [Attribution panel](/help/analysis-workspace/c-panels/attribution.md), [fallout diagrams](/help/analysis-workspace/visualizations/fallout/fallout-flow.md), and [dimension breakdowns](/help/components/dimensions/t-breakdown-fa.md). Examples of out-of-the-box visualizations are:

    *   [Customer retention analysis via cohort / latency tables](/help/analysis-workspace/visualizations/cohort-table/cohort-use-cases.md), where you simply drag-and-drop metrics / dimensions in a builder and you're done in less than 30 seconds,

    *   [Fallout](/help/analysis-workspace/visualizations/fallout/configuring-fallout.md) / [flow](/help/analysis-workspace/visualizations/c-flow/create-flow.md) visualizations. Set up in less than a minute.
    
*   **Segmentation capability at every step of your progressive exploration**: whenever you think it makes sense, you can publish your audience back into Experience Platform and from there to any of the supported destinations. 

*   **Sessionization** that is fully [customizable](/help/data-views/component-settings/persistence.md): you determine when a session, as part of a channel in a customer journey, starts and ends.

*   **Curation and Democratization**: The dashboards created in CJA can be:

    * [Curated](/help/analysis-workspace/curate-share/curate.md) to other individuals in the organization for continuous exploration, 
    * Exported to Excel using [Report Builder](/help/report-builder/report-buider-overview.md) (a dedicated plug-in), 
    * [Shared](/help/analysis-workspace/curate-share/share-projects.md) in various formats, including [PDF](/help/analysis-workspace/export/download-send.md), [CSV](/help/analysis-workspace/export/download-send.md) and through a [dedicated mobile app](/help/mobile-app/home.md), to those who are interested in the final reports and/or visualizations. 

Comparing CJA's visualization capabilities to what BI tools offer is difficult due to the variety of visualizations available. Some BI tools have more advanced visualizations, but CJA focuses on interactive and interoperable customer journey visualizations that allow you to break down the data within seconds while not 'charging' you for every additional query.


## Summary

CJA differs from BI tools in how it integrates a highly optimized customer-journey-focused reporting engine seamlessly with user-friendly tools and components to perform analysis and build reports and advanced visualizations. All from within one single UI, without you having to move back and forth between query engine and visualization environment.
