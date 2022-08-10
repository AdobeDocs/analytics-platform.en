---
title: Compare terminology for Analytics data passed through the Analytics Source Connector
description: Some terminology differences
solution: Customer Journey Analytics
exl-id: f0f9aa1e-f9d2-4dcb-bbe9-7960412c094b
---
# Compare terminology for Analytics data passed through the Analytics Source Connector

Some terminology differences exist between Adobe Analytics, Data Feeds, Analytics Source Connector/Data Lake, and CJA. This topic aims to highlight and clarify those differences.

| Related Terms | Adobe Analytics | Adobe Analytics Data Feeds | Analytics Source Connector/Data Lake | CJA | Notes |
|---|---|---|---|---|---|
| <ul><li>Hits</li><li>Occurrences</li><li>Records</li><li>Events</li></ul> | **Occurrences** metric<br><br>See:<ul><li>[Terms used in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[Occurrences](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=en)</li></ul>  | Count of rows (records) in the data feed file  | Count of rows (records) in the dataset<br><br>See:<ul><li>[Compare your Adobe Analytics data to CJA data](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=en)</li></ul>  | **Events** metric  | <ul><li>"Hit" and "occurrence" are synonymous in Adobe Analytics.</li><li>See _Custom Events_ below.</li><li>Certain data is filtered as it passes through the Analytics Source Connector to AEP. See [Compare your Adobe Analytics data to CJA data](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=en)   |
| <ul><li>Unique Visitors</li><li>Unique Devices</li><li>Unique Cookies</li></ul>  | **Unique Visitors** metric<br><br>See:<ul><li>[Terms used in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[Unique Visitors](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html?lang=en)</li></ul>  | Distinct values of **post\_visid\_high & post\_visid\_low** concatenated together.<br><br>See:<ul><li>[Use data feeds to calculate common metrics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en)</li></ul>  | Count distinct of **endUserIDs.\_experience.aaid.id**  | **People** metric, if **endUserIDs.\_experience.aaid.id** is chosen as the Person ID. | <ul><li>A "visitor" in Adobe Analytics is usually associated with a "device identifier" such as a cookie. AAID is the primary device identifier in Adobe Analytics, not ECID. See also [AAID, ECID, AACUSTOMID and the Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/aaid-ecid-adc.html?lang=en).</li><li>"Visitor" is not an out-of-the-box metric in CJA. But if you choose **endUserIDs.\_experience.aaid.id** as the Person ID, the People metric in CJA is roughly equivalent to Unique Visitors in Adobe Analytics.</li></ul> |
| <ul><li>People</li></ul> | **People** metric<br><br> See:<ul><li>[People](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=en)</li></ul> | Not available | Count distinct of **_\<path\>_.stitchedId** (available in stitched datasets only)  | **People** metric  | <ul><li>The People metric in CJA is the count distinct of Person IDs. Depending on what you choose as the Person ID in the CJA connection, the People metric can mean different things.</ul></li>  |
| <ul><li>Visits</li><li>Sessions</li></ul> | **Visits** metric<br><br>See:<ul><li>[Terms used in Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html?lang=en)</li><li>[Visits](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=en)</li><li>[Report time processing](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en)</ul></li> | Distinct values of **post\_visid\_high, post\_visid\_low, visit\_num & visit\_start\_time\_gmt** concatenated together.<br><br>See:<ul><li>[Use data feeds to calculate common metrics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en)</li></ul> | Not available  | **Sessions** metric  | <ul><li>With report-time processing in Adobe Analytics virtual report suites and CJA data views, the concept of a visit (session) is configurable. As a result, visit (session) counts may differ between environments depending on the definition applied. See also [Compare data processing across Adobe Analytics and CJA reporting features](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/data-processing-comparisons.html?lang=en) and [Virtual Report Suites, Data Views, AEP Sandboxes and the Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/compare-aa-cja/vrs-dataview-sandbox-adc.html?lang=en).                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <ul><li>Custom events</li><li>Success events</li></ul>  | Custom events 1-1000  | **post\_events\_list**<br><br>See:<ul><li>[Use data feeds to calculate common metrics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html?lang=en)  | **\_experience.analytics.<ul>event1to100.event1** through<br>**event901to1000.event1000**</ul> |**\_experience.analytics.<ul>event1to100.event1** through<br>**event901to1000.event1000**</ul> | <ul><li>An "event" in Adobe Analytics is a [Success Event](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=en) (custom event) that has been set in an Adobe Analytics image request (data collection server call.)</ul>  |
| <ul><li>Event deduplication</li><li>Metric deduplication</ul></li>  | See:<ul><li>[Event ID serialization](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=en)</li></ul>  |  The **post_events_list** column contains deduplicated event metrics.<br><br>See <ul><li>[Data column reference](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=en). </ul></li> | Not available  | See:<ul><li>[Metric deduplication component settings](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=en)  | <ul><li>Event/metric de-duplication in Adobe Analytics differs slightly from CJA. In Adobe Analytics, deduplication occurs at data processing time. In CJA, deduplication occurs at report runtime, providing more flexibility. Deduplicated metrics may differ slightly in Adobe Analytics vs CJA.</li></ul>    |    
| <ul><li>Instances metrics</li></ul>| See:<ul><li>[Instances](https://experienceleague.adobe.com/docs/analytics/components/metrics/instances.html?lang=en) | Count of times a "pre" variable is not null (e.g. eVar1). | Count of times a "mid" variable is not null (e.g. **\_experience.analytics.<br>customDimensions.eVars.eVar1**). | **Instances** metrics | <ul><li>Instances is normally associated with prop and eVar columns as a means to determine how many times the variable has been set. |