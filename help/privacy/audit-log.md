---
title: Audit logs
description: Learn how to view and manage CJA audit logs.
---

# Audit logs

To increase the transparency and visibility of activities performed in the system, Customer Journey Analytics (CJA) allows you to audit user activity for various services and capabilities in the form of "audit logs". These logs form an audit trail that can help with troubleshooting issues, and help your business effectively comply with corporate data stewardship policies and regulatory requirements, such as the Health Insurance Portability and Accountability Act (HIPAA).

In a basic sense, an audit log tells **who** performed **what** action, and **when**. Each action recorded in a log contains metadata that indicates the action type, date and time, the email ID of the user who performed the action, and additional attributes relevant to the action type.

This topic covers audit logs in CJA, including how to view and manage them in the UI.

## Event types captured by audit logs

The following table outlines which actions on which component types are recorded by audit logs:

| Component Type | Actions |
| --- | --- |
| Annotation |<ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul>|
| Audience | <ul><li>API_Request</li><li>Approve</li><li>Create</li><li>Delete</li><li>Edit</li><li>Export</li><li>Refresh</li></ul> |
| Calculated Metric | <ul><li>API_Request</li><li>Approve</li><li>Create</li><li>Delete</li><li>Edit</li><li>Share</li><li>Unapprove</li><li>Unshare</li></ul> |
| Connection | <ul><li>Delete</li><li>Edit</li></ul> |
| Data Group | No actions were listed - Is a data group the same as a dataset? |
| Data View | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li><li>Export</li></ul> |
| Date Range | <ul><li>Approve</li><li>Create</li><li>Delete</li><li>Edit</li><li>Login failed</li><li>Share</li><li>Unapprove</li><li>Unshare</li></ul>  |
| Feature Access | <ul><li>Login_successful</li></ul> How do you define feature access?  |
| Filter | <ul><li>Approve</li><li>Create</li><li>Delete</li><li>Edit</li><li>Share</li><li>Unapprove</li><li>Unshare</li></ul>  |
| IMS Org | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |
| Mobile | <ul><li>Refresh</li></ul> How do you define Mobile? |
| Project | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li><li>Share</li><li>Unshare</li></ul> |
| Report | <ul><li>API_Request</li><li>Transfer</li></ul> |
| Scheduled Project | <ul><li>Approve</li><li>Create</li><li>Delete</li><li>Edit</li><li>Unapprove</li></ul> |
| User | <ul><li>Delete</li><li>Edit</li><li>Share</li><li>Unshare</li></ul> |
| User Group | <ul><li>API_Request</li><li>Create</li><li>Delete</li><li>Edit</li></ul> |

{style="table-layout:auto"}

## Access to audit logs

When the feature is enabled for your organization, audit logs are automatically collected as activity occurs. You do not need to manually enable log collection.

In order to view and export audit logs, you must have been granted the **[!UICONTROL View User Activity Log]** access control permission??? To learn how to manage individual permissions for CJA features, please refer to the [access control documentation](/help/getting-started/cja-access-control.md).

## Manage audit logs in the UI

In CJA, navigate to **[!UICONTROL Tools]** > **[!UICONTROL Audit Logs]**.

### Filter audit logs

Select the funnel icon (![filter](assets/filter-icon.png)) to display a list of filter controls to help narrow results. Only the last 1,000 records are displayed, irrespective of the various filters selected.

![filters](assets/filters.png)

The following filters are available for audit events in the UI:

| Filter | Description |
| --- | --- |
| Date Range |  |
| Action | You can filter on the following actions:  |
| User ID | Filter on a specific user by their user ID. |
| Email | Filter on a specific email address. |
| Component ID |  |
| Component Type | Filter on one or more component types: <ul> |

{style="table-layout:auto"}

