---
description: How to specify dates and date ranges, or select a preset.
title: Calendar and date ranges overview
feature: Calendar
solution: Customer Journey Analytics
exl-id: 4afdc68b-97f8-4d8a-9d13-e2f3986873f1
role: User
---
# Calendar and date ranges overview

Using the calendar, you can specify dates and date ranges, or select a preset. Date ranges are a type of component you can use in Workspace projects. They allow you to see data trended over time or see when events happen the most. Date ranges are color coded in purple. Custom date ranges allow you to customize the dates you see in Workspace projects. 

Calendar selections apply at the panel level, but you have the option to apply them to all panels. When you click a date range in Workspace, the interface displays the current calendar month and the previous calendar month. You can adjust these two calendars by clicking the right and left arrows in each respective upper corner.

![Calendar showing October 2022 and November 2022 with November 1 through 30 selected.](assets/aw_calendar2.png){width="60%"}

The first click on a calendar starts a date range selection. The second click completes a date range selection, which becomes highlighted. If the `Shift` key is held down (or right-click is used), it appends to the currently selected range.

You can also drag dates (and time dimensions) into a Workspace project. You can select specific days, weeks, months, years, or a rolling date.

[Using Date Ranges and Calendar in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html) (4:07)

| Setting | Description |
| --- | --- |
| Selected Days | Selected days/weeks/months/years |
| Use Rolling Dates | Rolling dates allow you to generate a dynamic report that looks forward or backward for a set period of time based on when you ran the report. For example, if you want to report on all Orders placed "Last Month" (based on the Created Date field) and ran that report in December, you'd see orders placed in November. If you ran that same report in January, you'd see orders placed in December.<ul><li>**[!UICONTROL Date Preview]**: Indicates what time period the rolling calendar encompasses.</li><li>**[!UICONTROL Start]**: You can choose among current day, current week, current month, current quarter, current year.</li><li>**[!UICONTROL End]**: You can choose among current day, current week, current month, current quarter, current year.</li></ul>For an example, go [here](/help/components/date-ranges/custom-date-ranges.md). |
| Date Range | Lets you pick a preset date range. Last 30 days is the default. **[!UICONTROL This week/month/quarter/year (excluding today)]** lets you choose from date ranges that do not include partial-day data from today. |
| Apply to All Panels | Lets you not only change the selected date range for the current panel, but also for all other panels within the project. |
| Apply | Applies the date range to this panel only. |

## About relative panel date ranges {#relative-panel-dates}

If you're working in Workspace, you can make the date range components relative to the panel calendar. Three common use cases where you'll see relative panel dates take effect are Combo charts, Key metrics summary, and Freeform table date ranges.

To use relative panel date ranges

1.  Select the **Workspace** tab.
1.  Select **Blank project**.
1.  Add dimensions, metrics, and filters from the left rail. 
1.  Click the panel date range field to toggle the relative panel date range setting.
1.  Select **Make date range components relative to panel calendar**.
    *   Select the option to make the date range components relative to the panel calendar.
        If relative dates are selected, then rolling dates will be based on the start date of the panel calendar and not today's date.
    *   If this option isn't selected, then rolling dates will be based on today's date.

    ![Calendar with Make date range components relative to panel calendar selected](assets/relative-date-selected.png){width="60%"} 

1.  Click **Apply**.
    The relative dates are shown in the upper-right.

    ![Freeform table with relative dates highlighted and showing Last month highlighted. ](assets/relative-date-range1.png)

## Guidelines for relative panel date ranges {#guidelines}

Keep in mind the following guidelines when using relative panel date ranges.

### Formulas and relative date ranges {#formula-relative-dates}

If you have relative dates selected, all date formulas will use the panel's start date as the starting point.

### Custom calendars and relative date ranges {#custom-calendar-formulas}

When you use a week-based custom calendar and you add months or years, the formula calculates the offset of the day in the given period. The actual date may be different because of the offset. The formula chooses the day landing in the same place in the custom calendar. For example, the third Friday of the third week in a custom calendar.

### About filters that use rolling dates and relative panel date ranges {#segments-relative-dates}

If you build a filter or use a filter with a rolling date, for example, the Last 7 Days or the Last 2 Weeks, and you click on the filter preview, it will start the rolling date from *Today* instead of the panel start date. As a result the preview for the filter will not match when you actually use the filter in the table. The preview is impacted, not the filter itself. 

## Guidelines for panel date ranges and previews {#guidelines-panel-dates}

*   Starting with the February release, component and data previews will be based on the panel date range and not the last 90 days. 
*   All components listed in the left rail will be available based on the panel date range. 
*   All date previews in the filter and calculated metric builders will be based on the panel date range (unless accessed from the component managers, which do not have an associated panel, they will still be based on the last 90 days). 
*   Any data previews will display data or components based on the panel date range.