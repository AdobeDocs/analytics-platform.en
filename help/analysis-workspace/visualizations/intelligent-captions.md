---
description: Use intelligent captions to generate natural-language insights to surface trends quickly within visualizations.
title: Intelligent captions
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
---
# Intelligent captions

Intelligent captions use advanced Machine Learning and Generative AI to provide valuable natural-language insights for Workspace visualizations. The initial release provides auto-generated insights for the [Line](line.md) visualization. Other visualizations will follow. 

Intelligent captions are geared towards:

* Analysts, who need narratives to share with other users. Analysts need these insights to be able to provide context to their users.
* Business users, who want to discover high-level takeaways quickly.

## Launch intelligent captions {#launch}

To launch auto-generated captions for a line visualization, click the **[!UICONTROL Intelligent captions]** icon at the top right of the visualization.

![Launch Analysis window showing the Intelligent captions for Product Views Trend. ](assets/intell-caps-1.png)

Natural-language insights are now being generated. 

Keep in mind that

* You need a minimum of 3 data points to generate captions successfully. Otherwise, you might get an error like **[!UICONTROL Not enough data to analyze]**.

* Captions are generated every time the underlying selected data changes in the table that powers the visualization. 

* If there are multiple metrics in the table, captions are only generated for the first metric or the metric currently selected by the user.

* If you save the project at a specific point, and re-load it later, the captions are auto-updated with new data. The same applies to scheduled projects and PDF files exported from a project.

Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)

## Actions

You can perform the following actions on intelligent captions:

### Copy to clipboard {#copy}

You can copy the captions to a clipboard and paste them into a PowerPoint or other tools. Select ![Copy captions to clipboard](/help/assets/icons/Copy.svg) at the top right of the captions dialog.

### Edit display {#edit}

You can edit the display of captions, such as hiding or unhiding a particular category of insights. 

1. Select ![Edit intelligent captions display](/help/assets/icons/EditInLight.svg) in the Intelligent captions dialog.

1. Toggle between ![Visibility](/help/assets/icons/Visibility.svg) to display a specific insight (like **[!UICONTROL Min]**), or ![VisibilityOff](/help/assets/icons/VisibilityOff.svg) to hide a specific insight (like **[!UICONTROL Spike]**).

   ![Edit intelligent captions](assets/edit-intelligent-captions.png)

1. Select **[!UICONTROL Apply]**.


### Provide feedback

You can provide feedback on the generated intelligent captions.

1. Select ![More actions](/help/assets/icons/More.svg) in the Intelligent captions dialog.

1. Select ![Good response](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL Good response]**, ![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL Bad response]**, or ![Flag](/help/assets/icons/Flag.svg) **[!UICONTROL Report]**.

1. In the **[!UICONTROL Thank you for your feedback]** dialog, provide your feedback and select **[!UICONTROL Submit]** to submit the feedback.

### Export {#export}

You can export intelligent captions as part of a PDF, as long as the project is saved with the intelligent captions generated.

### Toggle off {#toggle}

If you would rather not show intelligent captions, you can toggle the feature off. 

1. Go to [Visualizations preferences](/help/analysis-workspace/user-preferences.md#visualizations-preferences).
1. Uncheck **[!UICONTROL Show intelligent captions]**.

   ![Line visualization options showing the option to uncheck Show intelligent captions.](assets/toggle-captions.png)

1. Select **[!UICONTROL Save]** to save the preference.


## Intelligent captions in Mobile Scorecards

Intelligent captions are also available in Customer Journey Analytics [mobile scorecards](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions).

## Feature Access

The following parameters govern access to Intelligent captions:

* **Solution access**: The Intelligent captions feature is available in Customer Journey Analytics, but not in Adobe Analytics.

* **Contractual access**: If you are not able to use Intelligent captions, please contact your organization's administrator or Adobe Account Representative. Before you can use Intelligent captions in your organization, you must agree to certain GenAI-related legal terms.

* **Permissions**: In the [!UICONTROL Adobe Admin Console], the [!UICONTROL Reporting Tools] **[!UICONTROL Intelligent Captions]** permission determines access. A [product profile admin](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html) needs to follow these steps in the [!UICONTROL Admin Console]:
   1. Navigate to **[!UICONTROL Admin Console]** > **[!UICONTROL Products and services]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL Product Profiles]**.
   1. Select the title of the product profile for which you want to provide access to Intelligent captions.
   1. In the specific product profile, select **[!UICONTROL Permissions]**.
   1. Select ![Edit](/help/assets/icons/Edit.svg) to edit **[!UICONTROL Reporting Tools]**.
   1. Select ![AddCircle](/help/assets/icons/AddCircle.svg) to add **Intelligent Captions** to **[!UICONTROL Included permission items]**.

      ![Add permission](./assets/intelligent-captions-permissions.png)

   1. Select **[!UICONTROL Save]** to save the permissions.

See [Access control](/help/technotes/access-control.md#access-control) for more information.
