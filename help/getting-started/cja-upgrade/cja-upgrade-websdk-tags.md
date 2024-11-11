---
title: Use Tags to implement the Web SDK for Customer Journey Analytics
description: Learn how to use Tags to implement the Web SDK for Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: yes
hidefromtoc: yes
exl-id: b6de921c-4f96-40ad-bb49-873094627192
---
# Use Tags to implement the Web SDK for Customer Journey Analytics

>[!NOTE]
> 
>Follow the steps on this page only after you complete all previous upgrade steps. You can follow the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations), or you can follow the upgrade steps that were dynamically generated for your organization with the [Adobe Analytics to Customer Journey Analytics upgrade questionnaire](https://gigazelle.github.io/cja-ttv/). 
>
>After you complete the steps on this page, continue following the recommended upgrade steps or the dynamically generated upgrade steps. 

You can use the Tags feature within Adobe Experience Platform to implement code on your site to collect data. This tag management solution lets you deploy code alongside other tagging requirements. Tags offer seamless integration with Adobe Experience Platform using the Adobe Experience Platform Web SDK extension.

## Create your tag

1. Log in to experience.adobe.com using your Adobe ID credentials.

1. In Adobe Experience Platform, go to **[!UICONTROL Data Collection]** > **[!UICONTROL Tags]**.

1. Select **[!UICONTROL New Property]**. 

    Name the tag, select **[!UICONTROL Web]** and enter a domain name. Select **[!UICONTROL Save]** to continue.

    ![Create a property](assets/create-property.png)

## Configure your tag

After creating the tag, you must configure it with the correct extensions and configure data elements and rules according to how you want to track your site and send data to Adobe Experience Platform. 

Select your newly created tag from the list of [!UICONTROL Tag Properties] to open it.


### **Extensions**

To ensure you can send data to Adobe Experience Platform (via your datastream), add the Adobe Platform Web SDK extension to your tag.

To create and configure the Adobe Experience Platform Web SDK extension:

1. Select **[!UICONTROL Extensions]** in the left rail.

1. Select **[!UICONTROL Catalog]** in the top bar.

1. Search for or scroll to the Adobe Experience Platform Web SDK extension, and Select **[!UICONTROL Install]** to install it.

   <img src="assets/aepwebsdk-extension.png" width="35%"/>

1. Select your sandbox and your earlier created datastream for your [!UICONTROL Production Environment] and (optional) [!UICONTROL Staging Environment] and [!UICONTROL Development Environment].

   ![AEP Web SDK extension configuration](assets/aepwebsk-extension-datastreams.png)

   Select **[!UICONTROL Save]**.

See [Configure the Adobe Experience Platform Web SDK extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration.html) for more information.

The Web SDK includes the [!UICONTROL Adobe Experience Cloud ID Service] natively, so you do not need to add the ID service extension to your tag.

### **Data Elements**

Data elements are the building blocks for your data dictionary (or data map). Use data elements to collect, organize, and deliver data across marketing and ad technology. You set up data elements in your tag that read from your data layer and can be used to deliver data into Adobe Experience Platform.

There are different types of data elements. You first set up a data element to capture the page name persons are viewing on your site.

To define a page name data element:

1. Select **[!UICONTROL Data Elements]** in the left rail.

2. Select **[!UICONTROL Add Data Element]**.

3. In the [!UICONTROL Create Data Element] dialog:

   - Name your data element, for example `Page Name`.

   - Select **[!UICONTROL Core]** from the [!UICONTROL Extension] list.

   - Select **[!UICONTROL Page Info]** from the [!UICONTROL Data Element Type] list.

   - Select **[!UICONTROL Title]** from the [!UICONTROL Attribute] list.

     ![Create Date Element using Page Info](assets/create-dataelement-1.png)

     Alternatively you could have used the value from a variable of your data layer, for example `pageName` and the [!UICONTROL JavaScript Variable] data element type to define the data element.

     ![Create Data Element using Javascript Variable](assets/create-dataelement-2.png)

   - Select **[!UICONTROL Save]**.

You now want to set up a data element referencing the Experience Cloud ID that is automatically provided by the Adobe Experience Platform Web SDK and available through the Experience Cloud ID Service extension.

To define an ECID data element:

1. Select **[!UICONTROL Data Elements]** in the left rail.

2. Select **[!UICONTROL Add Data Element]**.

3. In the [!UICONTROL Create Data Element] dialog:

   - Name your data element, for example `ECID`.

   - Select **[!UICONTROL Experience Cloud ID Service]** from the [!UICONTROL Extension] list.

   - Select **[!UICONTROL ECID]** from the [!UICONTROL Data Element Type] list.

     ![ECID Data Element](assets/ecid-dataelement.png)

   - Select **[!UICONTROL Save]**.

Finally, you now want to map any of your specific data elements to the schema you defined earlier. You define another data element which provides a representation of your XDM schema.

To define an XDM object data element:

1. Select **[!UICONTROL Data Elements]** in the left rail.

2. Select **[!UICONTROL Add Data Element]**.

3. In the [!UICONTROL Create Data Element] dialog:

   - Name your data element, for example `XDM - Page View`.

   - Select **[!UICONTROL Adobe Experience Platform Web SDK]** from the [!UICONTROL Extension] list.

   - Select **[!UICONTROL XDM Object]** from the [!UICONTROL Data Element Type] list.

   - Select your sandbox from the [!UICONTROL Sandbox] list.

   - Select your schema from the [!UICONTROL Schema] list.

   - Map the `identification > core > ecid` attribute, defined in your schema, to the ECID data element. Select the cylinder icon to easily pick the ECID data element from your list of data elements.

     ![Pick ECID Data Element](assets/pick-ecid-dataelement.png)

        ![Map ECID Data Element](assets/map-ecid.png)


   - Map the `web > webPageDetails > name` attribute, defined in your schema, to the Page Name data element.

        ![Map Page Name Data Element](assets/map-pagename.png)

   - Select **[!UICONTROL Save]**.


### **Rules**

Tags in Adobe Experience Platform follow a rule-based system. They look for user interaction and associated data. When the criteria outlined in your rules are met, the rule triggers the extension, script, or client-side code you identified. You can use rules to send data (like an XDM object) into Adobe Experience Platform using the Adobe Experience Platform Web SDK extension.

To define a rule:

1. Select **[!UICONTROL Rules]** in the left rail.

1. Select **[!UICONTROL Create New Rule]**.

1. In the [!UICONTROL Create Rule] dialog:

   - Name the rule, for example `Page View`.

   - Select **[!UICONTROL + Add]** underneath [!UICONTROL Events]. 
    
   - In the [!UICONTROL Event Configuration] dialog:

     - Select **[!UICONTROL Core]** from the [!UICONTROL Extension] list.

     - Select **[!UICONTROL Window Loaded]** from the [!UICONTROL Event Type] list.

       ![Rule - Event Configuration](assets/event-windowloaded-pageview.png)

     - Select **[!UICONTROL Keep Changes]**.



   - Select **[!UICONTROL + Add]** underneath [!UICONTROL Actions]. 
    
   - In the [!UICONTROL Action Configuration] dialog:

     - Select **[!UICONTROL Adobe Experience Platform Web SDK]** from the [!UICONTROL Extension] list.

     - Select **[!UICONTROL Send Event]** from the [!UICONTROL Action Type] list.

     - Select **[!UICONTROL web.webpagedetails.pageViews]** from the [!UICONTROL Type] list.

     - Select the cylinder icon next to  [!UICONTROL XDM data] and Select **[!UICONTROL XDM - Page View]** from the list of data elements.

      ![Rule - Action Configuration](assets/action-pageview-xdm.png)

     - Select **[!UICONTROL Keep Changes]**.

   - Your rule should look like:

     ![Create Rule](assets/rule-pageview.png)

1. Select **[!UICONTROL Save]**.

The above is just an example of defining a rule that sends XDM data, containing values from other data elements, to Adobe Experience Platform. 

You can use rules in various ways in your tag to manipulate variables (using your data elements). 

See [Rules](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/rules.html) for more information.

## Build and Publish your tag

After having defined data elements and rules, you must build and publish your tag. When you create a library build, you must assign it to an environment. The build's extensions, rules, and data elements are then compiled and placed into the assigned environment. Each environment provides a unique embed code that allows you to integrate its assigned build into your site.

To build and publish your tag:

1. Select **[!UICONTROL Publishing Flow]** from the left rail.

2. Select **[!UICONTROL Select a working library]**, followed by **[!UICONTROL Add Library…]**.

3. In the [!UICONTROL Create Library] dialog:

    - Name the library.

    - Select **[!UICONTROL Development (development)]** from the [!UICONTROL Environment] list.

    - Select **[!UICONTROL + Add All Changed Resources]**.

        ![Publish - Create Library](assets/create-library-aep.png)

    - Select **[!UICONTROL Save & Build to Development]**.

    Your tag is saved and is build for your development environment. A green dot indicates a successful build of your tag on your development environment.

4. You can select **[!UICONTROL ...]** to rebuild the library or move the library to a staging or production environment.

    ![Publish - Build Library](assets/build-library.png)

Adobe Experience Platform Tags support simple to complex publishing workflows that should accommodate your deployment of the Adobe Experience Platform Web SDK. 

See [Publishing overview](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) for more information.


## Retrieve your tag code

Finally you must install your tag on the website you want to track, which implies placing code in the header tag of your website's template.

To get the code that references your tag:

1. Select **[!UICONTROL Environments]** in the left rail.

1. From the list of environments, select the correct install (box) button.

   In the [!UICONTROL Web Install Instructions] dialog, select the copy button next to the script code that should read like:

   ```
   <script src="https://assets.adobedtm.com/2a518741ab24/.../launch-...-development.min.js" async></script>>
         
   ```   

   ![Environment](assets/environment.png)

1. Select **[!UICONTROL Close]**.

   Instead of the code for the development environment, you could have selected another environment (staging, production) based on where you are in the process of deploying the Adobe Experience Platform Web SDK. 

   See [Environments](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/environments/environments.html?) for more information.

1. Continue following the [recommended upgrade steps](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations) or the [dynamically generated upgrade steps](https://gigazelle.github.io/cja-ttv/).
