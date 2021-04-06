---
title: Manage filters
description: lean how to manage filters in Customer Journey Analytics
exl-id: b8869560-0cf1-4e5d-a03c-dfca85d05e66
---
# Manage filters

The Filter Manager offers many ways of curating segments, such as sharing, tagging, approving, copying, deleting, and marking as favorites.

The Filter Manager shows you all the filters you own and that have been shared with you. Admin-level users can see all filters in the organization. This overview presents the user interface and the capabilities of the Filter Manager. 

Access the Filter Manager by going to **[!UICONTROL Customer Journey Analysis]** > **[!UICONTROL Components]** > **[!UICONTROL Filters]** in the top navigation.

## Filter Manager UI

![](assets/filter-manager-ui.png)

|  #  | UI Feature  | Description  |
|---|---|---|
|  1  | Filter Management Tool Bar  | Once you have checked a filter, this tool bar appears. Most management tasks can be completed from this tool bar.  |
|  2  | Check boxes  | Check a filter in order to manage it.  |
|  4  | Favorites  | Clicking the star next to a filter turns the star yellow and marks the filter as a favorite.  |
|  5  | Title and description  | Provided in the Filter Builder. To edit the title and description, click the title link - this takes you back to the Filter Builder.  |
|  7  | Owner  | Indicates who owns the filter. As a non-Admin, you can see only filters you own or those that were shared with you.  |
|  8  | Tags (not checked in column selector, hence column not appearing)  | Tags that were applied to the filter, either by you or by people who shared the filter with you.  |
|  9  | Shared with  | Lists individuals or groups (Admin only) or All (Admin only) that you shared the filter with.  |
|  10  | Date Modified  | Shows the date that the filter was last modified.  |
|  11  | Column selector  | (Top right) Lets you select which columns to display in the Filter Manager.  |
|  12  | Shared icon  | Indicates that this filter is shared by you or with you.  |
|  13  | Approved icon  | Indicates that this filter has been approved by an Administrator.  |
|  14  | Other Filters  | Lets you see filters by Tags, Data Views, Owners, and Other (Show All, Mine, Shared with Me, Approved, Favorites.)  |

## Plan filters

Devoting some time to plan segments improves the chances that they will be useful for your organization and that their numbers will be kept in check.

* Consider the audience : Who will consume it? With whom will you share it? Which groups of people will use this filter and how should I tag it accordingly? This also means providing a good filter description. At minimum, the description should answer these questions:

    * What is this filter useful for?

    * When should I use this filter? 

* Determine the filter scope . Which [filter container](/help/components/filters/filters-overview.md) best represents the scope? Use the smallest container possible.

* Decide which elements to include in the filter definition, and which values.

* Consider how you want your approval process to unfold. Will a single person review and approve filters or will it be a committee decision?

* Define your filters with view to a filter library that gives business users the ability to stack and reuse filter pieces or components in a modular fashion. What "modules" do you need to define to make this library a reality? 

### Tag filters

In the Filter Manager, tagging filters allows you to organize them. All users can create tags for filters and apply one or more tags to a segment. However, you can see tags only for those filters that you own or that have been shared with you.

What kinds of tags should you create? Here are some suggestions for useful tags:

* Tags based on team names, such as Social Marketing, Mobile Marketing.
    
* Project tags (analysis tags), such as Entry-page analysis.
    
* Category tags: Men's; geography.
    
* Workflow tags: To be approved; Curated for (a specific business unit)

To tag a filter:

1. In the Filter Manager, mark the checkbox next to the filter you want to tag. The filter management tool bar appears.

1. Click **[!UICONTROL Tag]** and either

    * select from existing tags, or

    * enter a new tag name and press **[!UICONTROL Enter]**. 

1. Click **[!UICONTROL Tag]** again to tag the segment. 

The tag should now appear in the Tags column. (Click the gear icon on the top right to manage your columns.)
You can also filter on tags by going to **[!UICONTROL Filters > Tags]**. 

### Approve filters

Within the Filter Manager, you can set up a workflow that includes approving filter for various levels of application, for specific departments or groups, and consistent with reporting policies.

Here is how to flag a filter as approved:

1. In Filter Manager, check the checkbox to the left of the Filter title.
    
1. Click **[!UICONTROL Approve]** in the filter management task bar.

1. Consider sharing the approved segment/s with your organization.
    
1. Click **[!UICONTROL OK]**.

    Notice the approval icon next to the filter in the list:

    ![](assets/seg_approved.png)

1. You can also unapprove an approved segment by clicking **[!UICONTROL Unapprove]**. 

### Share filters

Depending on your permissions, you can share filters with your whole organization, groups, or individual users. 

|Administrator| Non-Administrator|
|---|---|
|Can share filters with All, with Groups, and with Users. See the [Admin Console documentation](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) for more information.|Can share filters only with individual users.|

When should you share filters with the entire company versus just a group of users or individuals? Here are some best practices you might follow:

* As an Admin, share a filter with All if it's of use to the entire company and everyone is comfortable using it. In this case, you should also consider making it an approved filter.

* As an Admin, share a filter with a specific Product Profile if the filter provides good business value for that team. Do not officially approve this type of filter.

* As an Admin or an individual user, share a filter with other individuals to vet and validate a filter. If it doesn't prove useful, it can be discarded. Do not officially approve this type of filter. 

To share a filter:

1. In the Filter Manager, mark the checkbox next to the filter you want to share. 

1. In the filter management tool bar, click **[!UICONTROL Share]**.

1. If you are an Admin, you can select All or choose from Groups and Users in your organization. As a non-Admin, you can see only individual users. Use the Search field to search for groups or users. Click **[!UICONTROL Share]**. The Shared icon appears next to the filter: ![](assets/share_icon.png)

1. You can filter on filters shared with you by going to Filters > Other Filters > Shared with Me. 

### Mark filters as favorites

Marking segments as favorites is another way to organize them for ease of use.

1. In the Filter Manager, check the star next to any filter that you want to mark as a favorite. The star turns yellow when you select it.

1. You can also filter on favorites under Filters > Other Filters > Favorites.
