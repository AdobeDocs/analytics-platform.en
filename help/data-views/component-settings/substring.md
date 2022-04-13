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
  * **[!UICONTROL Include String]**: A checkbox that includes the **[!UICONTROL Match]** string in the output if enabled.
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
* **[!UICONTROL Get query string value]**: Get the value from a single query string. Place the desired query string parameter in the **[!UICONTROL Query key]** field. If the above URL is used with the `"cid"` query key, the output is `"campaign"`.
* **[!UICONTROL Get hash value]**: Get the URL's hash value. For example, `"cart"`.

If the input is not a valid URL or if the desired URL component is not present, [No value options](no-value-options.md) apply.

## Trim

Trim white space or special characters from the string.

* **[!UICONTROL Trim whitespaces]**: A checkbox that removes all whitespace at the beginning and end of the string if enabled.
* **[!UICONTROL Trim special characters]**: A checkbox that reveals a **[!UICONTROL Special characters]** input field if enabled. All characters in this field are stripped from the output. Multi-byte characters are not supported.

## Regex

Apply regular expressions to a dimension to retrieve the desired value.

* **[!UICONTROL Regex]**: The regular expression formula.
* **[!UICONTROL Output format]**: An optional field that lets you add text or reorder the regex subgroup output. If this field is blank, the string output is the evaluated regex expression.
* **[!UICONTROL Case sensitive]**: A checkbox that forces the regular expression to be case-sensitive if enabled.

CJA uses a subset of the Perl regex syntax. If the input does not match the regular expression and the **[!UICONTROL Output format]** is blank, [No value options](no-value-options.md) apply. The following expressions are supported:

| Expression | Description |
| --- | --- |
| `a` | A single character `a`. |
| `a|b` | A single character `a` or `b`. |
| `[abc]` | A single character `a`, `b`, or `c`. |
| `[^abc]` | Any single character except `a`, `b`, or `c`. |
| `[a-z]` | Any single character in the range of `a`-`z`. |
| `[a-zA-Z0-9]` | Any single character in the range of `a`-`z`, `A`-`Z`, or digits `0`-`9`. |
| `^` | Matches the beginning of the line. |
| `$` | Matches the end of the line. |
| `\A` | Start of string. |
| `\z` | End of string. |
| `.` | Matches any character. |
| `\s` | Any whitespace character. |
| `\S` | Any non-whitespace character. |
| `\d` | Any digit. |
| `\D` | Any non digit. |
| `\w` | Any letter, number, or underscore. |
| `\W` | Any non-word character. |
| `\b` | Any word boundary. |
| `\B` | Any character that is not a word boundary. |
| `\<` | Start of word. |
| `\>` | End of word. |
| `(...)` | Capture everything enclosed. |
| `(?:...)` | Non-marking capture. Prevents the match from being referenced in the output string. |
| `a?` | Zero or one of `a`. |
| `a*` | Zero or more of `a`. |
| `a+` | One ore more of `a`. |
| `a{3}` | Exactly 3 of `a`. |
| `a{3,}` | 3 or more of `a`. |
| `a{3,6}` | Between 3 and 6 of `a`. |

Output placeholders are also supported. You can use these sequences in the **[!UICONTROL Output format]** any number of times and in any order to achieve the desired string output.

| Output placeholder sequence | Description |
| --- | --- |
| `$&` | Outputs what matched the whole expression. |
| `$n` | Outputs what matched the nth sub expression. For example, `$1` outputs the first sub expression. |
| ``$` `` | Outputs the text between the end of the last match found (or the start of the text if no previous match was found), and the start of the current match. |
| `$+` | Outputs what matched the last marked sub expression in the regular expression. |
| `$$` | Outputs the string character `"$"`. |
