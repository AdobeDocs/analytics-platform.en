---
title: Regional Data Collection
description: Information on Regional Data Collection
feature: Regional Data Collection
---
# Regional Data Collection

The Adobe Experience Cloud uses Regional Data Collection (RDC) so that interactions between your visitors and Adobe and non-Adbobe solutions occur as close to your visitors as possible. Once data is collected regionally at a Data Collection Center (DCC, also known as Edge site, part of the Platform Edge Network), it is forwarded over a secure connection to the relevant solutions based on the configuration of your datastream and/or event forwarding.

![Data flow using Edge Networks](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png?lang=en)

The regional data collection process uses the following steps:

1. DNS automatically resolves the collection hostname to the IP address of the Data Collection Center nearest to the visitor.
1. The visitor sends the data to that location.
1. The data is immediately forwarded over a secure connection to the solutuons defined by the datastream or event forwarding configuration.

Using regional data collection provides several benefits:

* **Performance**: With RDC, your visitors connect to the closest DCC. This optimization provides the fastest response time, resulting in more accurate tracking and faster loading times.
* **Redundancy**: If there is a disruption in communication between the DCC and your DPC, Adobe's RDC infrastructure saves data locally, then forwards it to the DPC when communications are restored.

RDC currently includes the following locations (subject to change):


| RDC Type | Data Collection Centers |
| --- | --- |
| Global (Default) | Oregon, Virginia, Ireland, Paris, Mumbai, Singapore, Tokyo, Sydney |
| Americas Only | Oregon, Virginia |
| Europe Only | Ireland, Paris |
| Asia Pacific Only | Mumbai, Singapore, Tokyo, Sydney |

{style="table-layout:auto"}

See [Data collection overview](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html?lang=en) for more information about the process of data collection beyond the Experience Edge network and its regional data centers.

