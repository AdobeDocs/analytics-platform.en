---
title: Component settings
description: View core settings for a component.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
---
# Component settings

Core settings that a component uses.

![Component settings](../assets/component-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Component type] | Required. Allows you to change a component from Metric to Dimension or vice versa. Changing this dropdown shifts the component to its respective included components area. |
| [!UICONTROL Component Name] | Required. Lets you specify the friendly name that appears in Analysis Workspace. You can rename a component to give it a name specific to the data view. |
| [!UICONTROL Description] | Optional, but recommended. Provides information on the component to other users. |
| [!UICONTROL Tags] | Optional. Lets you tag the component with custom or out-of-the-box tags for easier searching/filtering in the Analysis Workspace UI. |
| [!UICONTROL Field Name] | The name of the schema field. |
| [!UICONTROL Dataset type] | Required. A non-editable field showing which dataset type (event, lookup, or profile) the component came from. |
| [!UICONTROL Dataset] | A non-editable field showing which dataset that the component originated from. This field can contain multiple datasets. |
| [!UICONTROL Schema Data Type] | A non-editable field showing the data type of the component.  While you can use any supported schema field type in Platform, not all fields types are supported in CJA. The following data types are supported: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`, and `Boolean`. Only the `String` schema data type is allowed in Lookup datasets at this time. |
| [!UICONTROL Component ID] | Required. The [CJA API](https://adobe.io/cja-apis/docs) uses this field to reference the component. Each component in a data view must be unique. Adobe automatically generates an ID for each component; however, you can click the edit icon and modify the component ID. Changing the component ID breaks all existing Workspace projects that contain this component. While each component needs a unique ID in a single data view, you can use the same component ID in other data views. If you use the same component ID in other data views, you can make Workspace projects compatible across data views. |
| [!UICONTROL Schema Path] | Required. A non-editable field showing the schema path that the component came from. |
| [!UICONTROL Hide component in reporting] | Lets you curate the component out of the data view for non-admins. Admins can still access it by clicking [!UICONTROL Show All Components] in an Analysis Workspace project. |
