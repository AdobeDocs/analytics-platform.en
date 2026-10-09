---
title: Brand Visibility Inbound Integration Configuration
description: Learn how to configure the integration of Brand Visibility with Customer Journey Analytics
feature: Experience Platform Integration
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
---
# Setup and configure inbound integration

This article details the [prerequisites](#prerequisites), [responsibilities](#responsibilities), [steps to verify](#verification), [troubleshoot steps](#troubleshoot), and [completion criteria](#completion-criteria) for setting up and configuring the Brand Visibility inbound integration with Customer Journey Analytics.

## Prerequisites

Consider the following prerequisites before enabling the inbound integration. And use the verification procedure to verify 

### BYOCDN log forwarding

CDN access logs must be forwarded to and received by Adobe Brand Visibility for each Brand Visibility site before the Brand Visibility source connector can be viable.

This requirement applies for each Brand Visibility site. A CDN configuration or log feed for one site, domain, or subdomain covers only that site unless Adobe confirms that coverage for another site.

Verify with Adobe both parts of the handoff:

1. You have configured the relevant CDN or log pipeline to forward the required access logs to the Adobe-provided Amazon S3 destination.
1. Adobe has confirmed that logs are being received and detected for the relevant site.

BYOCDN Log Forwarding provides the server-side CDN request data used for automated-agent traffic analysis. The data does not depend on JavaScript tags running in a browser. The required
CDN log feed ensures the downstream summary dataset contains the intended Brand Visibility agentic-traffic data. See the [BYOCDN log forwarding reference](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview) for more information.

### Required information

Ensure you have values for all required details listed in the table below for each Brand Visibility site.

| Required value | Verification or notes |
|---|---|
| Brand Visibility site or domain | Confirm the site covered by CDN log forwarding. |
| CDN provider | Identify the CDN that serves the site. |
| CDN log forwarding status | Proof that logs for the site are forwarded and detected by the Brand Visibility. |
| Brand Visibility readiness confirmation | Confirm with Adobe account team the readiness before you enable and schedule the connector. |
| IMS organization | Use the exact IMS organization associated with Brand Visibility, Experience Platform. |
| Sandbox | Use the exact sandbox name that is designated for the inbound integration. |
| Connection | Identify the Customer Journey connection that should include the dataset. |
| Data view | Identify a new or existing Customer Journey Analytics data view that should include the components. |  
| Administrator or owner | Provide name or team that is the configuration contact. |

Before Adobe schedules the managed connector, your Adobe account team must confirm that the site is ready for the inbound integration. Delivery communications refer to this as Brand Visibility approval or site readiness confirmation. Scheduling the managed connector is a managed-service requirement, not a customer self-service action.

### Sandbox

The managed connector must create the dataset in the specific named AEP sandbox designated by the customer within the IMS Organization. 

Confirm the following:

* IMS Organization
* Target Experience Platform sandbox

The target AEP sandbox is the same named sandbox used by the corresponding Customer Journey Analytics connection or connections that include the dataset. 

The customer can add the dataset to the appropriate CJA Connection only after Adobe confirms that the managed dataset has been created.

### Summary dataset

The inbound integration provides an aggregated summary dataset in Experience Platform that contains server-side CDN request information associated with LLM, bot, and automated-agent
traffic.

Brand Visibility uses CDN access logs to identify requests from bots and automated agents. This traffic does not fire browser JavaScript tags and therefore is not captured through a conventional web analytics implementation.

For the detailed description of the inbound integration, dataset structure, and available fields, see [about the dataset](#about-the-dataset).

The managed connector creates the summary dataset in Experience Platform using:

* The **[!UICONTROL XDM Summary Metrics]** class
* The **[!UICONTROL CDN Requests Summary]** field group
* Fields organized under a **[!UICONTROL cdn]** object

The connector creates the dataset for each Brand Visibility site, using the following naming pattern: <code>Adobe Brand Visibility (ABV) Dataset - _baseUrl without scheme_</code>. <br/>For example `Adobe Brand Visibility (ABV) Dataset - example.com` for the site <https://example.com>.

Datasets created before this naming convention was adopted display the earlier pattern <code>LLM Optimization (LLMO) Dataset - _baseUrl without scheme_</code>. 
In all cases, customers need to confirm the exact dataset name or dataset ID with their Adobe account team after creation.

The dataset is aggregated summary data. When analyzing request volume in Customer Journey Analytics, use the provided **[!UICONTROL CDN Request Count]** metric rather than counting dataset rows. 

Verify the available fields in the dataset schema created for the specific Brand Visibility site. To plan the configuration of the data view, review the fields.

## Responsibilities

Adobe manages the inbound connector and, after prerequisites are confirmed:

* Enables the managed ABV → AEP connector.
* Creates the summary dataset for each configured ABV site.
* Lands the dataset in the customer-provided AEP sandbox.
* Provides the customer with the dataset name or dataset ID for verification.

Your responsibilities as a customer are:

* To ensure  that CDN logs are forwarded to and received by Brand Visibility for each Brand Visibility site.
* To provide the correct IMS organization and named Experience Platform sandbox.
* To select the Customer Journey Analytics connection that should include the dataset.
* To add the dataset to that connection.
* To select the fields to expose as components in the relevant Customer Journey Analytics data view.
* To validate that the resulting dimensions and metrics support the intended analysis.

>[!IMPORTANT]
>
>The managed connector intentionally stops after creating and populating the Experience Platform dataset. Adobe does not modify your Customer Journey Analytics connections or data views.

The dataset is not available for Customer Journey Analytics analysis until you add the dataset to a connection. The data
is not available to users through a data view until the relevant fields have been added to that data view.

## Verification

Use the following procedure to verify the inbound integration:

1. Confirm ABV site and CDN-log readiness

   For each ABV site:

   * Confirm the exact site or domain covered by the request.
   * Confirm the CDN provider.
   * Confirm that the CDN or log pipeline is forwarding the required access logs.
   * Confirm that Brand Visibility is receiving or detecting logs for that site.
   * Obtain from Adobe the site's Brand Visibility readiness confirmation.

   Do not proceed using a general statement that "CDN logs are enabled" unless the confirmation covers the specific ABV site.

1. Verify the managed dataset in Experience Platform

   After Adobe confirms that the managed connector has created the dataset:
   1. Login to **[!UICONTROL Experience Platform]**.
   1. Select the named sandbox supplied during intake from the list of sandboxes.
   1. Locate the dataset name or dataset ID supplied by Adobe in **[!UICONTROL Datasets]**.
   1. Confirm that the dataset is associated with the expected Brand Visibility site.
   1. Record the **[!UICONTROL Dataset ID]** and linked **[!UICONTROL Schema]**.
   1. Review the dataset record count, latest ingestion information, and available sample data where permitted.
   1. Open the linked schema and verify the expected XDM structure:
      * Class: **[!UICONTROL XDM Summary Metrics]**
      * Field group: **[!UICONTROL CDN Requests Summary]**
      * Object: **[!UICONTROL cdn]**
      * Expected dimensions and metrics, such as **[!UICONTROL botType]**, **[!UICONTROL cdnProvider]**, **[!UICONTROL url]**, **[!UICONTROL host]**, **[!UICONTROL status]**, **[!UICONTROL requests]**, and **[!UICONTROL timeToFirstByte]**.

1. Add the dataset to a connection

   Your Customer Journey Analytics administrator must add the managed dataset to the intended Connection:
   
   1. Login to Customer Journey Analytics.
   1. [Create a new connection or edit the intended existing connection](/help/connections/create-connection.md). Confirm that the connection uses the same Experience Platform sandbox in which the managed dataset was created.
   1. Search for the dataset using the Adobe-provided dataset name or dataset ID.
   1. Add the dataset to the connection.
   1. Configure the dataset settings according to the customer's Customer Journey Analytics design.
   1. Save the connection.
   1. To confirm that the dataset is included and that ingestion is progressing, review the connection details.

1. Configure or update the data view

   After the dataset is part of the Connection:
   1. Login to Customer Journey Analytics.
   1. [Create a new data view or edit the data view](/help/data-views/create-dataview.md) associated with the intended reporting use case.
   1. Select the connection that contains the managed Brand Visibility dataset.
   1. Add the required schema fields as dimensions or metrics.
   1. Include the fields needed for the planned analysis, such as:
      * **[!UICONTROL Bot Type]**
      * **[!UICONTROL CDN Provider]**
      * **[!UICONTROL URL]**
      * **[!UICONTROL Host]**
      * **[!UICONTROL HTTP Status]**
      * **[!UICONTROL Request Count]**
      * **[!UICONTROL Time to First Byte]**
   1. Save the data view.
   1. Validate the fields in Analysis Workspace or the customer's selected reporting workflow.

1. Validate the end-to-end result
   
   Use a recent reporting period and verify that:

   * The expected Brand Visibility site is represented.
   * The expected CDN provider and host values are present.
   * Bot or automated-agent traffic is represented.
   * URL and HTTP-status dimensions contain expected values.
   * The CDN Request Count and performance metrics are available.
   * The dataset is included in the intended connection.
   * The required fields are exposed in the intended data view.

  The exact time required for data to become available depends on the managed ingestion and Customer Journey Analytics processing workflow. Your Adobe account team should provide any applicable processing expectations for your request.

## Troubleshoot

See below what to do if issues occur:

* The dataset does not appear in AEP.

  Verify that:

  * The IMS organization is correct.
  * The selected Experience Platform sandbox is correct.
  * Adobe has confirmed that the managed connector was enabled.
  * The dataset name or ID supplied by Adobe was used.
  * The dataset was created for the correct Brand Visibility site.

* The dataset exists but contains no expected data.

  Verify that: 
  * CDN logs are being forwarded for the exact Brand Visibility site.
  * ABV has confirmed that logs are being received or detected.
  * The site or domain in the CDN configuration matches the Brand Visibility site.
  * The managed connector was enabled after CDN log readiness was confirmed.
  * The selected date range includes the period after log ingestion began.


* The dataset exists in Experience Platform but is unavailable in Customer Journey Analytics.
  
  Verify that:
  * The Customer Journey Analytics connection uses the same named Experience Platform sandbox.
  * The dataset was explicitly added to the connection.
  * The Customer Journey Analytics administrator has the required permissions.
  * The connection has been saved after the dataset was added.

* The dataset is in the connection but fields are not available for reporting.

  Verify that:
  * The data view selects the correct Customer Journey Analytics connection.
  * The expected schema fields were added as data view components.
  * The fields were placed in the intended **[!UICONTROL Dimensions]** or **[!UICONTROL Metrics]** section.
  * The data view was saved after the components were added.
  * The dataset schema matches the expected **[!UICONTROL CDN Requests Summary]** field group structure.


## Completion criteria


The inbound integration is ready for customer-side Customer Journey Analytics configuration when all of the following are confirmed:

* CDN logs are forwarded to and received by Brand Visibility for each requested ABV site.
* Adobe has confirmed site readiness for the managed connector.
* The IMS organization has been provided.
* The exact target Experience Platform sandbox has been provided.
* Adobe has created the per-site summary dataset in that sandbox.
* You verified the dataset and its XDM schema.
* You added the dataset to the intended CJA Connection.
* You configured the relevant CJA Data View components.

