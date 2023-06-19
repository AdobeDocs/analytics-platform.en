---
title: SQL Connector
description: Learn how you can use Query Service, Power BI and/or Tableau to access Data Views using the SQL Connector.
solution: Customer Journey Analytics
feature: Data Views
hide: yes
hidefromtoc: yes
badgeCJASQLConnector: label="New Feature" type="Positive"
exl-id: 80feadef-3e2d-4901-8c82-25c56d296e9f
---
# SQL Connector

{{release-limited-testing}}

The [!DNL Customer Journey Analytics SQL Connector] enables SQL access to the [data views](./data-views.md) that you have defined in Customer Journey Analytics. Your data engineers and analysts might be more familiar with Power BI, Tableau, or other business intelligence and visualization tools (further referred to as BI tools). They can now create reporting and dashboards based on the same data views that Customer Journey Analytics users are using when creating their Analysis Workspace projects.

Adobe Experience Platform [Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=en) is the SQL interface to data available in the data lake of Experience Platform. With the [!DNL Customer Journey Analytics SQL Connector] enabled, the functionality of [!DNL Query Service] is extended to see your Customer Journey Analytics data views as tables or views in a [!DNL Query Service] session. As a result, business intelligence tools that use [!DNL Query Service] as their PostgresSQL interface benefit seamlessly from this extended functionality.

The main benefits are:

-   No need to recreate an equivalent representation of Customer Journey Analytics data views within the BI tool itself. <br/>See [Data view](data-views.md) for more information on the functionality of Data views to understand what must be recreated.<br/>

-   Greater consistency in reporting and analysis between BI tools and Customer Journey Analytics.
  
-   Combine Customer Journey Analytics data with other data sources already available in BI tools.

## Prerequisites

To use this functionality, you have to 

<!---   Enable the [!UICONTROL Customer Journey Analytics SQL Connector] in your Experience Platform organization. -->

-   Configure the functionality for the relevant product profiles, user groups and/or individual users.<br/>
    Users must have access to:
    - Experience Platform Query Service, 
    - Customer Journey Analytics  Workspace projects, and
    - Customer Journey Analytics Data views they want to use.

-   Use expiring on non-expiring credentials to connect BI tools to the Customer Journey Analytics SQL Connector. Thr [Credentials guide](https://experienceleague.adobe.com/docs/experience-platform/query/ui/credentials.html?lang=en) provides more information on setting expiring credentials or non-expiring credentials.

See [Access Control](../admin/cja-access-control.md) in the Customer Journey Analytics Administration section for additional information.


## Usage

To use the [!DNL Customer Journey Analytics SQL Connector] functionality, you can either use SQL directly or use the drag and drop experience available in the specific BI tool. 

### SQL

You can use the functionality directly in SQL statements using either the Query Editor or a standard PostgresSQL command-line interface (CLI) client.

+++ Query Editor

In the Experience Platform UI:

1.  Select **[!UICONTROL **Queries**]** from **[!UICONTROL **DATA MANAGEMENT**]** in the left rail.

2.  Select ![Create Query](assets/Smock_AddCircle_18_N.svg) **[!UICONTROL **Create query**]**.

3.  To execute the query, type your SQL statement and select the ![Play](assets/Smock_Play_18_N.svg) button (or press SHIFT + ENTER).

+++


+++ PostgresSQL CLI

1.  In the Experience Platform UI, look up and copy your PostgresSQL credentials:

    1.  Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

    2.  Select **[!UICONTROL **Credentials**]** from the top bar.

    3.  To copy the connect string, use ![Copy](assets/Smock_Copy_18_N.svg) in the **[!UICONTROL **PSQL command**]** section.

2.  Open your PostgresSQL CLI.

3.  To log in and start executing your queries, paste the connect string in the PostgresSQL CLI.
    
+++

See [Query Editor UI guide](https://experienceleague.adobe.com/docs/experience-platform/query/ui/user-guide.html?lang=en) for more information.


### BI Tools

Currently, the Customer Journey Analytics SQL Connector is supported and tested for Power BI and Tableau only. Other BI tools using the PSQL interface might work as well but are not yet supported officially.

+++ Power BI

1.  In the Adobe Experience Platform UI, look up the details of your PostgresSQL credentials.

    1.  Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

    2.  Select **[!UICONTROL **Credentials**]** from the top bar.

    3.  Use ![Copy](assets/Smock_Copy_18_N.svg) to copy each of the Postgres credentials parameters ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], and others) when needed in Power BI.

2.  In Power BI:

    1.  In the main window, select **[!UICONTROL **Get data**]** from the top toolbar.
   
    2.  Select **[!UICONTROL **More...**]** in the left rail.

    3.  In the **Get Data** screen, search for `PostgresSQL` and select the **[!UICONTROL **PostgresSQL database**]** from the list.

    4.  In the **[!UICONTROL **PostgressSQL database**]** dialog:

        1.  Paste **[!UICONTROL **Host**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into **[!UICONTROL **Server**]** text field.

        2.  Paste **[!UICONTROL **Database**]** parameter from Experience Platform Queries [!UICONTROL Credentials] in **[!UICONTROL **Database**]** text field.
        
            Add `?FLATTEN` to the **[!UICONTROL **Database**]** parameter, so it reads like `prod:all?FLATTEN` for example. See [Flatten nested data structures for use with third-party BI tools](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) for more information.

        3.  When prompted for **[!UICONTROL **Data Connectivity**]** mode, select **[!UICONTROL **DirectQuery**]** to ensure that the data structures are flattened properly.

        4.  You are prompted for **[!UICONTROL **Username**]** and **[!UICONTROL **Password**]**. Use the equivalent parameters from Experience Platform Queries [!UICONTROL Credentials].


    5.  After successful login, the Customer Journey Analytics Data View tables appear in Power BI's **[!UICONTROL **Navigator**]**. Data View tables are identified by using `dv_` in their names.


    6.  Select the data view tables that you want to use and select **[!UICONTROL **Load**]**.

    All dimensions and metrics associated with one or more selected tables appear in the right pane, ready to be used in your visualizations.

    See [Connect Power BI to Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/power-bi.html?lang=en) for more information.

+++

+++Tableau

1.  In the Experience Platform UI, look up the details of your PostgresSQL credentials.

    1.  Select **[!UICONTROL **Queries**]** from the left rail (under **[!UICONTROL **DATA MANAGEMENT**]**).

    2.  Select **[!UICONTROL **Credentials**]** from the top bar.

    3.  Use ![Copy](assets/Smock_Copy_18_N.svg) to copy each of the Postgres credentials parameters ([!UICONTROL Host], [!UICONTROL Port], [!UICONTROL Database], [!UICONTROL Username], and others) when needed in Tableau.

2.  In Tableau:

    1.  Select **[!UICONTROL **More**]** from **[!UICONTROL **To a Server**]** in the left rail.

    2.  Select **[!UICONTROL **PostgresSQL**]** from the list.

    3.  In the [!UICONTROL PostgresSQL] dialog:

        1.  Paste **[!UICONTROL **Host**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into **[!UICONTROL **Server**]** text field.

        2.  Paste **[!UICONTROL **Port**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into **[!UICONTROL **Port**]** text field.

        3.  Paste **[!UICONTROL **Database**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into **[!UICONTROL **Database**]** text field.

            Add `%3FFLATTEN` to the **[!UICONTROL **Database**]** parameter, so it reads like `prod:all%3FFLATTEN` for example. See [Flatten nested data structures for use with third-party BI tools](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) for more information.

        4.  Select **[!UICONTROL **Username and Password**]** from **[!UICONTROL **Authentication**]** list.

        5.  Paste **[!UICONTROL **Username**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into **[!UICONTROL **Username**]** text field.

        6.  Paste **[!UICONTROL **Password**]** parameter from Experience Platform Queries [!UICONTROL Credentials] into **[!UICONTROL **Password**]** text field.

        7.  Select **[!UICONTROL **Sign In**]**.

    4.  Customer Journey Analytics data views show up as tables in the **[!UICONTROL **Table**]** list. Data view tables are prefixed with `dv_`.
   
    5.  Drag the tables that you want to use on the canvas.

    You can now work with the data from the data view tables to build your reports and visualizations.

    See [Connect Tableau to Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/tableau.html?lang=en) for more information.

+++

See [Connect clients to Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/clients/overview.html?lang=en) for an overview of and more information on the various tools available.

## Functionality

By default, your data views have a table-safe name generated from their friendly name. For example, the data view named [!UICONTROL My Web Data] has the view name `dv_my_web_data`.  

If you want to use the data view IDs as the table names, you can add the optional `CJA_USE_IDS` setting to your database name when connecting. For example, `prod:all?CJA_USE_IDS` shows your data views with names like `dv_ABC123`.

### Data governance

The data governance-related settings in Customer Journey Analytics are inherited from Adobe Experience Platform. The integration between Customer Journey Analytics and Adobe Experience Platform Data Governance allows for labeling of sensitive Customer Journey Analytics data and enforcement of privacy policies.

Privacy labels and policies that were created on datasets consumed by Experience Platform can be surfaced in the Customer Journey Analytics data views workflow. Therefore, data queried using the Customer Journey Analytics SQL Connector show appropriate warnings or errors when not complying with the privacy labels and policies defined.

### List Data Views

In the standard PostgreSQL CLI, you can list your views using `\dv`

```sql
prod:all=> \dv
                                     List of relations
 Schema |                              Name                              | Type |  Owner             
--------+----------------------------------------------------------------+------+----------
 public | dv_adobe_analytics_spa                                         | view | postgres
 public | dv_adobe_analytics_spa_cja_adobe_users_only_                   | view | postgres
 public | dv_adobe_analytics_spa_cja_customers_only_                     | view | postgres
 public | dv_adobe_analytics_spa_core_aa_only_                           | view | postgres
 public | dv_adobe_analytics_spa_trad_aa_customers_only_                 | view | postgres
 public | dv_cja_audit_logs                                              | view | postgres
 public | dv_cja_connections_ui_prod_analytics_format_                   | view | postgres
 public | dv_cja_for_adobe_spark_usage                                   | view | postgres
 public | dv_cja_new_dimesnions                                          | view | postgres
 public | dv_cja_test_dimensions                                         | view | postgres
 public | dv_cja_usage_account_based_customers_only_                     | view | postgres
 public | dv_combined_trad_aa_apps                                       | view | postgres
 public | dv_customer_journey_analytics_sc_demo_users_                   | view | postgres

```

### Nested versus flattened

By default, the schema of your data views uses nested structures, just like the original XDM schemas. The integration also supports the `FLATTEN` option. You can use this option to force the schema for the data views (and any other table in the session) to be flattened. Flattening allows for easier use in BI tools that don't support structured schemas. See [Working with nested data structures in Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/essential-concepts/flatten-nested-data.html?lang=en) for more information.

### Supported SQL

See [Query Service SQL reference](https://experienceleague.adobe.com/docs/experience-platform/query/sql/overview.html?lang=en) for the full reference on what type of SQL is supported.

See table below for examples of the SQL you can use.

+++ Examples

| Pattern | Example |
|---|---|
| Schema discovery | <pre>SELECT * FROM dv1 WHERE 1=0</pre> |
| Ranked / Breakdown | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02' AND<br/>  filterId = '12345'<br/>GROUP BY dim1</pre><pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02' AND<br/>  AND (dim2 = 'A' OR dim3 IN ('X', 'Y', 'Z'))<br/>GROUP BY dim1</pre> |
| HAVING clause | <pre>SELECT dim1, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>GROUP BY dim1<br/>HAVING m1 > 100</pre> |
| Distinct, top <br/>dimension values | <pre>SELECT DISTINCT dim1 FROM dv1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>GROUP BY dim1</pre><pre>SELECT dim1 AS dv1<br/>FROM dv1<br/>WHERE \`timestamp\` >= '2022-01-01' AND \`timestamp\` < '2022-01-02'<br/>GROUP BY dim1<br/>ORDER BY SUM(metric1)<br/>LIMIT 15</pre> |
| Metric totals | <pre>SELECT SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'</pre> |
| Multi-dimension<br/>breakdowns<br/>and top-distincts | <pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>GROUP BY dim1, dim2</pre><pre>SELECT dim1, dim2, SUM(metric1) AS m1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>GROUP BY 1, 2<br/>ORDER BY 1, 2</pre><pre>SELECT DISTINCT dim1, dim2<br/>FROM dv1</pre> |
| Sub select:<br/>Additional result<br/>filtering | <pre>SELECT dim1, m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'</br>  GROUP BY dim1<br/>)<br/>WHERE dim1 in ('A', 'B')</pre> |
| Sub select:<br/>Joining with<br/>dataset not in<br/>Customer Journey Analytics | <pre>SELECT b.key, a.dim1, a.m1<br/>FROM (<br/>  SELECT dim1, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>  GROUP BY dim1<br/>) a<br/>LEFT JOIN lookups b ON a.dim1 = b.key</pre> |
| Sub select:<br/>Querying across<br/>data-views | <pre>SELECT key, SUM(m1) AS total<br/>FROM (<br/>  SELECT dim1 AS key, SUM(metric1) AS m1<br/>  FROM dv1<br/>  WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>  GROUP BY dim1<br/><br/>  UNION<br/><br/>  SELECT dim2 AS key, SUM(m1) AS m1<br/>  FROM dv2<br/>  WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>  GROUP BY dim2<br/>GROUP BY key<br/>ORDER BY total</pre> |
| Sub select: <br/>Layered source, <br/>filtering, <br/>and aggregation | Layered using subselects:<br><pre>SELECT rows.dim1, SUM(rows.m1) AS total<br/>FROM (<br/>  SELECT \_.dim1,\_.m1<br/>  FROM (<br/>    SELECT \* FROM dv1<br/>    WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>  ) \_<br/>  WHERE \_.dim1 in ('A', 'B', 'C')<br/>) rows<br/>GROUP BY 1<br/>ORDER BY total</pre><br/>Layers using CTE WITH:<br/><pre>WITH rows AS (<br/>  WITH \_ AS (<br/>    SELECT * FROM data_ares<br/>    WHERE \`timestamp\` BETWEEN '2021-01-01' AND '2021-02-01'<br/>  )<br/>  SELECT _.item, _.units FROM _<br/>  WHERE _.item IS NOT NULL<br/>)<br/>SELECT rows.item, SUM(rows.units) AS units<br/>FROM rows WHERE rows.item in ('A', 'B', 'C')<br/>GROUP BY rows.item</pre> |
| Selects where the<br/>metrics come before<br/> or are mixed with<br/>the dimensions | <pre>SELECT SUM(metric1) AS m1, dim1<br/>FROM dv1<br/>WHERE \`timestamp\` BETWEEN '2022-01-01' AND '2022-01-02'<br/>GROUP BY 2</pre> |

{style="table-layout:auto"}

+++

### Dimensions

You can select any of the dimensions available by default or defined in the data view. You select a dimension by its ID.

### Metrics

The metrics available to select are: 

-   any of the metrics available by default,
  
-   defined in the data view,
  
-   calculated metrics that are compatible with the Data View that the user has access to.  
 
You select a metric by its ID wrapped in a `SUM(metric)` expression just like you would do with other SQL sources.

You can use:

-   `SELECT COUNT(*)` or `COUNT(1)` to get the occurrences metric.
  
-   `SELECT COUNT(DISTINCT dimension)` or `SELECT APPROX_COUNT_DISTINCT(dimension)` to count the approximate distinct values of a dimension. See details in [Counting Distincts](#counting-distincts).
  
-   [Inline Calculations](#inline-calculations) to combine metrics on the fly and/or doing math on them.

#### Counting Distincts

Due to the underlying nature of how Customer Journey Analytics works, the only dimension you can get an exact distinct count for is the `adobe_personid` dimension. The following SQL statements `SELECT COUNT(DISTINCT adobe_personid)` or `SELECT APPROX_COUNT_DISTINCT(adobe_personid)` return the value of the default persons metric which is the count of distinct people. For other dimensions, an approximate distinct count is returned.

#### Conditional Metrics

You can embed an `IF` or `CASE` clause in the `SUM` or `COUNT` functions to add additional filtering that is specific to a selected metric. Adding these clauses is similar to applying a filter to a metric column in a Workspace report table.

Examples:

```sql
SUM(IF(dim1 = 'X' AND dim2 = 'A', metric1, 0)) AS m1
```

```sql
SUM(CASE WHEN dim1 = 'X' AND dim2 = 'A' THEN METRIC1 END) AS m1
```

#### Inline Calculations

You can apply additional to metric expressions in your `SELECT` instead of having the math defined in a calculated metric. The following table lists what type of expressions are supported.

| Operator or Function | Details |
|---|---|
|`+`, `-`, `*`, `/`, and `%` | Add, subtract, multiply, divide, and modulous/remainder |
| `-X` or `+X` | Changing the sign or a metric where X is the metric expression |
| `PI()` | π constant |
|`POSITIVE`, `NEGATIVE`, `ABS`, `FLOOR`, `CEIL`, `CEILING`, `EXP`, `LN`, `LOG10`, `LOG1P`, `SQRT`, `CBRT`, `DEGREES`, `RADIANS`, `SIN`, `COS`, `TAN`, `ACOS`, `ASIN`, `ATAN`, `COSH`, `SINH`, and `TANH` | Unary math functions |
| `MOD`, `POW`, `POWER`, `ROUND`, `LOG` | Binary math functions |

{style="table-layout:auto"}

### Special Columns

**Timestamp**

The `timestamp` special column is used to provide the date ranges for the query. A date range can be defined with a `BETWEEN` expression or a pair of `timestamp` `>`, `>=`, `<`, `<=` checks `AND`ed together.
The `timestamp` is optional and if no full range is provided, defaults are used:

-   If only a minimum is provided (`timestamp > X` or ` timestamp >= X`), the range is from X to now.
  
-   If only a max is provided (`timestamp < X` or `timestamp <= X`), the range is from X-30 days to X.
  
-   If nothing is provided the range is from now-30 days to now.

The timestamp range is converted to a date-range global filter in the RankedRequest.
The timestamp field can also be used in Date-Time functions to parse, truncate the event timestamp.

**Date range**

The `daterange` special column works similar to  `timestamp`, however the filtering is limited to full days. The `daterange` is also optional and has the same range defaults as `timestamp`.
The `daterange` field can also be used in Date-Time Functions to parse, truncate the event date.

**filterId**

The `filterId` special column is optional and is used to apply an externally defined filter to the query. Applying an externally defined filter to a query is similar to dragging a filter on a panel in Workspace. Multiple filter IDs can be provided by `AND`-ing them.

### WHERE Clause

The WHERE clause is handled in three steps:

1.  Find the date range from the `timestamp` special field.
  
2.  Find any externally defined `filterId`s to include in the filtering.

3.  Turn the remaining expressions into ad-hoc filters.

The handling is done by parsing the first level of `AND`s in the `WHERE` clause. Each top-level `AND`ed expression must match one of the above. Anything deeper than the first level of `AND`s, or, if the `WHERE` clause uses `OR`s at the top level, is handled as an ad-hoc filter.

### ORDER BY

By default, the query sorts the results by the first selected metric in descending order. You can overwrite the default sorting order by specifying `ORDER BY ... ASC` or `ORDER BY ... DESC`. If you use `ORDER BY`, you must specify `ORDER BY` on the first selected metric.  

You can also flip the order by using `-` (minus) in front of the metric. Both statements below result in the same ordering:

```sql
ORDER BY metric1 ASC
```

```sql
ORDER BY -metric1 DESC
```

### General Function Support

| Function | Example | Details |
|---|---|---|
| [CAST(column AS type)](https://spark.apache.org/docs/latest/api/sql/index.html#cast) |``CAST(`timestamp` AS STRING)`` or <br/> `` `timestamp`::string ``  | Type casting is not currently supported, but no error is thrown. The `CAST` function is ignored. |
| [TIMESTAMP(timeString)](https://spark.apache.org/docs/latest/api/sql/index.html#timestamp) | `` WHERE `timestamp` >= TIMESTAMP('2022-01-01 00:00:00') AND   `timestamp` < TIMESTAMP('2022-01-02 00:00:00') `` | Parse a time string as a timestamp for use within a `WHERE` clause. |
| [TO_TIMESTAMP(timeString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_timestamp) | `` WHERE `timestamp` >= TO_TIMESTAMP('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_TIMESTAMP('01/02/2022', 'MM/dd/yyyy') `` | Parse a time string as a timestamp for use within a `WHERE` clause, optionally providing a format for that time string. |
| [DATE(dateString)](https://spark.apache.org/docs/latest/api/sql/index.html#date) | `` WHERE `timestamp` >= DATE('2022-01-01') AND `timestamp` < DATE('2022-01-02') `` | Parse a date string as a timestamp for use within a `WHERE` clause. |
| [TO_DATE(dateString, formatString)](https://spark.apache.org/docs/latest/api/sql/index.html#to_date) | `` WHERE `timestamp` >= TO_DATE('01/01/2022', 'MM/dd/yyyy') AND `timestamp` < TO_DATE('01/02/2022', 'MM/dd/yyyy') `` | Parse a date string as a timestamp for use within a `WHERE` clause, optionally providing a format for that date string. |

{style="table-layout:auto"}

### Dimension Function Support

These functions can be used on dimensions in the `SELECT`, `WHERE` clause, or in conditional metrics.

**String functions**

| Function | Example | Details |
|---|---|---|
| [LOWER(stringDimension)](https://spark.apache.org/docs/latest/api/sql/index.html#lower) | ``SELECT LOWER(name) AS lower_name`` | Generate a dynamic dimension identity on the passed in field. |

{style="table-layout:auto"}

**Date-Time functions**

| Function | Example | Details |
|---|---|---|
| [YEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#year) | ``SELECT YEAR(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [MONTH(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#month) | ``SELECT MONTH(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [DAY(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#day) | ``SELECT DAY(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [DAYOFWEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofweek) | ``SELECT DAYOFWEEK(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value as you need the number not the friendly name. |
| [DAYOFYEAR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#dayofyear) | ``SELECT DAYOFYEAR(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [WEEK(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#week) | ``SELECT WEEK(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [QUARTER(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#quarter) | ``SELECT QUARTER(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [HOUR(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#hour) | ``SELECT HOUR(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value as you need the number not the friendly name. |
| [MINUTE(date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#minute) | ``SELECT MINUTE(`timestamp`)`` | Generate a dynamic dimension identity on the passed in field. |
| [EXTRACT(part FROM date or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#extract) | ``SELECT EXTRACT(MONTH FROM `timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value for some parts of this function as you need the number not the friendly name.<br/>Supported parts are:<br>- Keywords: `YEAR`, `MONTH`, `DAYOFMONTH`, `DAYOFWEEK`, `DAYOFYEAR`, `WEEK`, `QUARTER`, `HOUR`, `MINUTE`.<br/>- Strings:  `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`', `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, or `'MINUTE'`.|
| [DATE_PART(part, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_part) | ``SELECT DATE_PART('month', `timestamp`)`` | Generate a dynamic dimension identity on the passed in field. Use the item ID instead of the value for some parts of this function as you need the number not the friendly name.<br/>Supported string parts are: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`', `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, or `'MINUTE'`. |
| [DATE_TRUNC(granularity, date, or date-time)](https://spark.apache.org/docs/latest/api/sql/index.html#date_trunc) | ``SELECT DATE_TRUNC('quarter', `timestamp`)`` | Generate a dynamic dimension identity on the passed in field.<br/>Supported string granularities are: `'YEAR'`, `'Y'`, `'MONTH'`, `'M'`, `'DAYOFMONTH'`, `'DAY'`, `'D'`, `'DAYOFWEEK'`, `'DOW'`, `'DAYOFYEAR'`, `'DOY'`, `'WEEK'`, `'WOY`', `'W'`, `'QUARTER'`, `'QOY'`, `'Q'`, `'HOUR'`, or `'MINUTE'`. |

{style="table-layout:auto"}
