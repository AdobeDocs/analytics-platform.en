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
  * **[!UICONTROL Match]**: The string to match.
  * **[!UICONTROL Index]**: The **[!UICONTROL Match]** criteria can be present multiple times in a string. This integer determines which match to start or end the output, depending on the method. For example, an index of `1` represents the first match.
  * **[!UICONTROL Include String]**: A checkbox where, if enabled, includes the **[!UICONTROL Match]** string in the output.
* **[!UICONTROL Length]**: An integer that specifies the character count to include after the starting position of the output. Only available under the **[!UICONTROL To]** dropdown.

## Delimiter
