---
title: Component settings
description: View core settings for a data view component.
exl-id: 6300d289-d308-476e-aa4e-05cdae361bb2
solution: Customer Journey Analytics
feature: Data Views
role: Admin
---
# Component settings {#component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_settings"
>title="Component settings"
>abstract="View and configure the name, description, and other settings related to a component. Check this box to hide this component from non-admin users in reporting. Admins can still access the component by selecting **[!UICONTROL Show all components]** in a Workspace project."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_contextlabels"
>title="Context labels"
>abstract="Removing a context label may impact specific panels or reports where the component is required."

<!-- markdownlint-enable MD034 -->


The following information describes the settings that a data view component uses.

![Component settings described in this section](../assets/component-settings.png)

| Setting | Description/Use case |
| --- | --- |
| [!UICONTROL Component type] | Required. Allow you to change a component from Metric to Dimension or the opposite way. Changing this drop-down selection shifts the component to its respective included components area. |
| [!UICONTROL Component name] | Required. Lets you specify the friendly name that appears in Analysis Workspace. You can rename a component to give it a name specific to the data view. |
| [!UICONTROL Description] | Optional, but recommended. Provides information on the component to other users. |
| [!UICONTROL Tags] | Optional. Let you tag the component with custom or out-of-the-box tags for easier searching/filtering in the Analysis Workspace UI. |
| [!UICONTROL Context labels] | Optional. A drop-down menu of available system-defined [context labels](#context-labels) that can be applied to a component.  |
| [!UICONTROL Schema field name] | The name of the schema field. |
| [!UICONTROL Dataset type] | Required. A non-editable field showing which dataset type (event, lookup, or profile) the component came from. |
| [!UICONTROL Dataset] | A non-editable field showing which dataset that the component originated from. This field can contain multiple datasets. |
| [!UICONTROL Schema type] | A non-editable field showing the data type of the component. While you can use any supported schema field type in Platform, not all fields types are supported in Customer Journey Analytics. The following data types are supported: `Integer`, `Int`, `Long`, `Double`, `Float`, `Number`, `Short`, `Byte`, `String`, and `Boolean`. Only the `String` schema data type is allowed in Lookup datasets currently. |
| [!UICONTROL Component ID] | Required. The [Customer Journey Analytics API](https://www.adobe.io/cja-apis/docs) uses this field to reference the component. Each component in a data view must be unique. Adobe automatically generates an ID for each component; however, you can click the edit icon and modify the component ID. Changing the component ID breaks all existing Workspace projects that contain this component. While each component needs a unique ID in a single data view, you can use the same component ID in other data views. If you use the same component ID in other data views, you can make Workspace projects compatible across data views. <br/>For profile and lookup based components, the component ID has an ID prefix based on the dataset ID (for example: `642b28fcc1f0ee1c074265a0.person.name.firstName`). When you want to reuse a profile or lookup based component, like `person.name.firstName`, in your Workspace project, and configure this component in different data views, ensure you rename the component ID uniquely (for example: `myUniqueID.person.name.firstName`) across your data views. |
| [!UICONTROL Path] | Required. A non-editable field showing the schema path that the component came from. |
| [!UICONTROL Data Usage Labels] | Any data usage labels that are assigned to this component in Adobe Experience Platform. [Learn more](/help/data-views/data-governance.md). |
| [!UICONTROL Hide component in reporting] | Let you curate the component out of the data view for non-admins. Admins can still access it by clicking [!UICONTROL Show All Components] in an Analysis Workspace project. |

{style="table-layout:auto"}



>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Component type settings](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/data-views/component-type-settings-in-data-views){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Context labels

Context labels are system-defined tags applied to components within a data view. When context labels are applied to components (dimension or metrics), Customer Journey Analytics is instructed to use these context-labeled components automatically in certain visualizations or features.

Context labels allow you to provide semantic context to individual pieces of data.  In general, Customer Journey Analytics does not need to know the semantic meaning of a dimension or metric to perform its analysis.  However, some situations (project templates and a few selected visualizations) require Customer Journey Analytics to understand semantic meaning to perform some type of analysis. Context labels are created for those situations. 

Context labels operate at the component (dimension or metric) level, and allow for great flexibility within the data view for the customer. For example, you can assign a context label to a dimension after you have applied several post-processing transforms to a field. Or even to a dimension that is based on a derived field.  Context labels provide a layer of abstraction on top of components and fields.

For reasons of convenience, smart default context labels are applied automatically to components based on fields with a specific XDM path. For example, the **[!UICONTROL Commerce: Product Category]** context label is applied automatically to a **[!UICONTROL Category name]** dimension that is based on the `productListItems.productCategories.categoryName` schema path. You can, however, move the context label to a different component without any issue. 

To streamline Adobe provided project templates, several integrations (like Journey Optimizer, Content Analytics, and more) set up data views where out of the box components are constructed in a specific way. And appropriate context labels are applied automatically. Again, you can simply move any of those context labels to other components that are created in the data view and your custom component is used instead. 

Context labels are relevant for the disclosure of project templates as well. Project templates quickly realize the reporting foundation for several different purpose-built use cases. However, not every template does make sense for every data view and you don't want to show non-applicable templates. Context labels are used to show templates based on whether the context labels are included in the selected data view.  You can simply add more context labels to your data view (components), and more templates become available. Or remove context labels to hide specific templates.

>[!NOTE]
>
>You can apply more than one context label to a component, but you cannot apply one context label to multiple components within one data view.
>

The benefits of context labels are:

* **Convenience**: You don't have to re-select the same component in every panel or visualization.
* **Unlocks functionality**: Some visualizations (like [Map](/help/analysis-workspace/visualizations/map.md)) require knowledge about which component is latitude and longitude. Assigning context labels discloses that information to the visualization.
* **Consistency**: Everyone in your organization that works on one or more projects that are based on a data view that uses context labels gets the same behavior.
* **Visibility of features and templates**: Certain visualizations and features only appear when the proper context label is assigned. For example:
  
  * A [Map](/help/analysis-workspace/visualizations/map.md) visualization does display properly only when Customer Journey Analytics knows which components represent latitude and longitude. 
  * Specific [templates](/help/analysis-workspace/templates/use-templates.md) are visible only when the correct context labels are applied and the associated components become available. 

Context labels may be required in the following situations:

* To define a set of components, you can use in experimentation reporting using the [Experimentation panel](/help/analysis-workspace/c-panels/experimentation.md) in Analysis Workspace projects.
  
  For more information, see [Integrate with Journey Optimizer](/help/integrations/ajo.md#data-view) and [Target reporting](/help/integrations/at.md).

* To define a set of components, you can use within the [Map](/help/analysis-workspace/visualizations/map.md) visualization in Analysis Workspace projects.

  For more information, see [Add context labels in data views](/help/analysis-workspace/visualizations/map.md#add-context-labels-in-data-views) in [Map](/help/analysis-workspace/visualizations/map.md).

  **Note**: The Map visualization is in the Limited Testing phase of release and might not be available yet in your environment.

* To reveal [templates provided by Adobe](/help/analysis-workspace/templates/use-templates.md). Some templates provided by Adobe might not work because certain components are not in your data view.
  
  For each missing component, a matching context label is available in your data view. You need to either add the matching context label to a component that is already in your data view. Or you need to add a new component to your data view and add the context label to the component (if not already provided automatically).
  
  For more information, see [Add missing components to the data view for a given template](/help/analysis-workspace/templates/create-templates.md#add-missing-components-to-the-data-view-for-a-given-template) in the article [Create and manage templates](/help/analysis-workspace/templates/create-templates.md).


The following groups of context labels are available, each with a list of specific context labels.

+++ Campaign

| Name | Description |
|------|-------------|
| Tracking Code | Tracking code. |
| Tracking Code Instances | Tracking code instances. |

+++

+++ Commerce

| Name | Description |
|------|-------------|
| Cart Additions | Cart Additions |
| Cart Opens | The cart opens. |
| Cart Removals | Cart Removals |
| Cart Views | Cart Views |
| Checkouts | Checkouts. |
| Orders | Orders. |
| Product | Product. |
| Product Category | Product category. |
| Product Views | Product views. |
| Revenue | Revenue. |
| Store | Store. |
| Units | Units. |

+++

+++ Experimentation

| Name | Description |
|------|-------------|
| Experimentation Experiment | An experiment is a set of variations on an experience that were exposed to end users to determine which is best to keep in perpetuity. |
| Experimentation Variant | Variant is one of two or more alterations in an end user's experience that are being compared for the purpose of identifying the better alternative. |

+++

+++ Media

| Name | Description |
|------|-------------|
| Content ID | Content ID. |
| Content Time Spent | Content Time Spent. |
| Episode | Episode. |
| Event Type | Event Type. |
| Media Time Spent | Media Time Spent. |
| Season | Season. |
| Seconds Since Last Call | Seconds Since Last Call. |
| Show | Show. |
| Time to Start | Time to Start. |
| Total Buffer Duration | Total Buffer Duration. |
| Total Pause Duration | Total Pause Duration. |
| Video Length | Video Length. |
| Video Name | Video Name. |

+++

+++ Call Center

| Name | Description |
|------|-------------|
| Call Center Name | Call center name. |
| Call Costs | Call costs. |
| Call Hours | Call hours. |
| Call Length | Call length. |
| Call Reason | Call reason. |
| Call Survey Score | Call survey score. |
| Calls | Calls. |

+++

+++ Demographic

| Name | Description |
|------|-------------|
| Gender | Gender. |

+++

+++ Environment

| Name | Description |
|------|-------------|
| Browser | Browser. |
| Browser Type | Browser type. |
| Language | Language. |
| Operating System | Operating system. |
| Operating System Group | Operating system group. |
| Operating System Name | Operating system name. |

+++

+++ General

| Name | Description |
|------|-------------|
| Action Name | Action name. |
| Actions | Actions. |
| Interaction Channel | Interaction channel. |

+++

+++ Geo

| Name | Description |
|------|-------------|
| Geo City | Geo city. |
| Geo Country | Geo country. |
| Geo Dma | Geo dma. |
| Geo Region | Geo region. |
| Latitude | Latitude. |
| Longitude | Longitude. |
| Point Of Interest | Point of interest. |
| State | State. |

+++

+++ Marketing Channel

| Name | Description |
|------|-------------|
| First Touch Channel | First touch channel. |
| First Touch Channel Detail | First touch channel detail. |
| Last Touch Channel | Last touch channel. |
| Last Touch Channel Detail | Last touch channel detail. |
| Marketing Channel | Marketing channel. |

+++

+++ Mobile

| Name | Description |
|------|-------------|
| Application Id | Application id. |
| Mobile Carrier | Mobile carrier. |
| Mobile Crashes | Mobile crashes. |
| Mobile Device Name | Mobile device name. |
| Mobile Device Type | Mobile device type. |
| Mobile In App Message Name | Mobile in app message name. |
| Mobile Installs | Mobile installs. |
| Mobile Launches | Mobile launches. |
| Mobile Manufacturer | Mobile manufacturer. |
| Mobile Message Cancels | Mobile message cancels. |
| Mobile Message Clicks | Mobile message clicks. |
| Mobile Message Impressions | Mobile message impressions. |
| Mobile Message Push Opt In | Mobile message push opt-in. |
| Mobile Push Message Name | Mobile push message name. |
| Mobile Upgrades | Mobile upgrades. |
| Time Spent Per Timed Action | Time spent per timed action. |

+++

+++ Search

| Name | Description |
|------|-------------|
| Search Engine | Search engine. |
| Search Engine Keyword | Search engine keyword. |
| Search Engine Natural | Search engine natural. |
| Search Engine Natural Keyword | Search engine natural keyword. |
| Search Engine Paid | Search engine paid. |
| Search Engine Paid Keyword | Search engine paid keyword. |

+++

+++ Survey

| Name | Description |
|------|-------------|
| Survey | Survey. |
| Survey Answer | Survey answer. |
| Survey Completes | Survey completes. |
| Survey Question | Survey question. |
| Survey Starts | The survey starts. |

+++

+++ Web

| Name | Description |
|------|-------------|
| Average Page Time | Average page time. |
| Bounces | Bounces. |
| Entry Page | Entry page. |
| Exit Page | Exit page. |
| Page | Page. |
| Page Views | Page views. |
| Referrer | Referrer. |
| Referrer Type | Referrer type. |
| Referring Domain | Referring domain. |
| Referring Domain Original | Referring domain original. |
| Reloads | Reloads. |
| Single Page Visits | Single page visits. |
| Site Sections | Site sections. |

+++

+++ B2B

| Name | Description |
|------|-------------|
| Account Name | Account name. |
| Buying Group Name | Buying group name |
| Opportunity Name | Opportunity name |

+++

+++ Content Analytics

| Name | Description |
|------|-------------|
| Asset Absolute Left | Asset Absolute Left. |
| Asset Absolute Top | Asset Absolute Top. |
| Asset Attributes | Asset Attributes.|
| Asset Background Colors | Asset Background Colors. |
| Asset Camera Positions | Asset Camera Positions. |
| Asset Camera Proximities | Asset Camera Proximities. |
| Asset Camera Settings | Asset Camera Settings. |
| Asset Clicks | Asset Clicks. |
| Asset Created By | Asset Created By. |
| Asset Created Date | Asset Created Dat.e |
| Asset Display Height | Asset Display Height. |
| Asset Display Width | Asset Display Width. |
| Asset Foreground Colors | Asset Foreground Colors. |
| Asset Id | Asset Id. |
| Asset Image Types | Asset Image Types. |
| Asset Last Updated By | Asset Last Updated.|
| Asset Last Updated Date | Asset Last Updated Date. |
| Asset Lighting Conditions | Asset Lighting Conditions. |
| Asset Link Url | Asset Link Url. |
| Asset Name | Asset Name. |
| Asset People Categories | Asset People Categories. |
| Asset Perception ID | Unique identifier of assets that are perceptually the same. |
| Asset Photography Styles | Asset Photography Styles. |
| Asset Scenes | Asset Scenes. |
| Asset Source | Asset Source. |
| Asset Tags | Asset Tags. |
| Asset Type | Asset Type. |
| Asset Views | Asset Views. |
| Asset Visual Attention Spread | Asset Visual Attention Spread. |
| Asset Visual Content Density | Asset Visual Content Density. |
| Experience Attributes | Experience Attributes. |
| Experience channel | Experience Channel. |
| Experience Clicks | Experience Clicks. |
| Experience Emoji Count | Experience Emoji Count. |
| Experience Hashtag Count | Experience Hashtag Count. |
| Experience Horizontal Percentage Depth | Experience Horizontal Percentage Depth. |
| Experience Keywords | Experience Keywords. |
| Experience Marketing Emotions | Experience Marketing Emotions. |
| Experience Narratives | Experience Narratives. |
| Experience Persuasion Strategies | Experience Persuasion Strategies. |
| Experience Readability Word Count Per Sentence Count | Experience Readability Word Count Per Sentence Count. |
| Experience Readability Score | Experience Readability Score. |
| Experience Readability Sentences Count | Experience Readability Sentences Count. |
| Experience Readability Stop Words Count | Experience Readability Stop Words Count. |
| Experience Readability Text Quotes Count | Experience Readability Text Quotes Count. |
| Experience Readability Word Count | Experience Readability Word Count. |
| Experience Source | Experience Source. |
| Experience Tones | Experience Tones. |
| Experience Vertical Percentage Depth | Experience Vertical Percentage Depth. |
| Experience Views | Experience Views. |

+++

+++ Journey Optimizer

| Name | Description |
|------|-------------|
| Action Error (AJO) | Count of errors generated by journey actions. |
| Action Execution Error | Error condition that prevented Journey Runtime from executing the action. |
| Action Label (AJO) | The customer generated display name of the element with which the end-user interacted. |
| Alternative Exits (AJO) | The count of exits that did not occur due to a profile reaching an end node or failing due to an error. |
| App Installs (AJO) | Number of app installs. |
| App Launches (AJO) | Number of times a mobile app is launched. |
| Batch Id (AJO) | GUID created at invocation of each new batch instance for a scheduled Journey or Campaign Action. For example: If a scheduled Journey or Campaign Action runs at 8.00am and 10.00am, there will be two separate different batchInstanceID's. |
| Batch Instance Timestamp (AJO) | The timestamp of the batch instance. |
| Bounces For Outbound Channels(deprecated) | The total count of messages bounced across outbound channels. |
| Campaign Action Name (AJO) | The name of the campaign action. |
| Campaign Id (AJO) | The id of the campaign. |
| Campaign Name (AJO) | The name of the campaign. |
| Campaign Version ID (AJO) | The version id of the campaign. |
| Channel | The channel to which this data should be correlated. |
| Clicks (AJO) | Total count of clicks across all channels. |
| Consent Policy Rejections (AJO) | Count of journey actions that are rejected due to one or more consent policies. |
| Content Decision Error (AJO) | Error messages generated by content decision nodes of journey. |
| Content Decision Errors (AJO) | Count of errors generated by content decision nodes of journey. |
| Content Decision Node Name (AJO) | The content decision node name of the journey. |
| Correlation Id | Correlation Id.|
| Count of Offers (AJO) | The number of offer items in the proposition. |
| Decision Item Binding Key | A composite identifier that combines item ID with Experience Decisioning request ID, enabling data persistence across interactions. |
| Decision Provider (AJO) | The provider that was asked to make the decision. This dimension is used when multiple services can make decisions for the same placement or activity. |
| Decision Provider (Persisted) (AJO) | The decision provider with persistence binding enabled. |
| Decision Policy Id (AJO) | The id of the decision policy used when deciding which items to include in this proposition. |
| Dedup Metric (AJO) | Dedup Metric. |
| Delivered (deprecated) | Total count of messages delivered. |
| Displays (AJO) | This count displays of AJO messages. This count includes email opens, web displays, and in app displays. Mobile platforms do not report SMS and Push message displays, therefore they are not counted. |
| Dismissed (AJO) | Counts every time the inApp message is closed by the Adobe SDK regardless of which action the end user chooses to close it. |
| Dry Run Id (AJO) | Unique Identifier for Dry Run. |
| Email Bot Opens (AJO) | Total count of email opens performed by bots. |
| Email Opens (AJO) | Total count of email opens. |
| Email Recipient Domain (AJO) | Domain of Email Address. |
| Email Subject | Email subject, non-personalized. |
| Event Id | A unique identifier for the time-series event. |
| Exit Criteria Id (AJO) | The id of the exit criteria used to determine if the journey should exit. |
| Exit Criteria Name (AJO) | Name of exit criteria. |
| Experiment Id (AJO) | The id of the experiment. |
| Experiment Name (AJO) | The name of the experiment. |
| Fall Back Offer Count (AJO) | The number of fall back offers. |
| Fetch Error | Error condition that prevented Journey Runtime from executing the fetch. |
| Inbound Clicks (AJO) | Total count of clicks across inbound channels. |
| Inbound Dismisses (AJO) | Total count of dismiss across inbound channels. |
| Inbound Impressions (AJO) | Total count of impressions across inbound channels. |
| Inbound Sends (AJO) | Total count of sends across inbound channels. |
| Inbound Triggered (AJO) | Proposition was chosen to be displayed by the Adobe SDK. Other factors may prevent it from actually being displayed. |
| Is Send-Time Optimized (AJO) | Is message execution SendTimeOptimized? |
| Is Test Journey | Is the event part of a test journey execution? |
| Is Test Message (AJO) | Is message sent as a test execution? |
| Item ID (Persisted) (AJO) | The ID of the item with persistence binding enabled. |
| Item Id (AJO) | The id of the item. |
| Item Name (AJO) | The name of the item. |
| Item Name (Persisted) (AJO) | The name of the item with persistence binding enabled. |
| Journey Action Error (AJO) | Error messages generated by journey actions. |
| Journey Action Node Name | The node name of the journey action. |
| Journey Enters | True if the step event was a journey entrance event for a profile. |
| Journey End (AJO) | The end of the journey. |
| Journey Event Node Name | This value is set whenever a segment or external event occurs in a journey. |
| Journey Exclusion Reason | Reason for journey instance exclusion. |
| Journey Exclusion Rule Name | Name of the Rule that caused the denial of Journey Entry. |
| Journey Exclusions (AJO) | Indicate whether the current step event resulted in a journey discard for a profile. This typically occurs due to capping or concurrency rules being applied, preventing further progression in the journey. |
| Journey Exit Type (AJO) | The type of exit that occurred for the journey instance. |
| Journey Failures | Gives the current state of the step that has finished executing. |
| Journey Id | The id of the journey. |
| Journey Name | The name of the journey. |
| Journey Name and Version | The name and version of the journey. |
| Journey Version Id | The version id of the journey. |
| JourneyExits | True if the current step led to ending an instance of the journey. That is the last step in a journey for a given profile was executed successfully. |
| Landing Page Conversions (AJO) | Total count of conversions on landing page. |
| Landing Page Id (AJO) | Unique Identifier for Landing Page. |
| Landing Page Source (AJO) | The source of the landing page. |
| Landing Page Views (AJO) | Total count of views on landing page. |
| Landing page clicks (AJO) | Total count of clicks on landing page. |
| Link URL (AJO) | The URL clicked by the user. |
| Message Bounce Reason (AJO) | The reason for the message bounce. |
| Message Error Reason (AJO) | The reason for the message error. |
| Message Exclusion Reason (AJO) | Exclusion reason. |
| Message Failure Category (AJO) | Failure category .|
| Message Failure Reason (AJO) | Failure reason. |
| Message Failure Type (AJO) | Failure Type. |
| Message ID (AJO) | The message id to which this data should be correlated. |
| Message Language (AJO) | The language of the message. |
| Message Name (AJO) | The name of the message. |
| Message Retry (AJO) | Retry count. |
| Message Status (AJO) | Message status (for example, sent, bounced, error, etc.) |
| Message Type (AJO) | Whether the message is marketing or transactional. |
| Message Feedback Status (deprecated) | Feedback status. |
| Node Enters | True if the step event was a node entrance event for a profile. |
| Node Id | The node id of the journey node. |
| Node Name | The node name of the journey node. |
| Node Type | The node type of the journey node. |
| Orchestrated Campaign Action Identity Namespace (AJO) | The identity namespace of the orchestrated campaign action. |
| Orchestrated Campaign Action Name (AJO) | The action name of orchestrated campaign. |
| Orchestrated Campaign Action Node ID (AJO) | The action id of the orchestrated campaign. |
| Orchestrated Campaign ID (AJO) | The id of the orchestrated campaign. |
| Orchestrated Campaign Name (AJO) | The name of the orchestrated campaign. |
| Orchestrated Campaign Version ID (AJO) | The version id of the orchestrated campaign. |
| Outbound Clicks (AJO) | Total count of clicks across outbound channels. |
| Outbound Errors (deprecated) | Total count of messages having errors across outbound channels. |
| Outbound Exclusions (deprecated) | Total count of exclude events across outbound channels. |
| Outbound Sends (deprecated) | Total count of messages sent across outbound channels. |
| Point Of Interest | point of interest. |
| Proposition Id (AJO) | The id of the proposition. |
| Push Custom Actions (AJO) | Total count of custom actions in push interaction. |
| Push Interactions (AJO) | Number of times a mobile app is launched due to a direct push message interaction. |
| Push Platform (AJO) | Push provider service, for example, APNS or FCM. |
| Push Title | Push Title, non-personalized. |
| Ranking Strategy Id (AJO) | The Ranking Strategy Id. |
| Rejected Consent Policy Name | Name of the corresponding rejected consent policy. |
| Retry Count (AJO) | Number of times a message send was retried before either success or failure. |
| Rule Name | Name of the Rule that caused the denial of Journey Entry. |
| Selection Type (AJO) | This is the type of selection used when an item is derived as part of a decision. |
| Sends (deprecated) | Total count of messages sent across all channels. |
| SMS Inbound Message (AJO) | SMS inbound reply, for example, stop, start, subscribe, etc. |
| SMS Inbound Messages (AJO) | SMS inbound reply, e.g. stop, start, subscribe, etc. |
| SMS Message Type (AJO) | SMS provider, for example, inbound, inboundReply or send. |
| SMS Provider (AJO) | SMS provider, for example, Sinch or Twilio. |
| Spam Complaint (AJO) | Total count of spam complaint. |
| Strategy Name (AJO) | Strategy name. The strategy name of which the item was derived from. |
| Strategy Name (Persisted) (AJO) | The strategy name with persistence binding enabled. |
| Subscription List Adds (AJO) | Total count of adds to a subscription list. |
| Subscription List Id (AJO) | Unique Identifier for Subscription List. |
| Subscription List Removes (AJO) | Total count of removes from a subscription list. |
| Surface (AJO) | The channel surface on which the message was displayed. |
| Targeted (deprecated) | This count of the number of times a proposition was targeted to a person. This is the number of times a proposition was considered for display to a person. |
| Targeting Rule Name (AJO) | The name of the targeting rule. |
| Test Event (AJO) | Test event. |
| Time to Start | Time to Start. |
| Total Buffer Duration | Total Buffer Duration. |
| Total Pause Duration | Total Pause Duration. |
| Traffic Type (AJO) | The Ranking Traffic Type. |
| Treatment Id (AJO) | The id of selected treatment for the experiment. |
| Treatment Name (AJO) | The name of the treatment for the experiment. |
| Unique Visitors In Experiment (AJO) | The unique visitors in the experiment. |
| Unsubscribes (AJO) | Total count of unsubscribes. |
| Url Label (AJO) | Human-Friendly label for URL. |
| URL ID (AJO) | Unique Identifier of the URL clicked by the user. |

+++
