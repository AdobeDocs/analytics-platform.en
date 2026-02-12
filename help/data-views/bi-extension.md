---
title: Customer Journey Analytics BI Extension
description: Learn how you can use Power BI or Tableau Desktop to access data views using the Customer Journey Analytics BI extension.
solution: Customer Journey Analytics
feature: BI Extension
role: Admin
exl-id: ab7e1f15-ead9-46b7-94b7-f81802f88ff5
---
# Customer Journey Analytics BI extension

{{select-package}}

The [!DNL Customer Journey Analytics BI extension] enables SQL access to the [data views](./data-views.md) that you have defined in Customer Journey Analytics. Your data engineers and analysts might be more familiar with Power BI,  Tableau Desktop, or other business intelligence and visualization tools (further referred to as BI tools). They can now create reporting and dashboards based on the same data views that Customer Journey Analytics users are using when creating their Analysis Workspace projects.

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/home) is the SQL interface to data available in the data lake of Experience Platform. With the [!DNL Customer Journey Analytics BI extension] enabled, the functionality of [!DNL Query Service] is extended to see your Customer Journey Analytics data views as tables or views in a [!DNL Query Service] session. As a result, business intelligence tools that use [!DNL Query Service] as their PostgresSQL interface benefit seamlessly from this extended functionality.

The main benefits are:

* No need to recreate an equivalent representation of Customer Journey Analytics data views within the BI tool itself. <br/>See [Data views](data-views.md) for more information on the functionality of data views to understand what must be recreated.
* Greater consistency in reporting and analysis between BI tools and Customer Journey Analytics.
* Combine Customer Journey Analytics data with other data sources already available in BI tools.

## Prerequisites

To use this functionality, you can use expiring or non-expiring credentials to connect BI tools to the [!DNL Customer Journey Analytics BI extension]. The [Credentials guide](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/credentials) provides more information on setting expiring credentials or non-expiring credentials.
Below are additional steps to set up the required permissions.
<!---   Enable the [!UICONTROL Customer Journey Analytics BI extension] in your Experience Platform organization. -->

### Expiring credentials

To use expiring credentials, you can:

* Grant access to Experience Platform and Customer Journey Analytics. 
* Grant Product admin access to Customer Journey Analytics, so you can view, edit, update, or delete connections and data views.

Or you can: 

* Grant access to the data views you want to access.
* Grant access to the Customer Journey Analytics BI extension.

### Non-Expiring credentials

To use non-expiring credentials: 

* Create [non-expiring credentials in Experience Platform](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/bi-extension#non-expiring-credentials).
* Grant access to the non-expiring credentials by following the steps mentioned in [Expiring credentials](#Expiring-credentials).

See [Customer Journey Access Control](../technotes/access-control.md) for more information, specifically the [Product Admin additional permissions](../technotes/access-control.md#product-admin-additional-permissions) and [Customer Journey Analytics Permissions in the Admin Console](../technotes/access-control.md#customer-journey-analytics-permissions-in-admin-console).


## Usage

To use the [!DNL Customer Journey Analytics BI extension] functionality, you can either use SQL directly or use the drag and drop experience available in the specific BI tool. 

### SQL

You can use the functionality directly in SQL statements using either the Query Editor or a standard PostgresSQL command-line interface (CLI) client.

+++ Query editor

In Adobe Experience Platform:

1. Select **[!UICONTROL **Queries**]** from **[!UICONTROL **DATA MANAGEMENT**]** in the left rail.

1. Select ![Create Query](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **Create query**]**.

1. Select the `cja` database for your sandbox from the list of databases in the **[!UICONTROL Database]** drop-down menu. For example `prod:cja`.

1. To execute the query, type your SQL statement and select the ![Play](assets/Smock_Play_18_N.svg) button (or press `[SHIFT]` + `[ENTER]`).

+++


+++ PostgresSQL CLI

1. Look up and copy your PostgresSQL credentials in Adobe Experience Platform:

   1. Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

   1. Select **[!UICONTROL **Credentials**]** from the top bar.

   1. Select the `cja` database for your sandbox from the list of databases in the **[!UICONTROL Database]** drop-down menu. For example `prod:cja`.

   1. To copy the command string, use ![Copy](assets/Smock_Copy_18_N.svg) in the **[!UICONTROL **PSQL command**]** section.

1. Open a command or terminal window.

1. To log in and start executing your queries, paste the command string in your terminal.
    
+++

See the [Query Editor UI guide](https://experienceleague.adobe.com/en/docs/experience-platform/query/ui/user-guide) for more information.


### BI tools

Currently, the [!DNL Customer Journey Analytics BI extension] is supported and tested for the tools listed below. Other BI tools using the PSQL interface might work as well, but are not yet supported officially.

+++ Power BI

1. Look up the details of your PostgresSQL credentials in Adobe Experience Platform:

   1. Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

   1. Select **[!UICONTROL **Credentials**]** from the top bar.

   1. Select the `cja` database for your sandbox from the list of databases in the **[!UICONTROL Database]** drop-down menu. For example `prod:cja`.

   1. Use ![Copy](assets/Smock_Copy_18_N.svg) to copy each of the Postgres credentials parameters ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], and others) when needed in Power BI.

1. In Power BI:

   1. In the main window, select **[!UICONTROL **Get data**]** from the top toolbar.
   
   1. Select **[!UICONTROL More...]** in the left rail.

   1. In the **Get Data** screen, search for `PostgresSQL` and select the **[!UICONTROL **PostgresSQL database**]** from the list.

   1. In the **[!UICONTROL **PostgressSQL database**]** dialog:

      1. Paste the **[!UICONTROL **Host**]** parameter from Experience Platform Queries [!UICONTROL Credentials] in the  **[!UICONTROL **Server**]** text field.

      1. Paste the **[!UICONTROL **Database**]** parameter from Experience Platform Queries [!UICONTROL Credentials] in the **[!UICONTROL **Database**]** text field.
        
         Add `?FLATTEN` to the **[!UICONTROL **Database**]** parameter, so it reads like `prod:cja?FLATTEN` for example. See [Flatten nested data structures for use with third-party BI tools](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) for more information.

      1. When prompted for **[!UICONTROL Data Connectivity]** mode, select **[!UICONTROL DirectQuery]**.

      1. You are prompted for **[!UICONTROL Username]** and **[!UICONTROL Password]**. Use the equivalent parameters from Experience Platform Queries [!UICONTROL Credentials].


   1. After successful login, the Customer Journey Analytics data view tables appear in Power BIs **[!UICONTROL **Navigator**]**.

   1. Select the data view tables that you want to use and select **[!UICONTROL **Load**]**.

   All dimensions and metrics associated with one or more selected tables appear in the right pane, ready to be used in your visualizations.

   See [Connect Power BI to Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/power-bi) for more information. See also [BI extension use cases](/help/use-cases/data-views/bi-extension-usecases.md) for a detailed example.

+++

+++Tableau Desktop

1. Look up the details of your PostgresSQL credentials in Adobe Experience Platform:

   1. Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

   1. Select **[!UICONTROL **Credentials**]** from the top bar.

   1. Select the `cja` database for your sandbox from the list of databases in the **[!UICONTROL Database]** drop-down menu. For example `prod:cja`.

   1. Use ![Copy](assets/Smock_Copy_18_N.svg) to copy each of the Postgres credentials parameters ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], and others) when needed in Tableau Desktop.

1. In Tableau Desktop:

   1. Select **[!UICONTROL **More**]** from **[!UICONTROL **To a Server**]** in the left rail.

   1. Select **[!UICONTROL **PostgresSQL**]** from the list.

   1. In the [!UICONTROL PostgresSQL] dialog:

      1. Paste the **[!UICONTROL **Host**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into the **[!UICONTROL **Server**]** text field.

      1. Paste the **[!UICONTROL **Port**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into the **[!UICONTROL **Port**]** text field.

      1. Paste the **[!UICONTROL **Database**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into the **[!UICONTROL **Database**]** text field.

         Add `%3FFLATTEN` to the **[!UICONTROL **Database**]** parameter, so it reads like `prod:cja%3FFLATTEN` for example. See [Flatten nested data structures for use with third-party BI tools](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) for more information.

      1. Select **[!UICONTROL **Username and Password**]** from **[!UICONTROL **Authentication**]** list.

      1. Paste **[!UICONTROL **Username**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into **[!UICONTROL **Username**]** text field.

      1. Paste the **[!UICONTROL **Password**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into the **[!UICONTROL **Password**]** text field.

      1. Select the **[!UICONTROL **Sign In**]**.

   1. Customer Journey Analytics data views show up as tables in the **[!UICONTROL **Table**]** list.
   
   1. Drag the tables that you want to use on the canvas.

   You can now work with the data from the data view tables to build your reports and visualizations.

   See [Connect Tableau to Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/tableau) for more information. See also [BI extension use cases](/help/use-cases/data-views/bi-extension-usecases.md) for a detailed example.

+++

+++ Looker

1. Look up the details of your PostgresSQL credentials in Adobe Experience Platform:

   1. Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

   1. Select **[!UICONTROL **Credentials**]** from the top bar.

   1. Select the `cja` database for your sandbox from the list of databases in the **[!UICONTROL Database]** drop-down menu. For example `prod:cja`.

   1. Use ![Copy](assets/Smock_Copy_18_N.svg) to copy each of the Postgres credentials parameters ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], and others) when needed in Looker.

1. In Looker:

   1. Select **[!UICONTROL Admin]** from the left rail.
   1. Select **[!UICONTROL Connections]**.
   1. Select **[!UICONTROL Add Connection]**.
   1. In the **[!UICONTROL Connect your database to Looker]** screen, paste the appropriate values when you set up your new connection. Ensure you select **[!UICONTROL PostgreSQL 9.5+]** as the dialect.
   1. Select **[!UICONTROL Test]** to test your connection.
   1. When successful, select **[!UICONTROL Update]** to save your connection.

   You can now work with the data from the data view tables to build your reports and visualizations.

   See [Connect Looker to Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/looker) for more information. See also [BI extension use cases](/help/use-cases/data-views/bi-extension-usecases.md) for a detailed example.

+++

+++ Jupyter Noteboook

1. Look up the details of your PostgresSQL credentials in Adobe Experience Platform:

   1. Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

   1. Select **[!UICONTROL **Credentials**]** from the top bar.

   1. Select the `cja` database for your sandbox from the list of databases in the **[!UICONTROL Database]** drop-down menu. For example `prod:cja`.

   1. Use ![Copy](assets/Smock_Copy_18_N.svg) to copy each of the Postgres credentials parameters ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], and others) when needed in Jupyter Notebook.

1. In Jupyter Notebook: 

   1. Ensure you use the required libraries.
   1. Use the appropriate values when setting up and executing the connection.
   1. Test your connection by executing a relevant query.

   When successful, you can work with the data to build your reports and visualizations.

   See [Connect Jupyter Notebook to Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/jupyter-notebook) for more information. See also [BI extension use cases](/help/use-cases/data-views/bi-extension-usecases.md) for a detailed example.

+++

+++ RStudio

1. Look up the details of your PostgresSQL credentials in Adobe Experience Platform:

   1. Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

   1. Select **[!UICONTROL **Credentials**]** from the top bar.

   1. Select the `cja` database for your sandbox from the list of databases in the **[!UICONTROL Database]** drop-down menu. For example `prod:cja`.

   1. Use ![Copy](assets/Smock_Copy_18_N.svg) to copy each of the Postgres credentials parameters ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], and others) when needed in Jupyter Notebook.

1. In RStudio:

   1. Ensure you use the required libraries.
   1. Use the appropriate values when setting up and executing the connection.
   1. Test your connection by executing a relevant query.

   When successful, you can work with the data to build your reports and visualizations.

   See [Connect RStudio to Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/rstudio) for more information. See also [BI extension use cases](/help/use-cases/data-views/bi-extension-usecases.md) for a detailed example (that is using the RPostgres package instead).

+++

See [Connect clients to Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/clients/overview) for an overview of and more information on the various tools available.

See [Use cases](/help/use-cases/data-views/bi-extension-usecases.md) on how to accomplish a number of use cases using the Customer Journey Analytics BI extension.

## Functionality

By default, your data views have a table-safe name generated from their friendly name. For example, the data view named [!UICONTROL My Web Data View] has the view name `my_web_data_view`. You can define a preferred name to use in your BI tool for your data view. See [Data view settings](create-dataview.md#settings) for more information.

If you want to use the data view IDs as the table names, you can add the optional `CJA_USE_IDS` setting to your database name when connecting. For example, `prod:cja?CJA_USE_IDS` shows your data views with names like `dv_ABC123`.

### Data governance

The data governance-related settings in Customer Journey Analytics are inherited from Adobe Experience Platform. The integration between Customer Journey Analytics and Adobe Experience Platform Data Governance allows for labeling of sensitive Customer Journey Analytics data and enforcement of privacy policies.

Privacy labels and policies that were created on datasets consumed by Experience Platform can be surfaced in the Customer Journey Analytics data views workflow. Therefore, data queried using the [!DNL Customer Journey Analytics BI extension] show appropriate warnings or errors when not complying with the privacy labels and policies defined.

### List data views

In the standard PostgreSQL CLI, you can list your views using `\dv`

```sql
prod:all=> \dv
                       List of relations
 Schema |                    Name                    | Type |  Owner             
--------+--------------------------------------------+------+----------
 public | my_web_data_view                           | view | postgres
 public | my_mobile_data_view                        | view | postgres

```

### Nested versus flattened

By default, the schema of your data views uses nested structures, just like the original XDM schemas. The integration also supports the `FLATTEN` option. You can use this option to force the schema for the data views (and any other table in the session) to be flattened. Flattening allows for easier use in BI tools that don't support structured schemas. See [Working with nested data structures in Query Service](https://experienceleague.adobe.com/en/docs/experience-platform/query/key-concepts/flatten-nested-data) for more information.


### Defaults and limitations

The following additional defaults and limitations apply when using the BI Extenion:

* The BI extension requires a row limit for the query results. The default is 50, but you can override this in SQL using `LIMIT n`, where `n` is 1 - 50000.
* The BI extension requires a date range to limit the rows used for calculations. The default is the last 30 days, but you can override this in your SQL `WHERE` clause using the special [`timestamp`](#timestamp) or [`daterange`](#date-range) columns.
* The BI extension requires aggregate queries. You can't use SQL like `SELECT * FROM ...` to get the raw, underlying rows. At a high level, your aggregate queries should use:
  * Select totals using `SUM` and/or `COUNT`.<br/> For example, `SELECT SUM(metric1), COUNT(*) FROM ...`
  * Select metrics broken down by a dimension. <br/>For example, `SELECT dimension1, SUM(metric1), COUNT(*) FROM ... GROUP BY dimension1`
  * Select distinct metric values.<br/>For example, `SELECT DISTINCT dimension1 FROM ...`
  
    See for more details [Supported SQL](#supported-sql).


### Supported SQL

See [Query Service SQL reference](https://experienceleague.adobe.com/en/docs/experience-platform/query/sql/overview) for the full reference on what type of SQL is supported.

See the table below for examples of the SQL you can use.

+++ Examples

<table style="table-layout:auto">
    <thead>
        <tr>
            <th>Pattern</th>
            <th>Example</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Schema discovery </td>
            <td>
                <pre><code>SELECT * FROM dv1 WHERE 1=0</code></pre>
            </td>
        </tr>
        <tr>
            <td>Ranked or Breakdown </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  filterId = '12345'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02' AND
  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))
GROUP BY dim1</code></pre>
            </td>
        </tr>
        <tr>
            <td><code>HAVING</code> clause </td>
            <td>
                <pre><code>SELECT dim1, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1
HAVING m1 > 100</code></pre>
            </td>
        </tr>
        <tr>
            <td>Distinct, top 
dimension values </td>
            <td>
                <pre><code>SELECT DISTINCT dim1 FROM dv1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1</code></pre>
                <pre><code>SELECT dim1 AS dv1
FROM dv1
WHERE `timestamp` >= '2022-01-01' AND `timestamp` < '2022-01-02'
GROUP BY dim1
ORDER BY SUM(metric1)
LIMIT 15</code></pre>
            </td>
        </tr>
        <tr>
            <td>Metric totals </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</code></pre>
            </td>
        </tr>
        <tr>
            <td>Multi-dimension
breakdowns
and top-distincts </td>
            <td>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY dim1, dim2</code></pre>
                <pre><code>SELECT dim1, dim2, SUM(metric1) AS m1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 1, 2
ORDER BY 1, 2</code></pre>
                <pre><code>SELECT DISTINCT dim1, dim2
FROM dv1</code></pre>
            </td>
        </tr>
        <tr>
            <td>Subselect:
Filter additional
results </td>
            <td>
                <pre><code>SELECT dim1, m1
FROM (
  SELECT dim1, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'</br>  GROUP BY dim1
)
WHERE dim1 in ('A', 'B')</code></pre>
            </td>
        </tr>
        <tr>
            <td>Subselect:
Querying across
data views </td>
            <td>
                <pre><code>SELECT key, SUM(m1) AS total
FROM (
  SELECT dim1 AS key, SUM(metric1) AS m1
  FROM dv1
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim1
<br>
  UNION
<br>
  SELECT dim2 AS key, SUM(m1) AS m1
  FROM dv2
  WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  GROUP BY dim2
)
GROUP BY key
ORDER BY total</code></pre>
            </td>
        </tr>
        <tr>
            <td>Subselect: 
Layered source, 
filtering, 
and aggregation </td>
            <td>Layered using subselects:
<pre><code>SELECT rows.dim1, SUM(rows.m1) AS total
FROM (
  SELECT _.dim1,_.m1
  FROM (
    SELECT * FROM dv1
    WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
  ) _
  WHERE _.dim1 in ('A', 'B', 'C')
) rows
GROUP BY 1
ORDER BY total</code></pre>
Layers using CTE WITH:
<pre><code>WITH rows AS (
  WITH _ AS (
    SELECT * FROM data_ares
    WHERE `timestamp` BETWEEN '2021-01-01' AND '2021-02-01'
  )
  SELECT _.item, _.units FROM _
  WHERE _.item IS NOT NULL
)
SELECT rows.item, SUM(rows.units) AS units
FROM rows WHERE rows.item in ('A', 'B', 'C')
GROUP BY rows.item</code></pre>
        </td>
        </tr>
        <tr>
            <td>Selects where the
metrics come before
 or are mixed with
the dimensions </td>
            <td>
                <pre><code>SELECT SUM(metric1) AS m1, dim1
FROM dv1
WHERE `timestamp` BETWEEN '2022-01-01' AND '2022-01-02'
GROUP BY 2</code></pre>
            </td>
        </tr>
    </tbody>
</table>

+++

### Dimensions

You can select any of the dimensions available by default or defined in the data view. You select a dimension by its ID.

### Metrics

The metrics available to select are:

* Any of the metrics available by default;
* Defined in the data view;
* Calculated metrics that are compatible with the data view that the user has access to.  
 
You select a metric by its ID wrapped in a `SUM(metric)` expression just like you would do with other SQL sources.

You can use:

* `SELECT COUNT(*)` or `COUNT(1)` to get the occurrences metric. 
* `SELECT COUNT(DISTINCT dimension)` or `SELECT APPROX_COUNT_DISTINCT(dimension)` to count the approximate distinct values of a dimension. See details in [Counting distinct values](#counting-distinct-values).
* [Inline calculations](#inline-calculations) to combine metrics on the fly and/or doing math on them.

#### Counting distinct values

Due to the underlying nature of how Customer Journey Analytics works, the only dimension you can get an exact distinct count for is the `adobe_personid` dimension. The following SQL statements `SELECT COUNT(DISTINCT adobe_personid)` or `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` return the value of the default persons metric, which is the count of distinct people. For other dimensions, an approximate distinct count is returned.

#### Conditional metrics

You can embed an `IF` or `CASE` clause in the `SUM` or `COUNT` functions to add additional segmenting that is specific to a selected metric. Adding these clauses is similar to applying a segment to a metric column in a Workspace report table.

Examples:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN metric1 END) AS m1
```

#### Inline calculations

You can apply additional math to metric expressions in your `SELECT`. This math can be used instead of defining the math in a calculated metric. The following table lists what types of expressions are supported.

| Operator or Function | Details |
|---|---|
|`+`, `-`, `*`, `/`, and `%` | Add, subtract, multiply, divide, and modulous/remainder |
| `-X` or `+X` | Changing the sign or a metric where X is the metric expression |
| `PI()` | π constant |
|`POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, and `TANH` | Unary math functions |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binary math functions |

{style="table-layout:auto"}

### Special columns

#### Timestamp

The `timestamp` special column is used to provide the date ranges for the query. A date range can be defined with a `BETWEEN` expression or a pair of `timestamp` `>`, `>=`, `<`, `<=` checks `AND`ed together.
The `timestamp` is optional and if no full range is provided, defaults are used:

* If only a minimum is provided (`timestamp > X` or ` timestamp >= X`), the range is from X to now. 
* If only a max is provided (`timestamp < X` or `timestamp <= X`), the range is from X minus 30 days to X. 
* If nothing is provided, the range is from now minus 30 days to now.

The timestamp range is converted to a date range global segment in the RankedRequest.
The timestamp field can also be used in date/time functions to parse or truncate the event timestamp.

#### Date range

The `daterange` special column works similar to `timestamp`; however the segmenting is limited to full days. The `daterange` is also optional and has the same range defaults as `timestamp`.
The `daterange` field can also be used in date/time functions to parse or truncate the event date.

The `daterangeName` special column can be used to segment your query using a named date range like `Last Quarter`.

>[!NOTE]
>
>Power BI is not supporting `daterange` metrics that are less than a day (hour, 30 minute, 5 minute, etc.).
>

#### Segment ID

The `filterId` special column is optional and is used to apply an externally defined segment to the query. Applying an externally defined segment to a query is similar to dragging a segment on a panel in Workspace. Multiple segment IDs can be used by `AND`-ing them.

Along with `filterId`, you can use `filterName` to use a segment's name instead of ID.

### Where clause

The `WHERE` clause is handled in three steps:

1. Find the date range from the `timestamp`, `daterange`, or `daterangeName` special fields.
  
1. Find any externally defined `filterId`s or `filterName`s to include in the segment.

1. Turn the remaining expressions into ad-hoc segments.

The handling is done by parsing the first level of `AND`s in the `WHERE` clause. Each top-level `AND`-ed expression must match one of the above. Anything deeper than the first level of `AND`s, or, if the `WHERE` clause uses `OR`s at the top level, is handled as an ad-hoc segment.

### Sorting order

By default, the query sorts the results by the first selected metric in descending order. You can overwrite the default sorting order by specifying `ORDER BY ... ASC` or `ORDER BY ... DESC`. If you use `ORDER BY`, you must specify `ORDER BY` on the first selected metric.  

You can also flip the order by using `-` (minus) in front of the metric. Both statements below result in the same ordering:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### General function support

| Function | Example | Details |
|---|---|---|
| [Cast](https://spark.apache.org/docs/latest/api/sql/index.html#cast) |``CAST(`timestamp` AS STRING)`` or <br/> `` `timestamp`::string ``  | Type casting is not currently supported, but no error is thrown. The `CAST` function is ignored. |
| [Timestamp](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Parse a time string as a timestamp for use within a `WHERE` clause. |
| [To timestamp](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Parse a time string as a timestamp for use within a `WHERE` clause, optionally providing a format for that time string. |
| [Date](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Parse a date string as a timestamp for use within a `WHERE` clause. |
| [To date](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Parse a date string as a timestamp for use within a `WHERE` clause, optionally providing a format for that date string. |

{style="table-layout:auto"}

### Dimension function support

These functions can be used on dimensions in the `SELECT`, `WHERE` clause, or in conditional metrics.

**String functions**

| Function | Example | Details |
|---|---|---|
| [Lower](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generate a dynamic dimension identity on the passed in field. |

{style="table-layout:auto"}

**Date-time functions**

| Function | Example | Details |
|---|---|---|
| [Year](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [Month](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [Day](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [Day of week](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value as you need the number not the friendly name. |
| [Day of year](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [Week](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [Quarter](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [Hour](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value as you need the number not the friendly name. |
| [Minute](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [Extract](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value for some parts of this function as you need the number not the friendly name.<br/>Supported parts are:<br>- Keywords: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strings:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`', `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, or `'MINUTE'`.|
| [Date (part)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value for some parts of this function as you need the number not the friendly name.<br/>Supported string parts are: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`', `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, or `'MINUTE'`. |
| [Date (truncated)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generate a dynamic dimension identity on the passed in field.<br/>Supported string granularities are: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`', `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, or `'MINUTE'`. |

{style="table-layout:auto"}

### Partial Support

Some SQL functionality is only partially supported with the BI extension and does not return the same results you see with other databases.  This specific functionality is used in SQL generated by various BI tools, for which the BI extension does not have an exact match. As a result, the BI extension focuses on a limited implementation that covers the minimum BI tool usage without throwing errors. See the table below for more details.

| Function | Example | Details |
|---|---|---|
| MIN() & MAX() |``MIN(daterange)`` or <br/> ``MAX(daterange)`` | `MIN()` on `timestamp`, `daterange`, or any of the `daterangeX` like `daterangeday` will return 2 years ago.<br/><br/> `MAX()` on `timestamp`, `daterange`, or any of the `daterangeX` like `daterangeday` will return the current date/time.<br/><br/>`MIN()` or `MAX()` on any other dimmension, metric, or expression will return 0. |

{style="table-layout:auto"}
