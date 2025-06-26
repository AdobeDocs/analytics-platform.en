---
description: Send an Analysis Workspace project by email or schedule it for delivery.
keywords: Analysis Workspace
title: Send reports to others by email
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
role: User
---
# Send files to others

You can send Customer Journey Analytics reports as files to selected users by email. You can send files ad hoc, or you can configure files to be sent on a schedule. Files can be sent in CSV or PDF format.

Any tags applied to the project are automatically applied to the export.

Other methods of exporting Customer Journey Analytics data are also available, as described in [Export overview](/help/analysis-workspace/export/export-project-overview.md).

![Send file](assets/send-file.png)

## Send file

To send a file to recipients by email:

1. Select **[!UICONTROL Share] > [!UICONTROL Send file]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Use **[!UICONTROL Description]** to add a description to include in the email. 
1. Add recipients or groups. You can also enter email addresses. 
1. (Only for Healthcare Shield customers) Provide a password to [password-protect a scheduled report](#password-protect-a-new-scheduled-project).
1. (Optional) Select **[!UICONTROL Show scheduling options]** to [schedule a file export](#schedule-file-export).
1. Click **[!UICONTROL Send Now]**. Select **[!UICONTROL Cancel]** to cancel.


## Schedule file export {#schedule}

To send a file on a schedule to recipients by email

1. Select **[!UICONTROL Share] > [!UICONTROL Schedule file export]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Use **[!UICONTROL Description]** to add a description to include in the email. 
1. Add recipients or groups. You can also enter email addresses. 
1. (Only for Healthcare Shield customers) Provide a password to [password-protect a scheduled report](#password-protect-a-new-scheduled-project).
1. Ensure **[!UICONTROL Show scheduling options]**  is selected.
1. Select a **[!UICONTROL Frequency]**. You can select between:

   | Frequency | Options |
   |---|---|
   | **[!UICONTROL Send hourly]** | Enter a value for **[!UICONTROL Send every number of hours]**. |
   | **[!UICONTROL Send daily]** | Select a **[!UICONTROL Daily frequency]**: **[!UICONTROL Send every day]**, **[!UICONTROL Send every weekday]**, or **[!UICONTROL Custom frequency]**.<br/>If you select **[!UICONTROL Custom frequency]**, enter a value for **[!UICONTROL Send every number of days]**. |
   | **[!UICONTROL Send weekly]** | Enter a value for **[!UICONTROL Send every number of weeks]**. And select a **[!UICONTROL Day of week]**. |
   | **[!UICONTROL Send monthly by day of the week]** | Select a **[!UICONTROL Day of week]** and a **[!UICONTROL Week of month]**. |
   | **[!UICONTROL Send monthly by day of the month]** | Select a value from **[!UICONTROL Send on this day of the month]**. |
   | **[!UICONTROL Send yearly by day of the month]** | Select a **[!UICONTROL Day of week]**, select a **[!UICONTROL Week of month]**, and select a **[!UICONTROL Monthly of year]**. |
   | **[!UICONTROL Send yearly by specific date]** | Select a **[!UICONTROL Month of year]** and select a value from **[!UICONTROL Send on this day of the month]**. |

1. Enter a start date in **[!UICONTROL Starting on]**. Alternatively, select ![Calendar](/help/assets/icons/Calendar.svg) to pick a start date from the calendar.
   
1. Enter an end date in **[!UICONTROL Ending on]**. Alternatively, select ![Calendar](/help/assets/icons/Calendar.svg) to pick an end date from the calendar.
1. Select **[!UICONTROL Send on schedule]**. Select **[!UICONTROL Cancel]** to cancel.


## Password-protect a scheduled project {#password}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_sendfile_password"
>title="Password encryption"
>abstract="The supplied password will be used to encrypt the file for the scheduled project. The security requirements for your organization require password encryption."

<!-- markdownlint-enable MD034 -->


>[!NOTE]
>
>The option to password-protect a scheduled project appears only for Customer Journey Analytics customers who have purchased the [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html) add-on product. 

Adobe uses the password to encrypt scheduled projects, whether they are sent in .pdf or .csv formats.

After your company has purchased the Healthcare Shield SKU and has been enabled for it, the prompt to create a password for a scheduled project is displayed in the following circumstances:

* When someone creates a new scheduled project.

* When an existing scheduled project is about to be sent. The currently scheduled project is disabled until password protection is in place. The owner of the scheduled project receives an email informing them of this requirement. 

### Password requirements

The password requirements conform to the Adobe standards, requiring a minimum of 8 characters with at least one number and one special character. 

### Password-protect a new scheduled project

1. After you save your project, go to **[!UICONTROL Share]** > **[!UICONTROL Send file now]**, or **[!UICONTROL Share]** > **[!UICONTROL Send file on schedule]**.
1. Follow the instructions above, under [Send file now](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#now) or [Send file on schedule](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#schedule).

### Password-protect an existing scheduled project 

When you password-protect an existing scheduled project, the project owner receives an email similar to this:

![The Customer Journey Analytics email notification indicating password encryption is required for your organization.](assets/email-password.png)

1. Log in to Customer Journey Analytics.
1. Select **[!UICONTROL View Scheduled Project]**.
1. In the **[!UICONTROL Edit scheduled project]** dialog, enter and re-enter a password.
1. Let the recipients of the scheduled project know about this password. Do not distribute the password to people who are not recipients of the scheduled project.



## Scheduled Projects manager {#manager}

Scheduled Analysis Workspace projects can be managed from the main interface, using **[!UICONTROL Components]** > **[!UICONTROL Scheduled Projects]**. For more information, see [Scheduled projects](/help/components/scheduled-projects-manager.md).
