### Configure Component Settings

![](assets/component-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Component type] | Required. Allows you to change a component from Metric to Dimension or vice versa. |
| [!UICONTROL Component Name] | Required. Lets you specify the friendly name that will appear in Analysis Workspace. You can rename a component to give it a data-view-specific name. |
| [!UICONTROL Description] | Optional, but recommended, to provide information on the component for other users. |
| [!UICONTROL Tags] | Optional. Lets you tag the component with custom or out-of-the-box tags for easier searching/filtering in the Analysis Workspace UI. |
| [!UICONTROL Field Name] | The name of the schema field. |
| [!UICONTROL Dataset type] | Required. A non-editable field showing which dataset type (event, lookup, or profile) the component came from. |
| [!UICONTROL Dataset] | Required. A non-editable field showing which type of field the component came from (e.g. String, Integer, etc.). This field can contain multiple datasets. |
| [!UICONTROL Schema Data Type] | Refers to whether the component is a string, integer, and so on.  While you can use any supported schema field type in Platform, not all fields types are supported in CJA. The following data types are supported: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`, and `Boolean`. Note that only Strings are allowed in Lookup datasets at this time. |
| [!UICONTROL Component ID] | Required. The [CJA API](https://adobe.io/cja-apis/docs) uses this field to reference the component. You can click the edit icon and modify this component ID. However, changing this component ID breaks all existing Workspace projects that contain this component.<br>If you ever create another data view that uses a different field for a pageTitle dimension, you can rename it and make the dimension cross-data view compatible. |
| [!UICONTROL Schema Path] | Required. A non-editable field showing the schema path that the component came from. |
| [!UICONTROL Hide component in reporting] | Default = off. Lets you curate the component out of the Data View when used in reporting. This does not impact permissions, just component curation. In other words, you can hide the component from non-Admins in reporting. Admins can still access it by clicking [!UICONTROL Show All Components] in an Analysis Workspace project. |