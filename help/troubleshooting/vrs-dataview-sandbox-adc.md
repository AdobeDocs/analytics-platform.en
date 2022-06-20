# How Adobe Analytics virtual report suites, CJA data views, AEP sandboxes and the Analytics Source Connector

# Overview
Adobe Analytics, CJA and AEP provide a variety of means to create virtual environments. The discussion below compares Adobe Analytics virtual report suites, CJA data views, and AEP sandboxes.

#. Adobe Analytics Virtual Report Suite (VRS)
For more information, see: Virtual report suites overview.

A virtual report suite:

Can be based on Adobe Analytics segments.
Configuration can be applied to historical data.
Allows you to create one or many virtual views on top of a report suite for for use by different users in Adobe Analytics.
May be used to control access to and curate different kinds of data for different users.
Provides optional report-time processing capabilities for Adobe Analytics.
Is required for Cross-Device Analytics in Adobe Analytics.
A virtual report suite does note:

Provide a means to combine report suites together.

## VRS and the Analytics Source Connector

See PLATIR-21499 - Not able to find Virtual Adobe Analytics report in AEP Adobe Analytics Sources CLOSED

#. CJA data view
For more information, see: Data views overview.

A data view:

Can be based on CJA filters.
Configuration can be applied to historical data.
Allows you to create one or many virtual views on top of a CJA connection for use by different users in Customer Journey Analytics.
May be used to control access to and curate different kinds of data for different users.
Provides powerful non-destructive options for transforming and enhancing data coming into CJA through a CJA connection.
Is based on the report-time processing capabilities of CJA.
A data views does not:

Directly provide a means for combining report suites or other datasets. However, because a data view sits on top of a CJA connection, and a connection may be used to combine multiple report suites and AEP datasets, the combined data is available for use in the data view.

# AEP sandbox
For more information, see: Sandboxes overview.

An AEP sandbox:

Provides a means to partition a single AEP instance into separate virtual environments (dev, test, stage, production, etc.) to help develop and evolve digital experience applications.
An AEP sandbox does not:

Provide similar functions as a CJA connection or data view.
Allow you to connect or combine CJA data from different sandboxes.

