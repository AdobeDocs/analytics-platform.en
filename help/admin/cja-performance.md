---
title: Optimize CJA Performance
description: Best practices on how to optimize CJA performance
solution: Customer Journey Analytics
role: Admin
hide: yes
hide-from-toc: yes
---

# Optimize CJA performance

>[!NOTE]
>
>For optimizing Workspace performance factors, see [Optimize [!UICONTROL Analysis Workspace] performance](/help/analysis-workspace/workspace-faq/optimizing-performance.md).

These factors influence overall CJA performance:

| Factor | Definition | Influenced by | Optimization |
| --- | --- | --- | --- |
| Filter complexity | Intricate filters can have a significant impact on project performance. | Factors that add complexity to a filter (in descending order of impact) include: <ul><li>Operators of "contains,", "contains any of", "matches," "starts with," or "ends with" </li><li>Sequential Filtering, especially when dimension restrictions (Within/After) are used </li><li>Number of unique dimension items within dimensions used in the filter (e.g., Page = 'A' when Page has 10 unique items will be faster than Page = 'A' when Page has 100000 unique items) </li><li>Number of different dimensions used (e.g., Page = 'Home' and Page = 'Search results' will be faster than eVar 1 = 'red' and eVar 2 = 'blue')</li><li>Many OR operators (instead of AND)</li><li>Nested containers that vary in scope (e.g., "Hit" inside of "Visit" inside of "Visitor")</li></ul> | While some of the complexity factors cannot be prevented, look for opportunities to reduce the complexity of your filters. In general, the more specific you can be with your filter criteria, the better. For example:<ul><li>With containers, using a single container at the top of the filter will be faster than a series of nested containers.</li><li>With operators, "equals" will be faster than "contains", and "equals any of" will be faster than "contains any of".</li><li>With many criteria, AND operators will be faster than a series of OR operators.</li></ul> Look for opportunities to reduce many OR statements into a single "equals any of" statement.<br> |
| Visualization complexity (filters, metrics, filters) | The type of visualization (e.g. fallout vs a freeform table) added to a project by itself doesn't influence project performance very much. It is the complexity of the visualization that will add to processing time. | Factors that add complexity to a visualization include:<ul><li>Range of data requested</li><li>Number of filters applied; for instance, filters used as rows of a freeform table</li><li>Use of complex filters</li><li>[Static item](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) rows or columns in freeform tables</li><li>Filters applied to rows in freeform tables</li><li>Number of metrics included, especially calculated metrics that use filters</li></ul>|If you notice that your projects aren't loading as quickly as you'd like, try replacing some filters with eVars and filters, where possible.<br><br>If you find yourself continually using filters and calculated metrics for data points that are important to your business, consider improving your implementation to capture these data points more directly. The use of a tag manager like Adobe Experience Platform Launch and Adobe's processing rules can make implementation changes quick and easy to implement. |
| Data center capacity | The amount of reporting capacity you and other customers share within an Adobe data center. | This is impacted by the number of concurrent queries made by your organization and other organizations within your data center. | Your organization is entitled to a set capacity and if the system is under a light load, Adobe will shift more capacity to you, above and beyond your entitled allowance. |



`