---
description: Learn how you can analyze the results of A/B tests in the Customer Journey Analytics Experimentation panel.
title: Experimentation panel
feature: Panels
exl-id: e11169b4-2c73-4dd4-bca7-c26189d60631
---
# Experimentation panel

The **[!UICONTROL Experimentation]** panel lets analysts compare different user experience, marketing, or messaging variations to determine which is best at driving a specific outcome. You can evaluate the lift and confidence of any A/B experiment from any experimentation platform - online, offline, from Adobe solutions, Adobe Journey Optimizer, and even BYO (bring-your-own) data.

>[!IMPORTANT]
>
>At this point, [Adobe Analytics for Target](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=en) (A4T) data *cannot* be analyzed in the Experimentation panel. 

## Access Control {#access}

The Experimentation panel is available to use by all Customer Journey Analytics users. No Admin rights or other permissions are required. However, the setup (steps 1 and 2 below) requires actions that only Admins can perform.

## New functions in Calculated Metrics {#functions}

Two new advanced functions were added: [!UICONTROL Lift] and [!UICONTROL Confidence]. For more information, see [Reference - advanced functions](/help/components/calc-metrics/cm-adv-functions.md).

## Step 1: Create connection to experiment dataset/s {#connection}

The recommended data schema is for the experiment data to be in an [Object array](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/fields/array.html?lang=en) that contains the experiment and variant data in two separate dimensions. Both dimensions need to be in a **single** object array. If you have your experiment data in a single dimension with experiment and variant data in a delimited string, you can use the [substring](/help/data-views/component-settings/substring.md) setting in data views to split them into two for use in the panel.

After your experiment data has been [ingested](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html) into Adobe Experience Platform, [create a connection in Customer Journey Analytics](/help/connections/create-connection.md) to one or more experiment dataset/s.

## Step 2: Add context labels in data views {#contect-labels}

In Customer Journey Analytics data views settings, admins can add [context labels](/help/data-views/component-settings/overview.md) to a dimension or metric and Customer Journey Analytics services like [!UICONTROL Experimentation] panel can use these labels for their purposes. Two pre-defined labels are used for the Experimentation panel:

* [!UICONTROL Experimentation Experiment]
* [!UICONTROL Experimentation Variant]

In your data view that contains experimentation data, pick two dimension, one with the experimentation data and one with the variant data. Then label those dimensions with the **[!UICONTROL Experiment]** and the **[!UICONTROL Variant]** labels.

![Context label options for Experimentation and Experimentation Variant.](assets/context-label.png)

Without these labels present, the Experiment panel does not work, since there are no experiments to work with.

## Step 3: Configure the Experiment panel {#configure}

1. In Customer Journey Analytics Workspace, drag the Experimentation panel into a project.

  ![The Experimention panel dragged into a project.](assets/experiment.png)

   >[!IMPORTANT]
   >If the necessary setup in Customer Journey Analytics data views has not been completed, you will receive this message before you can proceed: "[!UICONTROL Please configure the experiment and variant dimensions in Data Views]".

1. Configure the panel input settings.

   | Setting | Definition |
   | --- | --- |
   | **[!UICONTROL Experiment]** | A set of variations on an experience that were exposed to end users in order to determine which is best to keep in perpetuity. An experiment is made up of two or more variants, one of which is considered the control variant. This setting is pre-populated with the dimensions that have been labeled with the  **[!UICONTROL Experiment]** label in data views, and the last 3 months' worth of experiment data. |
   | **[!UICONTROL Control Variant]** | One of two or more alterations in an end user's experience that are being compared for the purpose of identifying the better alternative. One variant must be selected as the control, and only one variant can be considered to be the control variant. This setting is pre-populated with the dimensions that have been labeled with the  **[!UICONTROL Variant]** label in data views. This setting pulls up the variant data that is associated with this experiment. |
   | **[!UICONTROL Success Metrics]** | The metric or metrics that a user is comparing variants with. The variant with the most desirable outcome for the conversion metric (whether highest or lowest) is declared the "best performing variant" of an experiment. You can add up to 5 metrics. |
   | **[!UICONTROL Normalizing Metric]** | The basis ([!UICONTROL People], [!UICONTROL Sessions], or [!UICONTROL Events]) on which a test will be run. For example, a test may compare the conversion rates of several variations where **[!UICONTROL Conversion rate]** is calculated as **[!UICONTROL Conversions per session]** or **[!UICONTROL Conversions per person]**. |
   | **[!UICONTROL Date Range]** | The date range is automatically set, based on the first event received in Customer Journey Analytics for the experiment selected. You can restrict or expand the date range to a more specific timeframe if needed. |

1. Click **[!UICONTROL Build]**.

## Step 4: View the panel output {#view}

The Experimentation panel returns a rich set of data and visualizations to help you better understand how your experiments are performing. At the top of the panel, a summary line is provided to remind you of the panel settings you selected. At any time, you can edit the panel by clicking the edit pencil at the top right.

You also get a text summary that indicates whether the experiment is conclusive or not, and summarizes the outcome. Conclusiveness is based on statistical significance. (See "Statistical methodology" below.) You can see summary numbers for the best performing variant with the highest lift and confidence.

For each success metric you selected, one freeform table and one conversion rate trend will be shown.

![The Experimentation output showing one freeform table and one conversion rate trend.](assets/exp-output1.png)

The [!UICONTROL Line] chart gives you the [!UICONTROL Control] versus [!UICONTROL Control Variant] performance:

![The line chart output showing Control versus Control Variant performance.](assets/exp-output2.png)

>[!NOTE]
>
>This panel currently does not support analysis of A/A tests.

## Step 5: Interpret the results {#interpret}

1. **Experiment is Conclusive**: Every time you view the experimentation report, Adobe analyzes the data that has accumulated in the experiment up to this point and will declare an experiment to be "Conclusive" when the anytime valid confidence crosses a threshold of 95% for *at least one* of the variants (with a Benjamini-Hochberg correction applied when there are more than two arms, to correct for multiple hypothesis testing).  

2. **Best Performing Variant**: When an experiment is declared to be conclusive, the variant with the highest conversion rate is labeled as the "best performing variant". Note that this variant must either be the control or baseline variant, or one of the variants that crosses the 95% anytime valid confidence threshold (with Benjamini-Hochberg corrections applied).

3. **Conversion Rate**: The conversion rate that is shown is a ratio of the success metric value, to the normalizing metric value. Note that this may sometimes be larger than 1, if the metric is not binary (1 or 0 for each unit in the experiment)

4. **Lift**: The Experiment report summary shows the Lift over Baseline, which is a measure of the percentage improvement in conversion rate of a given variant over the baseline. Defined precisely, it is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage.

5. **Confidence**: The Anytime Valid Confidence that is shown, is a probabilistic measure of how much evidence there is that a given variant is the same as the control variant. A higher confidence indicates less evidence for the assumption that control and non-control variant have equal performance. More precisely, the confidence that is displayed is a probability (expressed as a percentage) that we would have observed a smaller difference in conversion rates between a given variant and the control, if in reality there is no difference in the true underlying conversion rates. In terms of *p*-values, the confidence displayed is 1 - *p*-value.

>[!NOTE]
>
>A full description of results should consider all available evidence (i.e. experiment design, sample sizes, conversion rates, confidence etc.), and not just the declaration of conclusive or not. Even when a result is not yet "conclusive", there can still be compelling evidence for one variant being different from another (e.g. confidence intervals are nearly non-overlapping). Ideally, decision making should be informed by all statistical evidence, interpreted on a continuous spectrum.

## Adobe's statistical methodology {#statistics}

To provide easily interpretable and safe statistical inference, Adobe has adopted a statistical methodology based on [Anytime Valid Confidence Sequences](https://doi.org/10.48550/arXiv.2103.06476).

A Confidence Sequence is a "sequential" analog of a Confidence Interval. To understand what a confidence sequence is, imagine repeating your experiments one hundred times, and calculating an estimate of the mean business metric (e.g. open rate of an email) and its associated 95%-Confidence Sequence for *every new user* that enters the experiment.

A 95% Confidence Sequence will include the "true" value of the business metric in 95 out of the 100 experiments that you ran. (A 95% Confidence Interval could only be calculated once per experiment in order to give the same 95% coverage guarantee; not with every single new user). Confidence Sequences therefore allow you to continuously monitor experiments, without increasing False Positive error rates, i.e. they allow "peeking" at results.

## Interpret non-randomized dimensions {#non-randomized}

Customer Journey Analytics allows analysts to select any dimension as the "experiment". But how do you interpret an analysis where the dimension chosen as the experiment is not one for which persons are randomized?

For example, consider an ad that a person sees. You may be interested in measuring the change in some metric (e.g., average revenue) if you decide to show persons "ad B" instead of "ad A". The causal effect of showing ad B in place of ad A is of central importance in arriving at the marketing decision. This causal effect may be measured as the average revenue over the whole population, if we replaced the status quo of showing ad A with the alternate strategy of showing ad B. 

A/B testing is the gold standard within the industry for objectively measuring the effects of such interventions. The critical reason why an A/B test gives rise to a causal estimate is due to the randomization of persons to receive one of the possible variants. 

Now consider a dimension that is not achieved by randomization, for example, the US state of the person. Let's say that our persons primarily come from two states, New York and California. The average revenue of sales of a winter clothing brand can be different in the two states due to the differences in the regional weather. In such a situation, the weather may be the true causal factor behind winter clothing sales, and not the fact that the geographical states of persons are different.

The experimentation panel in Customer Journey Analytics lets you analyze data as average revenue difference by states of the persons. In such a situation, the output does not have a causal interpretation. However, such an analysis may still be of interest. It provides an estimate (along with measures of uncertainty) of the difference in average revenue by states of the persons. This is also referred to as "Statistical Hypothesis Testing". The output of this analysis may be interesting, but not necessarily actionable, since we have not and sometimes cannot randomize persons to one of the possible values of the dimension. 

The following illustration contrasts these situations:

![A Diagram showing Observational Data and the Randomized Experiment.](assets/randomize.png)

When you want to measure the impact of intervention X on outcome Y, it is possible that the real cause of both is the confounding factor C. If the data is not achieved by randomizing persons on X, the impact is harder to measure, and the analysis will explicitly account for C. Randomization breaks the dependence of X on C, allowing us to measure the effect of X on Y without having to worry about other variables. 

## Use calculated metrics in the Experimentation panel

Refer to this blog post for information on [using derived metrics in the Experimentation panel](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/using-derived-metrics-in-cja-s-experimentation-panel/ba-p/593119).
