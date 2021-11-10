---
title: Filter operators
description: Determine how a component interacts with a value within a filter.
exl-id: 744c7450-d6e9-4f78-a306-fe725ea0fa18
---
# Filter operators

The Filter builder lets you compare and constrain values using selected operators. There are two categories of operators: [!UICONTROL Standard] and [!UICONTROL Distinct Count].

## Standard operators

| Operator | Description |
| --- | --- |
| equals | Returns items that match exactly for a numeric or string value. If using wildcard characters, use the "matches" operator. |
| does not equal | Returns all items that do not contain the exact match of the value entered.  If using wildcard characters, use the "does not match" operator. |
| contains | Returns items that compare to the substrings of the values entered. For example, if the rule for a string dimension contains `"Search"`, it matches any page that has the substring `"Search"` in it, including `"Search Results"`, `"Search"`, and `"Searching"`. This operator is case-sensitive. |
| does not contain | All items that match the entered value are excluded from results. For example, if the rule for a string dimension does not contain `"Search"`, then it excludes any page that has the substring `"Search"` in it, including `"Search Results"`, `"Search"`, and `"Searching"`. |
| contains all of | Returns items that include all substrings (separated by a space) in any order. For example, entering `"Search Results"` with this operator would match `"Search Results"` and `"Results of Search"`, but not `"Search"` or `"Results"` independently. This operator supports up to 100 words delimited by spaces. |
| does not contain all of | All items that match every entered value are excluded from results. For example, entering `"Search Results"` with this operator would exclude `"Search Results"` and `"Results of Search"`, but not `"Search"` or `"Results"`. This operator supports up to 100 words delimited by spaces. |
| contains any of | Returns items that contain any of the specified substrings. For example, entering `"Search Results"` with this operator would match `"Search Results"`, `"Results of Search"`, `"Search"`, and `"Results"`. This operator supports up to 100 words delimited by spaces. |
| does not contain any of | All items that match any substring are excluded from results. For example, entering `"Search Results"` would exclude `"Search Results"`, `"Results of Search"`, `"Search"`, and `"Results"`. This operator supports up to 100 words delimited by spaces. |
| starts with | Returns items that start with the character or strings of the value entered. |
| does not start with | Returns all items that do not start with the characters or strings of the values entered. |
| ends with | Returns items that end with the character or strings of the value entered. |
| does not end with | Returns all items that do not end with the characters or strings of the value entered. |
| matches | Returns items that match exactly based on a given numeric or string value. Supports wildcards using an asterisk (`*`). This operator is case sensitive. For example:<ul><li>`a*e` matches `ae`, `abcde`, `adobe`, and `a whole sentence`.</li><li>`adob*` matches `adobe`, `adobe analytics`, and `adobo recipe`</li><li>`*dobe` matches `dobe`, `adobe`, and `cute little dobe`.</li></ul>|
| does not match | All items that match the string are excluded. Supports wildcards using an asterisk (`*`). |
| exists | Returns items if the value is not null. |
| does not exist | Returns items if the value is null. |

## Distinct Count operators

You can segment on a distinct count of items within a dimension. For example, you can create filters for visitors who viewed more than 5 distinct products or visits where more than 5 distinct pages were seen.

| Operator | Description |
| --- | --- |
| equals | Returns dimension items whose unique count equals the value entered. |
| does not equal | Returns dimension items whose unique count does not equal the value entered. |
| is greater than | Returns dimension items whose unique count is greater than the value entered. |
| is less than | Returns dimension items whose unique count is less than the value entered. |
| is greater than or equal to | Returns dimension items whose unique count is greater than or equal to the value entered. |
| is less than or equal to | Returns dimension items whose unique count is less than or equal to the value entered. |
