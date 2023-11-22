---
description: Send an Analysis Workspace project by email or schedule it for delivery.
keywords: Analysis Workspace
title: Send Customer Journey Analytics data to others by email
feature: Curate and Share
mini-toc-levels: 3
exl-id: 36b5133a-2cd3-4cf1-a6fa-93a02dba276a
---
# Send Customer Journey Analytics data to others through email

You can export Customer Journey Analytics reports by sending it to selected recipients through email. You can send files ad hoc, or you can configure files to be sent on a schedule. Files can be sent in CSV or PDF format.

Any tags applied to the project are automatically applied to the export.

Other methods of exporting Customer Journey Analytics data are also available, as described in [Export overview](/help/analysis-workspace/export/export-project-overview.md).

## Send file now {#now}

To send a file immediately to recipients by email:

1. Click **[!UICONTROL Share] > [!UICONTROL Export file]**.
1. Specify the file type:
   * [!UICONTROL **CSV**]: Choose this option if you want plain-text data.
   * [!UICONTROL **PDF**]: Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.
1. (Optional) Add a description to include in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. (Only for Healthcare Shield customers) Provide a password. See the section Password-protect a scheduled report.
1. (Optional) Click **[!UICONTROL Show scheduling options]** to specify a delivery schedule.
1. Click **[!UICONTROL Send Now]**.

![The Send file window and Send now button.](assets/send-file-no-scheduling-options.JPG)

## Send file on schedule {#schedule}

To send a file on a recurring schedule to recipients by email:

1. Click **[!UICONTROL Share] > [!UICONTROL Schedule file export]**.
1. Specify the file type (CSV or PDF).
1. (Optional) Add a description that will be included in the email to explain the file being received. 
1. Add recipients or groups. Email addresses can also be entered. 
1. (Only for Healthcare Shield customers) Provide a password. See the section Password-protect a scheduled report. 
1. Specify the range the schedule should be delivered over by modifying Starting on and Ending on inputs. The end date must be within a year from the day the schedule is created or modified.
1. Specify the delivery frequency. Each frequency allows for different customizations. 
1. Click **[!UICONTROL Send on schedule]**.

![The Send file window and scheduling options displayed to show the Starting on, Ending on dates, and the daily frequency settings.](assets/send-file.JPG)

## Scheduled Projects manager {#manager}

Scheduled Analysis Workspace projects can be managed under **[!UICONTROL Analytics] > [!UICONTROL Components] > [!UICONTROL Scheduled Projects]**.

In the Scheduled Projects Manager, you can edit and delete recurring project schedules. Search for a schedule in the search bar or by using the filter options in the left rail. You can filter by tag, approved schedules, owners and more.

| Field | Description |
| --- | --- |
| [!UICONTROL Favorites] | Selecting the star icon makes this schedule a favorite. |
| [!UICONTROL Schedule ID] | This ID is used mainly for debugging purposes. |
| [!UICONTROL Title and Description] | Title and description of this project. |
| [!UICONTROL Owner] | The person who created and owns the project. |
| [!UICONTROL Tags] | (optional) Tagging is a good way to organize projects. All users can create tags and apply one or more tags to a project. However, you can see tags only for those projects that you own or that have been shared with you.  |
| [!UICONTROL Delivered To] | The recipient(s) of this scheduled project. |
| [!UICONTROL Expiration Date] | You can set the expiration date to up to one year, regardless of schedule frequency. |
| [!UICONTROL Frequency] | How often you want to have this schedule project sent to the recipient(s). |
| [!UICONTROL Execution Time] | At what time of day this scheduled project gets sent. |
| [!UICONTROL Number of Queries] | The number of queries against this project. | 

The following are common actions in the Scheduled Projects manager:

|Action|Description|
|---|---|
|**[!UICONTROL Edit schedule]**|Click the title of the schedule to update its delivery settings.|
|**[!UICONTROL Delete schedule]**|Select the scheduled project in the list and then click Delete from the menu. This will delete the selected schedule for the project; the project itself will not be deleted.|
|**[!UICONTROL Add tags]**|Select the scheduled project in the list and then choose "Tag" or "Approve" to organize your schedules and make them easier to search for.|
|**[!UICONTROL View failed schedules]**|Navigate to the left rail > Other filters > Failed to see schedules that have failed.|
|**[!UICONTROL View expired schedules]**|Navigate to the left rail > Other filters > Expired to see schedules that have expired. Click the title of the schedule to setup a new delivery schedule.|
|**[!UICONTROL View schedule ID]**|Navigate to column options in the top right and add the Schedule ID column to the table. The scheduled ID is often useful for debugging.|

The Scheduled Projects Manager shows the items that a specific user has created. If the user account is disabled in the application, all scheduled deliveries stop.
For more information, see [Scheduled projects](/help/components/scheduled-projects-manager.md).

## Password-protect a scheduled project {#password}

>[!NOTE]
>
>The option to password-protect a scheduled project appears only for Customer Journey Analytics customers who have purchased the [Healthcare Shield](https://business.adobe.com/solutions/industries/healthcare.html) add-on product. 

Adobe uses the password to encrypt scheduled projects, whether they are sent in .pdf or .csv formats.

After your company has purchased the Healthcare Shield SKU and has been enabled for it, the prompt to create a password for a scheduled project is displayed in the following circumstances:

* When someone creates a new scheduled project.

* When an existing scheduled project is about to be sent. The currently scheduled project is disabled until password protection is in place. The owner of the scheduled project receives an email informing them of this requirement. 

![The Edit scheduled project window and password encryption notification indicating your organization requires password encryption.](assets/password.png)

### Password requirements

The password requirements conform to the Adobe standards, requiring a minimum of 8 characters with at least one number and one special character. 

### Password-protect a new scheduled project

1. After you save your project, go to **[!UICONTROL Share]** > **[!UICONTROL Send file now]**, or **[!UICONTROL Share]** > **[!UICONTROL Send file on schedule]**.
1. Follow the instructions above, under [Send file now](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#now) or [Send file on schedule](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/t-schedule-report.html#schedule).

### Password-protect an existing scheduled project 

Before a project is scheduled, the project owner receives an email similar to this:

![The Customer Journey Analytics email notification indicating password encryption is required for your organization.](assets/email-password.png)

1. Log in to Customer Journey Analytics.
1. Select **[!UICONTROL View Scheduled Project]**.
1. In the **[!UICONTROL Edit scheduled project]** dialog, enter and re-enter a password.
1. Let the recipients of the scheduled project know about this password. Do not distribute the password to people who are not recipients of the scheduled project.
