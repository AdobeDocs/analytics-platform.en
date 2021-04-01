---
title: What is dimension persistence in Customer Journey Analytics?
description: Dimension persistence is a combination of allocation and expiration. Together, they determine what dimension values persist.
---

# Persistence

Dimension persistence is a combination of allocation and expiration. Together, they determine what dimension values persist. Adobe highly recommends that you discuss within your organization how multiple values for each dimension are handled (allocation) and when dimension values stop persisting data (expiration).

* By default, a dimension value uses last allocation. New values overwrite persisted values.
* By default, a dimension value uses an expiration of [!UICONTROL Session].

## Allocation

Determines how CJA assigns credit for a success event if a variable receives multiple values before the event. Supported values include:

* Most Recent: The last eVar value always receives credit for success events until that eVar expires.
* Original Value: The first eVar always receives credit for success events until that eVar expires.
* Instance: ??

Note: Switching allocation to or from Linear prevents historical data from displaying. Mixing allocation types in the reporting interface can lead to misstated data in reports. For example, Linear allocation might divide revenue across a number of different eVar values. After changing back to Most Recent allocation, 100% of that revenue would be associated with the most recent single value. This association can lead to incorrect conclusions by users.

To avoid the likelihood of confusion in reporting, Analytics makes the historical data unavailable to the interface. It can be viewed if you decide to change the given eVar back to the initial allocation setting, although you should not change eVar allocation settings simply to access the historical data. Adobe recommends using a new eVar when new allocation settings are desired for data already being recorded, rather than changing allocation settings on an eVar that already has a significant amount of historical data built up.

## Expiration

Dimension values expire after the time period that you specify. After the dimension value expires, it no longer receives credit for a metric. Dimensions can also be configured to expire on metrics. For example, if you have an internal promotion that expires at the end of a visit, the internal promotion receives credit only for purchases or registrations that occur during the visit in which they were activated.

There are two ways to expire an eVar:

You can set the eVar to expire after a specified time period or event.
You can use force the expiration of an eVar by resetting it, which is useful when repurposing a variable.
For example, if you change the expiration of an eVar from 30 to 90 days, eVar values collected will continue to persist for the duration of the new expiration set (in this case, 90 days). The system simply looks at the current expiration setting and the last set timestamp of the eVar value collected to determine expiration. Only the Reset option expires values and does so immediately.

Another example: If an eVar is used in May to reflect internal promotions and expires after 21 days, and in June it is used to capture internal search keywords, then on June 1, you should force the expiration of, or reset, the variable. Doing so will help keep internal promotion values out of June’s reports.