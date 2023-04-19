---
title: Custom field Url Parse function
description: Description of the custom field Url Parse function.
solution: Customer Journey Analytics
feature: Data Views
---

# Url Parse

This function provides the ability to parse out different parts of a URL including the host, path or query parameters.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>Sing field</li><li>Parsing option<ul><li>Get protocol</li><li>Get host</li><li>Get path</li><li>Get query value<ul><li>Query param</li></ul></li><li>Get hash value</li></ul></li></ul></li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case 1

A customer would like to get only the referring domain from the referrer and use that as part of the marketing channel's set of rules.

Assumptions:

- Dataset has a field with the referring URL details.

### Data

| BEFORE:<br/>Referring URL | AFTER: New custom field<br/>Referrer Domain
|----|----|
| <https://www.google.com/> | www.google.com |
| <https://duckduckgo.com/> | duckduckgo.com |
| <https://t.co/> | t.co |
| <https://l.facebook.com/>| l.facebook.com |

{style="table-layout:auto"}

### Screenshot

![Url Parse 1](../assets/url-parse-1.png)


## Use Case 2

A customer would like to use the value of a query string as part of the output of a derived tracking code report. They would like to pull the value out of the 'cid' parameter.

Assumption: 

- Dataset has a field for Page URL that contains query string parameters.

### Data

| BEFORE:<br/>Page URL | AFTER: New custom field<br/>Query String CID
|----|----|
| <https://www.adobe.com/?cid=abc123> | abc123 |
| <https://www.adobe.com/?em=email1234&cid=def123> | def123 |
| <https://www.adobe.com/landingpage?querystring1=test&test2=1234&cid=xyz123> | xyz123 |

{style="table-layout:auto"}

### Screenshot

![Url Parse 2](../assets/url-parse-2.png)

