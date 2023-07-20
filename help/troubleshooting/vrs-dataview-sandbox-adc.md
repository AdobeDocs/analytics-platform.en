# Virtual Report Suites, Data Views, Adobe Experience Platform Sandboxes and the Analytics source connector

Adobe provides a variety of means to create virtual reporting environments and sandbox environments. It is useful to understand the similarities and differences between the following features and how these features relate to the [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en):

* Adobe Analytics virtual report suites
* Customer Journey Analytics data views
* Adobe Experience Platform sandboxes

## Adobe Analytics Virtual Report Suites (VRS)

For more information, see: [Virtual report suites overview](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=en).

A VRS:

* Can be based on Adobe Analytics segments.
* Can be applied to both historical and new data in a non-destructive manner.
* Allows you to create one or many virtual views on top of an Adobe Analytics report suite for use by different business teams.
* May be used to control access to and curate different kinds of data for different users in Adobe Analytics.
* Provides optional [report-time processing](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=en) capabilities for Adobe Analytics. In this case, a VRS may be used to create a custom definition for "visit".
* Is applied at report runtime, similar to segment evaluation. This is _after_ the data has been collected and stored within Adobe Analytics.
* Is required for [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=en) in Adobe Analytics.
* Has available the same number of variables for use as a standard Analytics Report Suite (250 eVars, 250 props, 1000 events), although VRS curation can limit which variables are exposed to users.
* Supports custom calendar options.

A virtual report suite is (does) not:

* Provide a means to combine report suites together.
* Available in Adobe Analytics Data Warehouse.
* Available as a source for dataflows into Adobe Experience Platform via the Analytics source connector. Only full (non-virtual) report suites are available for use with the Analytics source connector.


## Customer Journey Analytics data views

For more information, see: [Data views overview](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en).

A data view:

* Can be based on Customer Journey Analytics filters.
* Can applied to both historical and new data in a non-destructive manner.
* Allows you to create one or many virtual views on top of a Customer Journey Analytics connection for use by different business teams.
* May be used to control access to and curate different kinds of data for different users in Customer Journey Analytics.
* Provides powerful non-destructive options for transforming and enhancing data coming into Customer Journey Analytics through a Customer Journey Analytics connection.
* Is based on the report-time processing capabilities of Customer Journey Analytics.
* Allows users to create a custom definition for "session."
* Is applied at report runtime, similar to filter evaluation. This is _after_ the Source Connector (Adobe Analytics or other) has written data to a dataset in the Adobe Experience Platform data lake, and _after_ the data has been ingested into Customer Journey Analytics via a Customer Journey Analytics connection.
* Allows for an unlimited number of variables, although curation can limit which variables are exposed to users
* Allows for custom naming of Event, Session & Person containers.
* Supports custom calendar options.

A data view does not:

* Directly provide a means for combining report suites or other datasets. Instead, datasets are combined with in a Customer Journey Analytics connection. The combined data from the Customer Journey Analytics connection is available for use in all data views based on that connection.

## Adobe Experience Platform sandboxes

For more information, see: [Sandboxes overview](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en).

An Adobe Experience Platform sandbox:

* Provides a means to partition a single Adobe Experience Platform instance into separate virtual environments (dev, test, stage, production, etc.) to help develop and evolve digital experience applications.
* Can be thought of as a container which holds all the data and applications for a given environment.

An Adobe Experience Platform sandbox does not:

* Provide similar functions as virtual report suites, Customer Journey Analytics connections or data views.
* On its own combine report suites with or without other datasets. However, the datasets within a sandbox can be combined within a Customer Journey Analytics connection.

Further:

* Data from different sandboxes cannot be combined within Customer Journey Analytics.
* The Analytics Source connector sends report suite data _into_ a specific sandbox. Each report suite may be configured as a source for a single sandbox. See the [Analytics source connector documentation](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) for more details.