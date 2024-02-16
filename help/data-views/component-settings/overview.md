---
title: Component settings
description: View core settings for a data view component.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Component settings

The following information describes the settings that a data view component uses.

![Component settings described in this section](../assets/component-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Component type] | Required. Allows you to change a component from Metric to Dimension or the opposite way. Changing this drop-down selection shifts the component to its respective included components area. |
| [!UICONTROL Component Name] | Required. Lets you specify the friendly name that appears in Analysis Workspace. You can rename a component to give it a name specific to the data view. |
| [!UICONTROL Description] | Optional, but recommended. Provides information on the component to other users. |
| [!UICONTROL Tags] | Optional. Lets you tag the component with custom or out-of-the-box tags for easier searching/filtering in the Analysis Workspace UI. |
| [!UICONTROL Context labels] | Optional. A drop-down list of available system-defined labels that can be applied to a component. These labels may be required to define a set of components used for reporting in Analysis Workspace projects or panels. |
| [!UICONTROL Schema field name] | The name of the schema field. |
| [!UICONTROL Dataset type] | Required. A non-editable field showing which dataset type (event, lookup, or profile) the component came from. |
| [!UICONTROL Dataset] | A non-editable field showing which dataset that the component originated from. This field can contain multiple datasets. |
| [!UICONTROL Schema Type] | A non-editable field showing the data type of the component. While you can use any supported schema field type in Platform, not all fields types are supported in Customer Journey Analytics. The following data types are supported: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`, and `Boolean`. Only the `String` schema data type is allowed in Lookup datasets currently. |
| [!UICONTROL Component ID] | Required. The [Customer Journey Analytics API](https://adobe.io/cja-apis/docs) uses this field to reference the component. Each component in a data view must be unique. Adobe automatically generates an ID for each component; however, you can click the edit icon and modify the component ID. Changing the component ID breaks all existing Workspace projects that contain this component. While each component needs a unique ID in a single data view, you can use the same component ID in other data views. If you use the same component ID in other data views, you can make Workspace projects compatible across data views. <br/>For profile and lookup based components, the component ID has an ID prefix based on the dataset ID (for example: `642b28fcc1f0ee1c074265a0.person.name.firstName`). When you want to reuse a profile or lookup based component, like `person.name.firstName`, in your Workspace project, and configure this component in different data views, ensure you rename the component ID uniquely (for example: `myUniqueID.person.name.firstName`) across your data views. |
| [!UICONTROL Path] | Required. A non-editable field showing the schema path that the component came from. |
| [!UICONTROL Data Usage Labels] | Any data usage labels that were assigned to this component in Adobe Experience Platform. [Learn more](/help/data-views/data-governance.md). |
| [!UICONTROL Hide component in reporting] | Lets you curate the component out of the data view for non-admins. Admins can still access it by clicking [!UICONTROL Show All Components] in an Analysis Workspace project. |

{style="table-layout:auto"}

Here is a video on component settings in data views:

>[!VIDEO](https://video.tv.adobe.com/v/333112/?quality=12)
