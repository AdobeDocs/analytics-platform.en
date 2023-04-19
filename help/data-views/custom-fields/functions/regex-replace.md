---
title: Custom field Regex Replace function
description: Description of the custom field Regex Replace function.
solution: Customer Journey Analytics
feature: Data Views
---

# Regex Replace

This function replaces a field or portion of a field based on a regular expression.

## Input(s) / Operators / Output

| Input Data Type | Input(s) | Included Operators | Output(s) |
|---|---|---|---|
| <ul><li>String</li></ul> | <ul><li>Sing field</li><li>Regex definition</li><li>Output definition</li></ul> | <p>N/A</p> | <p>New custom field</p> |

{style="table-layout:auto"}

## Use Case

A customer would like to grab a potion of a URL and use that as a unique page identifier to analyze their traffic. They will use `[^/]+(?=/$|$)` for the match on the end of the URL. Output pattern would be `$1`.


### Data

| BEFORE:<br/>Example URLs | AFTER: New custom field<br/>Page Name
|----|----|
| <https://business.adobe.com/products/analytics/adobe-analytics-benefits.html> | adobe-analytics-benefits.html |
| <https://business.adobe.com/products/analytics/adobe-analytics.html> | adobe-analytics.html |
| <https://business.adobe.com/products/experience-platform/customer-journey-analytics.html> | customer-journey-analytics.html |
| <https://business.adobe.com/products/experience-platform/adobe-experience-platform.html>| adobe-experience-platform.html |

### Screenshot

Pending availability in the UI.
