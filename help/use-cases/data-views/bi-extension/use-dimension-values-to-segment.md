---
title: Use Dimension Values To Segment
description: Use dimension values to segment use case for the BI extension in various BI tools in Customer Journey Analytics
solution: Customer Journey Analytics
feature: Data Views
role: User
---
# Use dimension values to segment

You use the dynamic **[!UICONTROL Hunting]** value for **[!UICONTROL Product Category]** to segment products from the hunting category. Alternatively, for those BI tools that do not support the dynamic retrieval of product category values, you create a new segment in Customer Journey Analytics that segments on products from the hunting product category. 
Then you want to use the new segment to report on product names and occurrences (events) for products from the hunting category during January 2023.

+++ Customer Journey Analytics

Create a new segment with **[!UICONTROL Title]** `Hunting Products` in Customer Journey Analytics.

![Customer Journey Analytics Use Dimension Values To Segment](../assets/cja-hunting-products.png)

You then can use that segment in an example **[!UICONTROL Using Dimension Values To Filter]** panel for the use case:

![Customer Journey Analytics Distinct Count Values](../assets/cja-using-dimension-values-to-filter.png)

+++

+++ BI tools

>[!PREREQUISITES]
>
>Ensure you have validated [a successful connection, can list data views, and use a data view](connect-and-validate) for the BI tool for which you want to try out this use case. 
>

>[!BEGINTABS]

>[!TAB Power BI Desktop] 

1. Select **[!UICONTROL Home]** from the menu, then select **[!UICONTROL Refresh]** from the toolbar. You need to refresh the connection to pick up the new filter you just defined in Customer Journey Analytics.
   
1. In the **[!UICONTROL Data]** pane:
   1. Select **[!UICONTROL daterange]**.
   1. Select **[!UICONTROL product_category]**.
   1. Select **[!UICONTROL product_name]**.
   1. Select **[!UICONTROL sum occurrences]**.

  You see a visualization displaying **[!UICONTROL Error fetching data for this visual]**.

1. In the **[!UICONTROL Filters]** pane:
   1. Select **[!UICONTROL filterName is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Select **[!UICONTROL Basic filtering]** as the **[!UICONTROL Filter type]**.
   1. Select **[!UICONTROL daterange is (All)]** from **[!UICONTROL Filters on this visual]**.
   1. Select **[!UICONTROL Advanced filtering]** as the **[!UICONTROL Filter type]**.
   1. Define the filter to **[!UICONTROL Show items when the value]** **[!UICONTROL is on or after]** `1/1/2023` **[!UICONTROL And]** **[!UICONTROL is before]** `2/1/2023`.
   1. Select **[!UICONTROL Basic filter]** as the **[!UICONTROL Filter type]** for **[!UICONTROL product_category]**, and select **[!UICONTROL Hunting]** from the list of possible values. 
   1. Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove **[!UICONTROL filterName]** from **[!UICONTROL Columns]**.
   1. Select ![CrossSize75](/help/assets/icons/CrossSize75.svg) to remove **[!UICONTROL daterange]** from **[!UICONTROL Columns]**.
   
   You see the table updated with the applied **[!UICONTROL product_category]** filter. Your Power BI Desktop should look like below.

   ![Power BI Desktop Using Date Range Names To Filter](../assets/uc10-powerbi-final.png)



>[!TAB Tableau Desktop] 

![AlertRed](/help/assets/icons/AlertRed.svg) Tableau Desktop does not support fetching the dynamic list of product categories from Customer Journey Analytics. Instead, this use case uses the newly created filter for **[!UICONTROL Hunting Products]** and use the filter name critetia.

1. In the **[!UICONTROL Data Source]** view, underneath **[!UICONTROL Data]**, from the context menu on **[!UICONTROL cc_data_view(prod:cja%3FFLATTEN)]**, select **[!UICONTROL Refresh]**. You need to refresh the connection to pick up the new filter you just defined in Customer Journey Analytics.
1. Select the **[!UICONTROL Sheet 1]** tab at the bottom to switch from **[!UICONTROL Data source]**. In the **[!UICONTROL Sheet 1]** view:
   1. Drag the **[!UICONTROL Filter Name]** entry from the **[!UICONTROL Tables]** list in the **[!UICONTROL Filters]** shelf.
   1. In the **[!UICONTROL Filter \[Filter Name\]]** dialog ensure **[!UICONTROL Select from list]** is selected, and select **[!UICONTROL Hunting Products]** from the list. Select **[!UICONTROL Apply]** and **[!UICONTROL OK]**.
   1. Drag **[!UICONTROL Daterange]** entry from the **[!UICONTROL Tables]** list in the **[!UICONTROL Filters]** shelf.
   1. In the **[!UICONTROL Filter Field \[Daterange\]]** dialog, select **[!UICONTROL Range of Dates]** and select **[!UICONTROL Next >]**.
   1. In the **[!UICONTROL Filter \[Daterange\]]** dialog, select **[!UICONTROL Range of dates]**, and select `01/01/2023` - `1/2/2023`. Select **[!UICONTROL Apply]** and **[!UICONTROL OK]**.
   1. Drag **[!UICONTROL Product Name]** from the **[!UICONTROL Tables]** list to **[!UICONTROL Rows]**.
   1. Drag **[!UICONTROL Occurrences]** entry from the **[!UICONTROL Tables]** list and drop the entry in the field next to **[!UICONTROL Columns]**. The value changes to **[!UICONTROL SUM(Occurrences)]**.
   1. Select **[!UICONTROL Text Table]** from **[!UICONTROL Show Me]**.
   1. Select **[!UICONTROL Fit Width]** from the **[!UICONTROL Fit]** drop-down menu.

      Your Tableau Desktop should look like below.

      ![Tableau Desktop Multiple Dimension Ranked Filter](../assets/uc10-tableau-final.png)   

>[!TAB Looker]

1. In the 1. In the **[!UICONTROL Explore]** interface of Looker, refresh your connection. Select ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Clear cache and refresh]**.
1. In the **[!UICONTROL Explore]** interface of Looker, ensure you do have a clean setup. If not, select ![Setting](/help/assets/icons/Setting.svg) **[!UICONTROL Remove fields and filters]**.
1. Select **[!UICONTROL + Filter]** underneath **[!UICONTROL Filters]**.
1. In the **[!UICONTROL Add Filter]** dialog:
   1. Select **[!UICONTROL ‣ Cc Data View]**
   1. From the list of fields, select **[!UICONTROL ‣ Daterange Date]** then **[!UICONTROL Daterange Date]**.
      ![Looker filter](../assets/uc2-looker-filter.png)
1. Specify the **[!UICONTROL Cc Data View Daterange Date]** filter as **[!UICONTROL is in range]** **[!UICONTROL 2023/01/01]** **[!UICONTROL until (before)]** **[!UICONTROL 2023/02/01]**.
1. Select **[!UICONTROL + Filter]** underneath **[!UICONTROL Filters]** to add another filter.
1. In the **[!UICONTROL Add Filter]** dialog:
   1. Select **[!UICONTROL ‣ Cc Data View]**
   1. From the list of fields, select **[!UICONTROL ‣ Product Category]**.
1. Ensure **[!UICONTROL is]** as the selection for the filter.

![AlertRed](/help/assets/icons/AlertRed.svg) Lookes does not show the list of possible values for **[!UICONTROL Product Category]**.

![Looker count distinct](../assets/uc10-looker-result.png)


>[!TAB Jupyter Notebook]

1. Enter the following statements in a new cell.

   ```python
   data = %sql SELECT DISTINCT product_category FROM cc_data_view WHERE daterange BETWEEN '2023-01-01' AND '2024-01-01';
   style = {'description_width': 'initial'}
   category_filter = widgets.Dropdown(
      options=[d for d, in data],
      description='Product Category:',
      style=style
   )
   display(category_filter)
   ```

1. Execute the cell. You should see output similar to the screenshot below.

   ![Jupyter Notebook Results](../assets/uc10-jupyter-input.png)

1. Select **[!UICONTROL Hunting]** from the drop-down menu.

1. Enter the following statements in a new cell.

   ```python
   import seaborn as sns
   import matplotlib.pyplot as plt
   data = %sql SELECT product_name AS `Product Name`, COUNT(*) AS Events \
               FROM cc_data_view \
               WHERE daterange BETWEEN '2023-01-01' AND '2023-02-01' \
               AND product_category = '{category_filter.value}' \
               GROUP BY 1 \
               ORDER BY Events DESC \
               LIMIT 10;
   df = data.DataFrame()
   df = df.groupby('Product Name', as_index=False).sum()
   plt.figure(figsize=(15, 3))
   sns.barplot(x='Events', y='Product Name', data=df)
   plt.show()
   display(data)
   ```

1. Execute the cell. You should see output similar to the screenshot below.

   ![Jupyter Notebook Results](../assets/uc10-jupyter-results.png)


>[!TAB RStudio]

1. Enter the following statements between ` ```{r} ` and ` ``` ` in a new chunk. Ensure you use an appropriate category. For examplee, `Hunting`.

   ```R
   ## Dimension 1 Filtered by Dimension 2 value
   df <- dv %>%
      filter(daterange >= "2023-01-01" & daterange < "2023-02-01" & product_category == "Hunting") %>%
      group_by(product_name) %>%
      count() %>%
      arrange(desc(n), .by_group = FALSE)
   print(df)
   ```

1. Run the chunk. You should see output similar to the screenshot below.

   ![RStudio Results](../assets/uc10-rstudio-results.png)

>[!ENDTABS]

+++

