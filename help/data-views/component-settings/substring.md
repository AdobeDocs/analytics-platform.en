---
title: Substring component settings
description: Use a subset of a string as dimension items.
solution: Customer Journey Analytics
feature: Data Views
---
# [!UICONTROL Substring] component settings

[!UICONTROL Substring] component settings allow you to perform multiple string manipulation methods to obtain the desired dimension items in reports.

[!UICONTROL Substring] is available only on dimensions, and is retroactive to the data it is applied to. It is an immediate data transformation that happens before filtering or other analysis operations are applied.

![Substring settings](../assets/substring-settings.png)

## From the Left/Right

Take a part of a string based on its position to the beginning or end of a string. **[!UICONTROL From the Left]** and **[!UICONTROL From the Right]** methods provide two dropdowns: **[!UICONTROL From]** (where the output starts) and **[!UICONTROL To]** (where the output ends).

* **[!UICONTROL String Start]**: The start of the string.
* **[!UICONTROL String End]**: The end of the string.
* **[!UICONTROL Position]**: A static number of characters from the left or right, depending on the method.
* **[!UICONTROL String]**: Match a character or sequence of characters to indicate the beginning or end of a string. This dropdown also reveals additional options:
  * **[!UICONTROL Match]**: The string to match. If the input has no match with this field, [No value options](no-value-options.md) apply.
  * **[!UICONTROL Index]**: The **[!UICONTROL Match]** criteria can be present multiple times in a string. This integer determines which match to start or end the output, depending on the method. For example, an index of `1` represents the first match. If the index is higher than the number of matches available, [No value options](no-value-options.md) apply.
  * **[!UICONTROL Include String]**: A checkbox where, if enabled, includes the **[!UICONTROL Match]** string in the output.
* **[!UICONTROL Length]**: An integer that specifies the character count to include after the starting position of the output. Only available under the **[!UICONTROL To]** dropdown.

## Delimiter

Use this method for fields that use a delimiter to separate multiple string values. You can either extract an individual element to use as the output, or convert the string into an object array schema element.

* **[!UICONTROL Criterion]**: How you want to treat the delimited list of values.
  * **[!UICONTROL From the Left]**: Start from the beginning of the delimited list and count forward.
  * **[!UICONTROL From the Right]**: Start from the end of the delimited list and count backward.
  * **[!UICONTROL Convert to array]**: Treat this dimension as if it is an object array schema element.
* **[!UICONTROL Delimiter]**: The delimiter that the field uses.
* **[!UICONTROL Index]**: Only present if the criterion is From the Left/Right. The element number as if it was in an array. For example, if the string input is `"Fox,Turtle,Rabbit,Wolf"` with an index of 3, the output is `"Rabbit"`. If the index is higher than the number of delimited elements, [No value options](no-value-options.md) apply.

## URL parse

For use with fields that contain URLs. Using the example URL `https://example.com/store/index.html?cid=campaign#cart`, the following options are available:

* **[!UICONTROL Get protocol]**: Get the URL's protocol. For example, `"https://"`.
* **[!UICONTROL Get host]**: Get the URL's host. For example, `"example.com"`.
* **[!UICONTROL Get path]**: Get the URL's path. For example, `"store/index.html"`.
* **[!UICONTROL Get query string value]** Get the value from a single query string. Place the desired query string parameter in the **[!UICONTROL Query key]** field. If the above URL is used with the `"cid"` query key, the output is `"campaign"`.
* **[!UICONTROL Get hash value]**: Get the URL's hash value. For example, `"cart"`.

If the input is not a valid URL or if the desired URL component is not present, [No value options](no-value-options.md) apply.

## Trim

Trim white space or special characters from the string.

* **[!UICONTROL Trim whitespaces]**: A checkbox where, if enabled, removes all whitespace at the beginning and end of the string.
* **[!UICONTROL Trim special characters]**: A checkbox where, if enabled, reveals a **[!UICONTROL Special characters]** input field. All characters in this field are stripped from the output. Multi-byte characters are not supported.

## Regex

Apply regular expressions to a dimension to retrieve the desired value.

* **[!UICONTROL Regex]**: The regular expression formula.
* **[!UICONTROL Output format]**: 
* **[!UICONTROL Case sensitive]**: A checkbox where, if enabled, forces the regular expression to be case sensitive.

If the input does not match the regular expression, [No value options](no-value-options.md) apply.
