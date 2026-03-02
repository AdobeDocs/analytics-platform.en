---
description: Explains the features of the new landing page.
title: Customer Journey Analytics landing page
role: User, Admin
feature: Basics
exl-id: 65c7bc26-7160-4bba-b764-5b0fa8686fca
---
# Customer Journey Analytics landing page

The landing page for Customer Journey Analytics highlights [!DNL Analysis Workspace] and features a project manager home page and a learning section to help you manage customer journey data more effectively.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Landing page in Analysis Workspace](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/cja-basics/customer-journey-analytics-landing-page){target="_blank"} for a demo video.

{{videoaa}}

>[!ENDSHADEBOX]


The Customer Journey Analytics landing page is comprised of the following subtabs: Projects and Learning.

**[!UICONTROL Projects]** are customized designs that combine data components, tables, and visualizations that you built or that someone else built and shared with you. [!UICONTROL Projects] also refers to blank projects and blank mobile scorecards.

The **[!UICONTROL Learning]** tab contains hands-on video tours, tutorials, and links to documentation.

>[!BEGINTABS]

>[!TAB Projects] 

![Projects landing page](assets/landing-projects.png)

>[!TAB Learning]

![Learning landing page](assets/landing-learning.png)


>[!ENDTABS]

## Projects

[!UICONTROL Projects] serves as the [!UICONTROL Workspace] home page. The **[!UICONTROL Projects]** tab displays the Company folder, any personal folders you created, your Workspace projects, and Mobile scorecards. Use this page to view, create, and modify folders, projects, and mobile scorecards. See [Projects](/help/analysis-workspace/build-workspace-project/freeform-overview.md) for more information.


**[!UICONTROL Projects]** are customized designs that combine data components, tables, and visualizations that you built or that someone else built and shared with you. [!UICONTROL Projects] also refers to blank projects and blank mobile scorecards.

>[!NOTE]
>
>Several of the following settings persist during the session and across sessions. For example, the tab you selected, the selected segments, selected columns, and the column sort direction. Search results are not persistent.

See [Projects](/help/analysis-workspace/build-workspace-project/freeform-overview.md) for more information.

<!--

### Customize table columns

To customize column widths, drag the vertical bar that separates each column. 

To add or remove columns from the list of projects, click the column icon (![Landing all](assets/select-column.png) ) in the top-right, then select or deselect column titles. 

The available columns are:

| Column name | Description |
|---------|----------|
| [!UICONTROL **Name**] | Identifies the name of the project. |
| [!UICONTROL **Type**] | Indicates whether this type is a Workspace project, a Mobile scorecard, or a folder. |
| [!UICONTROL **Tags**] | Tags projects to organize them into groups. |
| [!UICONTROL **Scheduled**] | Set to [!UICONTROL On] when a project is scheduled or [!UICONTROL Off] when it is not. Clicking the [!UICONTROL On] link lets you see information about the scheduled project. You can also [edit the project schedule](/help/analysis-workspace/export/t-schedule-report.md) if you are the project owner. |
| [!UICONTROL **Project role**] | Identifies the project roles: whether you are the project Owner and whether you have permissions to Edit or Duplicate the project. |
| [!UICONTROL **Report suite**] | Identifies the Report Suites that are associated with the project.<br>Tables and visualizations within a panel derive data from the report suite selected in the top right of the panel. The report suite also determines what components are available in the left rail. Within a project, you can use one or many report suites depending on your analysis use cases. The list of report suites is sorted on relevance. Adobe defines relevance based on how recently and frequently the suite has been used by the current user, and how frequently the suite is used within the organization. |
| [!UICONTROL **Owner**] | Identifies the person who created the project. |
| [!UICONTROL **Shared With**] | Shows who the project is currently shared with. |
| [!UICONTROL **Last Modified**] | The date and time when the project was last modified. |
| [!UICONTROL **Last Opened**] | Identifies the date that a project was last opened by the user who is currently viewing the Projects page. |
| [!UICONTROL **Last Used**] | Helps determine whether a project is valuable to users in your organization by showing the date and time when the project was last opened by any user within the organization.<p>Consider the following when viewing this column:</p><ul><li>Usage information is available starting in September 2023.</li><li>This column is available only to system administrators.</li></ul> |
| [!UICONTROL **Project ID**] | Can be used for debugging projects. |
| [!UICONTROL **Longest Date Range**] | Longer date ranges increase project complexity and may increase processing and load times. |
| [!UICONTROL **Number of queries**] | The total number of requests made to Analytics when the project loads. A higher number of project queries increases project complexity and may increase processing and load times. This data is available only after a project has loaded or a scheduled project was sent. |
| [!UICONTROL **Location**] | Shows the folder where the project is located. |

### Other UI elements on the Projects page

| UI element | Definition |
| --- | --- |
| Edit preferences | Lets you [!UICONTROL View Tutorials], and [Edit user preferences](/help/analysis-workspace/user-preferences.md). |
| [!UICONTROL Create new] | Opens the project modal where you can create a Workspace project or a Mobile scorecard or open a company template.  |
| [!UICONTROL Show less<br> Show more] | Toggles between not showing and showing the banner: ![Top banner](assets/top-banner.png) |
| [!UICONTROL Workspace project] | Creates a blank [Workspace project](/help/analysis-workspace/home.md) for you to  design and build. |
| [!UICONTROL Mobile scorecard] | Creates a blank [mobile scorecard](https://experienceleague.adobe.com/docs/analytics/analyze/mobapp/curator.html) for you to design and build. |
| [!UICONTROL Open Training Tutorial] | Opens the Workspace training tutorial that guides you through the process of building a new starter project in a step-by-step tutorial.|
| [!UICONTROL Open release notes] | Opens the Adobe Analytics section of the latest Adobe Experience Cloud release notes. |
| Filter icon | Filters by tags, report suites, owners, types, and other filters (Mine, Shared with me, Favorites, and Approved)  |
| Search bar | Searches all columns in the table. |
| Selection box | Selects one or more projects to display the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| [!UICONTROL Favorites] | Adds a star next to a favorite project or folder that can be used as a filter. |
| [!UICONTROL Name] | Identifies the name of the project. |
| Pin icon | Pins items so they always appear at the top of your list but you can re-adjust the order by moving them up or down in the order. Use the ellipsis option menu and select **Move Up** or **Move down** in the list. |
| Info (i) icon | Displays the following information about a project: Type, Project Role, Owner, Description, and who it is shared with. It also indicates who can [edit or duplicate](/help/analysis-workspace/curate-share/share-projects.md) this project. |
| Ellipsis (...) | Displays the project management actions you can perform: **Delete**, **Share**, **Rename**, **Copy**, **Unpin**, **Move Up**, **Move Down**, **Tag**, **Approve**, **Export CSV**, and **Move to**. You may not have permissions to perform all listed actions. |
| SHOW: Folders & Projects or All Projects | Changes the view setting on the table to show folders and projects according to your folder organization **or** show all of your projects in an unorganized list. |
| < (Back button) | Returns you to your most recent landing page configuration in a Workspace project or a report. The page configuration you had when you left the landing page will persist when you return. |

-->

## Learning

The Learning page contains hands-on video tours, tutorials, and links to documentation.

Use the Learning page in Customer Journey Analytics to learn:

* Beginner, intermediate, or advanced features and use-cases in Customer Journey Analytics
* How to transition more seamlessly from Adobe Analytics to Customer Journey Analytics

To access the learning content:

* In Customer Journey Analytics, select [!UICONTROL **Workspace**] from the top menu and select [!UICONTROL **Learning**] from the left panel.

### Features

The learning page offers the following features

* **Filter content:** Use ![Filter](/help/assets/icons/Filter.svg) to filter learning content by **[!UICONTROL Type]** (**[!UICONTROL Document]**, **[!UICONTROL Video]**, and **[!UICONTROL Tours & tutorials]**) and **[!UICONTROL Experience Level]** (**[!UICONTROL Beginner]**, **[!UICONTROL Intermediate]**, or **[!UICONTROL Advanced]**).
* **Track progress:** After you select a piece of content, a ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Viewed]** tag appears. This tag helps you track your progress through the learning content. You can select the ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL Viewed]** tag to remove it from a piece of content.
* **View additional content:** While viewing any video, select **[!UICONTROL Learn more]** to view related documentation content on Experience League. Or, from the Learning page, select either of the following options to view additional content:
  * **[!UICONTROL Visit YouTube]:** View the full Analysis Workspace YouTube playlist.
  * [!UICONTROL **Visit Experience League**]: View the full suite of Customer Journey Analytics documentation on Experience League. 
* **Fundamentals for new users:** The [!UICONTROL Learning Workspace Fundamentals] tour is recommended for new users. This tour takes you directly to Workspace and walks you through the most common actions. This tour can also be relaunched any time in Workspace via the tooltip from the [Freeform panel](/help/analysis-workspace/c-panels/freeform-panel.md) or [Blank panel](/help/analysis-workspace/c-panels/blank-panel.md) header.

## Preferred landing page

You can set your preferred landing page. See [User preferences](/help/analysis-workspace/user-preferences.md#general-preferences) for more information.

<!--
## Landing page FAQ {#landing-faq}

| Question | Answer |
| --- | --- |
| Does the work I do in the beta program UI carry over to the production [!UICONTROL Workspace] experience? | Yes, any work done in the beta carries over to the old/current [!UICONTROL Workspace] experience. |
| Is there a maximum number of projects I can pin? | No, there is no limit on the number of projects you can pin. |
| Can admins designate this landing page for their users? | No, admins cannot designate the landing page on behalf of users. Individual users must turn on the toggle themselves. |
| Are all reports that currently exist in [!DNL Reports & Analytics] still available? | No, the following reports were phased out, based on overall usage data: <ul><li>Any custom eVars/props/events/classifications<li>My Recommended Reports</li><li>Hourly/Daily/Weekly/Monthly/Quarterly/Yearly unique visitors</li><li>DailyWeekly/Monthly/Quarterly/Yearly unique customers</li><li>Action name depth</li><li>Action name summary</li><li>Add dashboard</li><li>Age</li><li>Audio support</li><li>Billing information</li><li>Clicks to page</li><li>Color depth</li><li>Cookie support</li><li>Cookies</li><li>Connection types</li><li>Creative elements</li><li>Credit card type</li><li>Cross sell</li><li>Custom event funnels</li><li>Custom links</li><li>Customer ID</li><li>Day of week</li><li>Entry action name</li><li>Exit action name</li><li>Exit links</li><li>Fallout</li><li>File downloads</li><li>Find in store</li><li>Full paths</li><li>Gender</li><li>Hit ype VISTA rule</li><li>Image support</li><li>Java</li><li>JavaScript</li><li>JavaScript version</li><li>Manage bookmarks</li><li>Manage dashboards</li><li>Monitor color depth</li><li>Monitor resolutions</li><li>Newsletter signups</li><li>Next action name</li><li>Next action name flow</li><li>Null searches</li><li>Operating system</li><li>Order review</li><li>Page of day</li><li>Pages not found</li><li>Pathfinder</li><li>Path length</li><li>Previous action name</li><li>Previous action name flow</li><li>Product activity</li><li>Product cost</li><li>Product department</li><li>Product inventory category</li><li>Product name</li><li>Product reviews</li><li>Product season</li><li>Product shares</li><li>Product zooms</li><li>Reload</li><li>Searches</li><li>Servers</li><li>Single page visits</li><li>Shipping information</li><li>Site hierarchy</li><li>Social mentions</li><li>Time of day</li><li>Time spent on action name</li><li>Video support</li><li>Visitor state</li></ul> |
-->
