---
title: Manage custom fields
description: How to create, edit or delete custom fields.
solution: Customer Journey Analytics
feature: Data Views
---

# Manage custom fields

You create, edit and/or delete custom fields in Customer Journey Analytics (CJA) as part of [Data Views](../data-views.md).


## Custom field interface

When you create or edit a custom field, you use the custom field interface.

![Custom field dialg](assets/custom-field-dialog.png)


|  | Name | Description
|---------|----------|--------|
| 1 | **Selector** | Select and drag and drop your ![Function](assets/Smock_Function_18_N.svg) function, ![Function template](assets/Smock_FileTemplate_18_N.svg) function template, ![Schema field](assets/Smock_Folder_18_N.svg) schema field, or standard field on to the rule builder. <br/>You can search for function, function templates, schema, and standard fields using the Search box. <br/>You can filter the selected object list by selecting Filter and specify filters in the Filter field by dialog. You can easily remove filters using the x for each filter. | 
| 2 | **Rule builder** | Build your custom field sequentially using one or more rules. Every rule is always associated with only one function. The function type determines the interface of the rule<br/>See the [Rule interface](#rule-interface) for more information. |
| 3 | **[!UICONTROL **Field Settings**]** | Define the name and description of your custom field. | 
| 4 | **[!UICONTROL **Final Output**]** | Shows an on-the-fly updated preview of  output values, based on data over the last 30 days and the changes you make to the custom field in the Rule builder. |

{style="table-layout:auto"}

## Rule interface

When you define a rule in the Rule builder, you use the rule interface.

![Rule Interface](assets/rule-interface.png)

|  | Name | Description
|---------|----------|--------|
| A | **Rule Name** | By default the rule name is **Rule X** (X referring to a sequence number). To edit the name of a rule, select its name and type in the new name, for example `Query Parameter`.
| B | **Function Name** | The selected function name for the rule, for example **URL PARSE**. When the function is the last in the sequence of functions and determines the final output values, the function name is followed by **FINAL OUTPUT**, for example **URL PARSE - FINAL OUTPUT**. <br/>To show a popup with more information on the function, select ![Help](assets/Smock_HelpOutline_18_N.svg).
| C | **Rule Description** | You can optionally add a description to a rule.<br/>Select ![More](assets/More.svg), then select **[!UICONTROL **Add Description**]** to add a description or **[!UICONTROL **Edit Description**]** to edit an existing description.<br/>Use the editor to enter a description. You can use the toolbar to format the text (using style selector, bold, italic, underline, right, left, centered, color, number list, bullet list) and adding links to external information. <br/>To finish editing the description, click outside of the editor. |
| D | **Function Area** | Defines the logic of the function. The interface depends on the type of function. See [Custom field functions](custom-field-functions.md) on detailed information for each of the functions supported. |

{style="table-layout:auto"}

## Create a custom field

1.  In CJA's main interface, select **[!UICONTROL **Data views**]** from the top rail.

2.  Select an existing Data view or create a Data view. See [Data views](../data-views.md) for more information.

3.  Select the **[!UICONTROL **Components**]** tab of the Data view.

4.  Select **[!UICONTROL **Create custom field**]** from the left rail.
   
5.  To define your custom field, use the **[!UICONTROL **Create custom field**]** interface. See [Custom field interface](#custom-field-interface).

    To save your new custom field, select **[!UICONTROL **Save**]**.

6.  Your new custom field is added to the **[!UICONTROL **Custom fields >**]** container, as part of **[!UICONTROL **Schema fields**]** in the left rail of your Data view.


## Edit a custom field

1.  In CJA's main interface, select **[!UICONTROL **Data views**]** from the top rail.

2.  Select an existing Data view. See [Data views](../data-views.md) for more information.

3.  Select the **[!UICONTROL **Components**]** tab of the Data view.

4.  Select **[!UICONTROL **Schema fields**]** tab in [!UICONTROL Connection] pane.

5.  Select **[!UICONTROL **Custom fields >**]** container.

6.  Hover over the custom field that you want to edit, and select ![Edit](assets/Smock_Edit_18_N.svg).

7.  To modify your custom field, use **[!UICONTROL **Edit custom field**]** interface. See [Custom field interface](#custom-field-interface).

    -   Select **[!UICONTROL **Save**]** to save your updated custom field.

    -   Select **[!UICONTROL **Cancel**]** to cancel any changes you made to the custom field.

    -   Select **[!UICONTROL **Save As**]** to save the custom field as a new custom field. The new custom field with have the same name as the original edited custom field with (copy) added to it.

## Delete a custom field

1.  In CJA's main interface, select **[!UICONTROL **Data views**]** from the top rail.

2.  Select an existing Data view. See [Data views](../data-views.md) for more information.

3.  Select the **[!UICONTROL **Components**]** tab of the Data view.

4.  Select **[!UICONTROL **Schema fields**]** tab in [!UICONTROL Connection] pane.

5.  Select **[!UICONTROL **Custom fields >**]** container.

6.  Hover over the custom field that you want to delete, and select ![Edit](assets/Smock_Edit_18_N.svg).

7.  In the Use **[!UICONTROL **Edit custom field**]** interface, select Delete.

    A [!UICONTROL Delete component] dialog asks you to confirm the deletion. Consider any external references there might exist to the custom field outside of the Data view. 
    
    - Select **[!UICONTROL **Continue**]** to delete the custom field.






