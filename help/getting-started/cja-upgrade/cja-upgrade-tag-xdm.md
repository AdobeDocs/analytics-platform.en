---
title: Add XDM data collection logic to your tag
description: Learn how to add XDM data collection logic to your tag
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: bc6c7568-8bd2-4ee1-ab1b-9fa1f6138811
---
# Add XDM data collection logic to your tag

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

After [creating the tag and adding the Web SDK extension](/help/getting-started/cja-upgrade/cja-upgrade-tag-property.md), you must configure it with data elements and rules, according to how you want to track your site and send data to Adobe Experience Platform. After you configure data elements and rules for your tag, you can build and publish it.

## Configure data elements

Data elements are the building blocks for your data dictionary (or data map). Use data elements to collect, organize, and deliver data across marketing and ad technology. You set up data elements in your tag that read from your data layer and can be used to deliver data into Adobe Experience Platform.

There are different types of data elements. First, set up a data element to capture the page name persons are viewing on your site. Then, set up a data element referencing the Experience Cloud ID. Finally, define an XDM object data element.

### Page name data element

To define a page name data element:

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.

1. Select **[!UICONTROL Data Elements]** in the left rail.

1. Select **[!UICONTROL Add Data Element]**.

1. In the [!UICONTROL Create Data Element] dialog, specify the following information:

   * **[!UICONTROL Name]**: The name of your data element. For example `Page Name`.

   * **[!UICONTROL Extension]**: Select **[!UICONTROL Core]** from the list.

   * **[!UICONTROL Data Element Type]**: Select **[!UICONTROL Page Info]** from the list.

   * **[!UICONTROL Attribute]**: Select **[!UICONTROL Title]** from the list.

     ![Create Date Element using Page Info](assets/create-dataelement-1.png)

     Alternatively you could have used the value from a variable of your data layer, for example `pageName` and the [!UICONTROL JavaScript Variable] data element type to define the data element.

     ![Create Data Element using Javascript Variable](assets/create-dataelement-2.png)

1. Select **[!UICONTROL Save]**.

   You now want to set up a data element referencing the Experience Cloud ID that is automatically provided by the Adobe Experience Platform Web SDK and available through the Experience Cloud ID Service extension.

1. Continue with [ECID data element](#ecid-data-element).

### ECID data element

To define an ECID data element:

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.

1. Select **[!UICONTROL Data Elements]** in the left rail.

1. Select **[!UICONTROL Add Data Element]**.

1. In the [!UICONTROL Create Data Element] dialog, specify the following information:

   * **[!UICONTROL Name]**: The name of your data element. For example `ECID`.

   * **[!UICONTROL Extension]**: Select **[!UICONTROL Experience Cloud ID Service]** from the list.

   * **[!UICONTROL Data Element Type]**: Select **[!UICONTROL ECID]** from the list.

     ![ECID Data Element](assets/ecid-dataelement.png)

1. Select **[!UICONTROL Save]**.

1. Continue with [XDM object data element](#xdm-object-data-element).

### XDM object data element

Finally, you now want to map any of your specific data elements to the schema you defined earlier. You define another data element which provides a representation of your XDM schema.

To define an XDM object data element:

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.

1. Select **[!UICONTROL Data Elements]** in the left rail.

1. Select **[!UICONTROL Add Data Element]**.

1. In the [!UICONTROL Create Data Element] dialog, specify the following information:

   * **[!UICONTROL Name]**: The name of your data element. For example `XDM - Page View`.

   * **[!UICONTROL Extension]**: Select **[!UICONTROL Adobe Experience Platform Web SDK]** from the list.

   * **[!UICONTROL Data Element Type]**: Select **[!UICONTROL XDM Object]** from the list.

   * **[!UICONTROL Sandbox]**: Select your sandbox from the list.

   * **[!UICONTROL Schema]**: Select your schema from the list.

1. Map the `identification > core > ecid` attribute, defined in your schema, to the ECID data element. Select the cylinder icon to easily pick the ECID data element from your list of data elements.

   ![Pick ECID Data Element](assets/pick-ecid-dataelement.png)

   ![Map ECID Data Element](assets/map-ecid.png)


1. Map the `web > webPageDetails > name` attribute, defined in your schema, to the Page Name data element.

   ![Map Page Name Data Element](assets/map-pagename.png)

1. Select **[!UICONTROL Save]**.

1. Continue with [Configure rules](#configure-rules).

## **Configure rules**

Tags in Adobe Experience Platform follow a rule-based system. They look for user interaction and associated data. When the criteria outlined in your rules are met, the rule triggers the extension, script, or client-side code you identified. You can use rules to send data (like an XDM object) into Adobe Experience Platform using the Adobe Experience Platform Web SDK extension.

To define a rule:

>[!NOTE]
>
>The following steps are an example of defining a rule that sends XDM data, containing values from other data elements, to Adobe Experience Platform. 
>
>You can use rules in various ways in your tag to manipulate variables (using your data elements). 
>
>See [Rules](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) for more information.

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.

1. Select **[!UICONTROL Rules]** in the left rail.

1. Select **[!UICONTROL Create New Rule]**.

1. In the [!UICONTROL Create Rule] dialog, specify the following information:

   * **[!UICONTROL Name]**: The name of the rule. For example `Page View`.

   * **[!UICONTROL Events]**: Select **[!UICONTROL + Add]**. Then, in the [!UICONTROL Event Configuration] dialog, specify the following information. When you are finished, select **[!UICONTROL Keep Changes]**.

     * **[!UICONTROL Extension]**: Select **[!UICONTROL Core]** from the list.

     * **[!UICONTROL Event Type]**: Select **[!UICONTROL Window Loaded]** from the list.

       ![Rule - Event Configuration](assets/event-windowloaded-pageview.png)

   * **[!UICONTROL Actions]**: Select **[!UICONTROL + Add]**. Then, in the [!UICONTROL Action Configuration] dialog, specify the following information. When you are finished, select **[!UICONTROL Keep Changes]**.

     * **[!UICONTROL Extension]**: Select **[!UICONTROL Adobe Experience Platform Web SDK]** from the list.

     * **[!UICONTROL Action Type]**: Select **[!UICONTROL Send Event]** from the list.

     * **[!UICONTROL Type]**: Select **[!UICONTROL web.webpagedetails.pageViews]** from the list.

     * **[!UICONTROL XDM data]**: Select the cylinder icon, then select **[!UICONTROL XDM - Page View]** from the list of data elements.

       ![Rule - Action Configuration](assets/action-pageview-xdm.png)

       Your rule should look like:

       ![Create Rule](assets/rule-pageview.png)

1. Select **[!UICONTROL Save]**.

## Build and publish your tag

After you define data elements and rules, you must build and publish your tag. When you create a library build, you must assign it to an environment. The build's extensions, rules, and data elements are then compiled and placed into the assigned environment. Each environment provides a unique embed code that allows you to integrate its assigned build into your site.

Adobe Experience Platform Tags support simple to complex publishing workflows that should accommodate your deployment of the Adobe Experience Platform Web SDK. See [Publishing overview](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) for more information.

To build and publish your tag:

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.

1. Select **[!UICONTROL Publishing Flow]** from the left rail.

1. Select **[!UICONTROL Select a working library]**, followed by **[!UICONTROL Add Library…]**.

1. In the [!UICONTROL Create Library] dialog, specify the following information:

    * **[!UICONTROL Name]**: The name of the library.

    * **[!UICONTROL Environment]**: Select **[!UICONTROL Development (development)]** from the list.

1. Select **[!UICONTROL + Add All Changed Resources]**.

   ![Publish - Create Library](assets/create-library-aep.png)

1. Select **[!UICONTROL Save & Build to Development]**.

    Your tag is saved and is build for your development environment. A green dot indicates a successful build of your tag on your development environment.

1. You can select **[!UICONTROL ...]** to rebuild the library or move the library to a staging or production environment.

   ![Publish - Build Library](assets/build-library.png)
