---
description: You can download data from Analysis Workspace by copying it, or in PDF and CSV formats.
title: Download Customer Journey Analytics data
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
---
# Download Customer Journey Analytics data

You can download Customer Journey Analytics data to your personal workstation. This can be in the form of copied data, CSV, or PDF. A PDF is typically preferred if you want visualizations included in the downloaded file. CSV and copied data is preferred if you simply want plain-text data.

Other methods of exporting Customer Journey Analytics data are also available, as described in [Export overview](/help/analysis-workspace/export/export-project-overview.md).

## Download as CSV or PDF {#download-project}

Consider the following when downloading projects:

* When downloading projects as a CSV or PDF, the project can be saved or unsaved when you request a project download. However, only saved projects can be [scheduled](/help/analysis-workspace/export/t-schedule-report.md). 

* When downloading projects as a PDF:
  * Downloads can take several minutes to export because the project is re-run on Adobe servers before rendering in PDF format. We recommend not leaving the project until the PDF downloads in your browser. However, you can continue to make changes to the project while you wait. If a PDF takes longer than 5 minutes to render, you will be prompted to email it instead.
  * Downloads are rendered as a single page with no pagination applied.
  * PDF renderings contain what is on the page in Workspace. If a project has custom-sized visualizations and panels, you need to change them to be auto-sized (button in top-right corner) so that there will be no truncated content.
  * Any [hyperlinks](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md) that exist within freeform tables are not functional in the downloaded PDF. 

To download a project as a CSV or PDF file:

1. Do either of the following, depending on what format you want the download to be in:

   * **PDF:** Select **[!UICONTROL Project]** > **[!UICONTROL Download PDF]**.
  
     Choose this option if you want the downloaded file to contain all the displayed (visible) tables and visualizations in the project.

   * **CSV:** Select **[!UICONTROL Project]** > **[!UICONTROL Download CSV]**. 

     Choose this option if you want the downloaded file to be plain-text.

   ![The Project drop-down menue with the Download CSV and Download PDF options highlighted.](assets/download-project.png)

1. (Conditional) If you chose to download a PDF, a message is shown after the project is ready to be downloaded. Select [!UICONTROL **Download**].

## Copy to clipboard (hotkey: Ctrl+C) {#copy-data}

The right-click option **[!UICONTROL Copy to clipboard]** lets you quickly copy Customer Journey Analytics data from Workspace and paste it in a third-party tool. 

* If you want the displayed table copied, right-click the table header and choose **Copy data to clipboard**. 
* If you want a subset of data copied, make a selection in the table and then right-click > **Copy selection to clipboard**.

>[!TIP]
>
>You can use the hotkey `Ctrl+C` to copy your selection to the clipboard, then use `Ctrl+V` to paste it into a third-party tool.


![The Copy selection to clipboard option. ](assets/copy-selection.png)

## Download as CSV {#download-data}

The right-click option **[!UICONTROL Download data as CSV]** allows you to download a table of Customer Journey Analytics data or the data source of any visualization as a CSV.

* From the header of any table or visualization, right-click and choose **[!UICONTROL Download data as CSV]**. This downloads the displayed Customer Journey Analytics data in the table or the underlying data source for a visualization as a CSV. 

  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.


* Within a table, right-click and choose **[!UICONTROL Download selection as CSV]**. Only the selection is downloaded with this option, as opposed to the full, displayed table.

![The Download data as CSV option.](assets/download-data-viz.png)

## Download items as CSV {#download-items}

If you want to analyze more than the visible 400 rows of data in a table, right-click the table header or any row and select **Download items as CSV (_Dimension name_)**. This option exports up to 50,000 dimension items (based on the table sort) for the selected dimension, with sort options and filters applied. If you chose this option from the top of the table, the first dimension in the table will be exported. While no limits are enforced in the freeform table, it is recommended that the Download items option be used in tables with less than 20 columns to ensure optimal performance.

>[!TIP]
>
> If your dimension exceeds 50,000 items, download the file with different sort metrics applied or apply a filter. For example, sort descending by Visits in one download and then ascending by Visits in a second download. This tip can help you retrieve longer-tail items.

You can multi-task within the project and even navigate to a new Workspace project in the same tab while the download is in progress. The download pauses if you open a new browser tab. The download is canceled if you leave Workspace completely or close the browser tab.

![The Download items as CSV (Page) option.](assets/download-items.png)

### Downloaded items file {#items-file}

Features of the table will be applied to the downloaded file as follows:

* All panel filters are applied as filters.
* Breakdowns **above** the selected dimension in the table are applied as filters above each column. 
* Breakdowns **below** the selected dimension in the table are removed.

In the example above, Page items are downloaded with the panel filter (New Visitors Customers) and components above (Marketing Channel = Email) applied as filters, and the components below (Mobile Device Type) removed from the downloaded CSV.

![The downloaded .csv file opened in Excel.](assets/downloaded-file.png)

### Download notifications {#notifications}

As the file downloads, you will see an informational notification with the progress. At any time, you can cancel the download by clicking **[!UICONTROL Cancel download]**. Closing the toast **will not** cancel the download. 

Once the file completes, you will see a completion notification and the file will download to your browser.

If you request more than one download at a time, you will receive a notification that each additional download will be queued until the prior download completes.

![The download status notification showing the percentage complete and a Cancel download link.](assets/toast.png)

## Download sensitive data {#sensitive}

If the **[!UICONTROL Enforce Download]** [data governance policy](/help/data-views/data-governance.md) is turned on in the data view you are reporting on, any download (such as emailing or sharing PDF files) of Workspace projects will hash the data fields labeled as sensitive. You can still do analysis on these fields in Workspace, but if you try to email or otherwise share a project, the blocked fields will appear as empty in the .pdf or .csv file.

If any data fields labeled as sensitive are included in the [!UICONTROL Data View], the option to select and copy data from the screen is restricted for all data in the [!UICONTROL Data View].

## FAQ {#faq}

| Question | Answer |
| --- | --- |
| Why is my downloaded PDF one page? | Workspace does not paginate downloaded PDFs at this time. |
| Can I export more than 50,000 items with the "Download items as CSV" option? | While each download can contain up to 50,000 dimension items, you can change the sort of your table to retrieve longer tail items, or apply a filter to download more specific items. |
| What does **[!UICONTROL Copy visualization]** do? | Unlike [!UICONTROL **Copy data to clipboard**] or [!UICONTROL **Copy selection to clipboard**], the **[!UICONTROL Copy visualization]** right-click option is not an export option. It allows you to copy a visualization or panel from one place in Workspace to another. For example, from one panel to another in the same project, or from one project to another project. [Intra-linking video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |
