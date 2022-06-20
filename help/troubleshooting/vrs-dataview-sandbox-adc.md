# Virtual Report Suites, Data Views, AEP Sandboxes and the Analytics Source Connector

Adobe provides a variety of means to create virtual reporting environments and sandbox environments. It is useful to understand the similarities and differences between the following features and how these features relate to the [Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en):

* Adobe Analytics virtual report suites
* CJA data views
* AEP sandboxes

# Adobe Analytics Virtual Report Suites (VRS)

For more information, see: [Virtual report suites overview](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en).

A VRS:

* Can be based on Adobe Analytics segments.
* Can be applied to both historical and new data in a non-destructive manner.
* Allows you to create one or many virtual views on top of an Adobe Analytics report suite for for use by different business teams.
* May be used to control access to and curate different kinds of data for different users in Adobe Analytics.
* Provides optional [report-time processing](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) capabilities for Adobe Analytics.
* Is applied at report runtime. This is _after__ the data has been collected and stored within Adobe Analytics.
* Is required for [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en) in Adobe Analytics.

A virtual report suite is (does) not:

* Provide a means to combine report suites together.
* Available in Adobe Analytics Data Warehouse.
* Available as an source for dataflows into AEP via the Analytics Source Connector. Only full (non-virtual) report suites are available for use with the Analytics Source Connector.


# CJA data views

For more information, see: [Data views overview](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en).

A data view:

* Can be based on CJA filters.
* Can applied to both historical and new data in a non-destructive manner.
* Allows you to create one or many virtual views on top of a CJA connection for use by different business teams.
* May be used to control access to and curate different kinds of data for different users in CJA.
* Provides powerful non-destructive options for transforming and enhancing data coming into CJA through a CJA connection.
* Is based on the report-time processing capabilities of CJA.
* Is applied at report runtime. This is _after_ the Analytics Source Conector has written the report suite to a dataset in the AEP data lake, and after the data has been ingested into CJA via a CJA connection.

A data views does not:

* Directly provide a means for combining report suites or other datasets. However, because a data view sits on top of a CJA connection, and a connection may be used to combine multiple report suites and AEP datasets, the combined data from the CJA connection is available for use in the data view.

# AEP sandbox

For more information, see: [Sandboxes overview](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en).

An AEP sandbox:

* Provides a means to partition a single AEP instance into separate virtual environments (dev, test, stage, production, etc.) to help develop and evolve digital experience applications.

An AEP sandbox does not:

* Provide similar functions as a CJA connection or data view.
* Allow you to connect or combine CJA data from different sandboxes.

