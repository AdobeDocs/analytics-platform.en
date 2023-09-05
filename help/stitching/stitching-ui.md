---
title: Stitching
description: Understand how to create and manage stitched datasets
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
hide: yes
hidefromtoc: yes
---
# Create and manage stitched datasets

{{select-package}}

Stitching allows administrators to stitch identities on datasets available in Customer Journey Analytics. Stitching datasets increases the accuracy of a profile's representation resulting ultimately in better analysis and reporting.

The stitching process allows you to define an existing **persistent ID** in a dataset. Then stitch that persistent identifier for a specified replay window (daily, weekly) with the most accurate **transient ID** (person or authenticated identifier) available for that dataset. Examples of transient identifiers are email, phone number, CRM id, or other identities stored in the graph. See [Overview](overview.md) for more information on stitching.

## Create

To initiate stitching, you create one or more stitched datasets. To create a stitched dataset:

1. Select **[!UICONTROL **Stitching**]** from **[!UICONTROL **Data Management**]** at the top bar.

2. In the [!UICONTROL Stitched datasets] screen, select **[!UICONTROL **Create stitched dataset**]**.

    You are prompted with a dialog explaining your responsibilities.

3. Select **[!UICONTROL **Continue**]** if you accept these responsibilities. 

    >[!NOTE]
    >
    >    If you select **[!UICONTROL **Cancel**]**, you are not able to create a stitched dataset.

4. In the [!UICONTROL Stitched datasets > Untitled stitched dataset] screen:

   1. Define a **[!UICONTROL **Dataset name**]** and (optional) **[!UICONTROL **Description**]**,

   2. Select the sandbox from the **[!UICONTROL **Sandbox**]** list where the event dataset is stored.

        ![Initial creation screen](./assets/create-initial.png)

   3. Select the **[!UICONTROL **Select source dataset**]** button. 

        In the [!UICONTROL Select one dataset to stitch] popup window:

        ![Select one dataset](./assets/select-one-dataset.png)

        - Select a dataset and select **[!UICONTROL **Select**]** to continue.

   4. Select a persistent identifier from the **[!UICONTROL **Persistent ID**]** list.

   5. Select a transient identifier from the **[!UICONTROL **Transient ID**]** list.

      You notice that a preview panel appears to calculate the saturation rates (number of times there is a value for each of the specified identifiers over the number of events) for the last seven days. When finished calculating, the panel visualizes with colors whether the minimal conditions for stitching are met (green) or not met (red).

      ![Create stitched datset with staturation rates](./assets/create-before-experimenting.png)
        
      The minimal conditions are:

      - persistent identifier saturation: rate >= 95%
        
      - transient identifier saturation: rate >= 5%

        If the minimal conditions are met, you can experiment with sample values.

      - Select **[!UICONTROL **Create demo stitched ID's**]**.

        In the [!UICONTROL Experiment with sample values] dialog, a table is shown with sample value for [!UICONTROL timestamp], [!UICONTROL Persistent ID], [!UICONTROL Transient ID], [!UICONTROL Stitched ID (Live)], [!UICONTROL Stitched ID (1-day replay)], and [!UICONTROL Stitched ID (7-day replay)].

            ![Experiment with sample values](./assets/experiment-sample-values.png)

            1.  Enter a value for the **[!UICONTROL **Persistent ID**]**.

            2.  Select **[!UICONTROL **Refresh stitched IDs**]** to see the effect of the stitching process on the data in the dataset.

            3.  Select **[!UICONTROL **Close**]** when you are finished experimenting with samples values.


        Back in the [!UICONTROL Stitched datasets > _Dataset name_] screen:

   6. Select an option for the frequency and period of restating historical data from the **[!UICONTROL **Replay window**]** list.  
    
        You can select between the default value **[!UICONTROL **Previous day, daily**]** or **[!UICONTROL **Previous 7 days, weekly**]**. 

   7. Select a value from the **[!UICONTROL **Average number of daily events**]** list.

   8. Enter a value (between `0` and `12`) in **[!UICONTROL **Number of months to backfill**]**.

   9. Select **[!UICONTROL **Save**]** to save your stitched dataset and initiate the stitching.

## View status

You can view the status of stitching in the [!UICONTROL Stitched datasets] list.

- Select **[!UICONTROL **Stitching**]** from **[!UICONTROL **Data Management**]** at the top bar.

  You see a list of stitched datasets, each identified with [!UICONTROL Sandbox], [!UICONTROL Source dataset], [!UICONTROL Status], [!UICONTROL Backfill status], [!UICONTROL Owner], and [!UICONTROL Date created]. 
    
  ![Overview of stitched datasets](./assets/overview-stitched-datasetts.png)
    
  Possible values for [!UICONTROL Status] are: 

  | Value | Explanation |
  |-----|-----|
  | **[!UICONTROL **Queued**]** | The request is received and processes soon. |
  | **[!UICONTROL **Creation**]** in progress | Resources and newly stitched dataset is under creation. |
  | **[!UICONTROL **Stitching in progress**]** | Resources and stitched dataset exist and stitching is in progress |
  | **[!UICONTROL **Error**]** | There is an issue with stitching. Maybe a schema changed between source dataset and stitched dataset, the daily volume is too large, or... (_**need more information here...**_) | 

  >[!INFO]
  >
  >    Whenever a status changes, a notification is sent with the message **[!UICONTROL **Stitched dataset _name of dataset_ has changed to status _name of status_**]**.


  The [!UICONTROL Backfill status] can have the following values: 0%, 25%, 50%, 75%, or 100%.

  You can select the information icon to display a popup with more details on the selected stitched dataset.


## Delete

>[!NOTE]
>
>You can only delete datasets that have the status [!UICONTROL Stitching in progress], [!UICONTROL Error], or [!UICONTROL Queued].


To delete a single stitched dataset:

- Select **[!UICONTROL **...**]** for the stitched dataset and select **[!UICONTROL **Delete**]** from the menu.

  ![Delete a stitched dataset](./assets/delete-stitched-dataset.png)

To delete multiple stitched data:

- Select multiple stitched datasets using the checkbox at the start of each listed dataset.

- Select **[!UICONTROL **...**]** from one of the selected stitched datasets and select **[!UICONTROL **Delete**]** from the menu.
