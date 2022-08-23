# Introduction to Statistical Methodology in CJA's Experimentation Panel

This article describes the statistical calculations used by the Experimentation Panel in CJA. CJA uses advanced statistical methods to calculate **confidence** that is valid at any time, allowing you to run your experiments for as long as you want, and to monitor your results continuously. 

This article describes how A/B tests work, and provides an intuitive introduction to Adobe's ***Any Time Valid Confidence Sequences***. For expert users, the technical details and references are included at the end. 

## A/B testing and Causality
A/B tests are often described as a "gold standard" in evaluating the causal impact of some type of "intervention." They are randomized trials, which in the context of online testing, means that we expose some randomly selected users to a given variation of a website, message or email, and another randomly selected set of users to some other **variant** or **treatment**. After exposure, we then measure the outcome **metric(s)** we are interested in (e.g. opens of emails, subscriptions, or purchases). 

As illustrated in the image below, the fact that we randomly assigned users to each variant group means that on average the groups will share the same characteristics. Thus, any difference in outcomes can be interpreted as being due to the differences in the variants received, i.e. we are able to establish a **causal** link between our interventions and the outcomes we are interested in. This allows you to make rigorous, explainable, data driven decisions in optimizing your business goals, and so A/B testing is a fundamental part of the toolkit of any modern personalization practitioner. 

<p style="text-align:center;"><img width=75% src="img/causal-inference-cartoon.png" alt="causal-inf"></p>


Now, an important question is whether any observed differences are "real effects", or arise due to randomness. Intuitively, if there is only a small difference in the outcome metrics between groups, then this could have been observed by chance, while larger differences are more likely to be "real". The technical term here is that our measurements are *estimates* of the true values of the mean for each variant group. Statistical inference techniques give us ways to quantify the amount of uncertainty in our estimates - this is where the concepts of **p-values** and **Confidence Intervals** arise, but to understand these, we should first understand Statistical Errors. 

## Statistical Testing and Controlling Errors 
Many statistical inferencing methodologies are designed to control two types of errors: **False Positives** (Type-I errors), and **False Negatives** (Type-II Errors). These are illustrated in the table below. 


<p style="text-align:center;"><img width=50% src="img/contingency_table_stats_errors.png" alt="ContingencyTable"></p>


A False Positive is an incorrect rejection of the null hypothesis, when in fact it is true. In the context of online A/B tests, this means that we (falsely) conclude that the outcome business metric is different between variant arms, when in fact it was the same. Before we run the experiment, we typically pick a threshold *α*. After the experiment has run, the *p*-value is computed, and we reject the null if *p < α*. A commonly used threshold is *α*= 0.05, which means that in the long run, we expect 5 out of every 100 experiments to be false positives. 

Meanwhile, a False Negative means that we fail to reject the null hypothesis when in fact it is false. For A/B testing, this means that we do not reject the null hypothesis (recall, the null hypothesis states that the outcome business metric is the same between variant arms), when in fact it is different. To control this type of error, we generally need to have enough users in our experiment to guarantee a certain **Power**, defined as 1-*β* (i.e. one minus the probability of a type-II error). 

Most statistical inferencing techniques will require you to fix your sample size ahead of time, based on the effect size you wish to determine, as well as your error tolerance (*α* and *β*) ahead of time. However Adobe's methodology is designed to allow you to continuously look at your results, for any sample size. 



## Adobe's Statistical Methodology: _Anytime Valid Confidence Sequences_

To provide easily interpretable and safe statistical inference, Adobe has adopted a statistical methodology based on [_Anytime Valid Confidence Sequences_](
https://doi.org/10.48550/arXiv.2103.06476). 

A Confidence Sequence is a "sequential" analog of a Confidence Interval. To understand what a confidence sequence is, imagine repeating your experiments one hundred times, and calculating an estimate of the mean business metric (e.g. open rate of an email) and its associated 95%-Confidence Sequence for *every new user* that enters the experiment. A 95% Confidence Sequence will include the "true" value of the business metric in 95 out of the 100 experiments that you ran. (A 95% Confidence Interval could only be calculated once per experiment in order to give the same 95% coverage guarantee; not with every single new user). Confidence Sequences therefore allow you to continuously monitor experiments, without increasing False Positive error rates, i.e. they allow "peeking" at results. 

The difference between confidence sequences and confidence intervals for a single experiment is shown in the animation below:

<p style="text-align:center;"><img width=75% src="img/confidence-sequence-evolution-comparison.gif" alt="CSGIF"></p>


We note that confidence sequences shift the focus of A/B tests to *estimation* rather than hypothesis testing i.e., focusing on accurate estimation of the difference in means between treatments, rather than whether or not to reject a null hypothesis based on a threshold of statistical significance. 

However, in a similar manner to the relationship between $p$-values (or Confidence) and Confidence Intervals, there is also a relationship between Confidence Sequences and anytime valid $p$-values (or anytime valid Confidence). Given the familiarity of quantities like the Confidence, CJA provides the anytime valid Confidence in its reports.

The theoretical foundations of Confidence Sequences come from the study of sequences of random variables known as martingales. Some main results are included for expert readers below, but the takeways for practitioners are clear:


> Confidence sequences can be interpreted as "safe" sequential analogs of confidence intervals: you can look at and interpret data in your A/B test at any time you want, and safely stop, or continue experiments. The corresponding Anytime Valid Confidence (or *p*-value) is also safe to interpret.

It is important to note that because the statistical methodology is "anytime valid", it will be more conservative than a fixed horizon methodology applied at the same sample size. This means that the "anytime valid" *p*-values will generally be larger than corresponding fixed horizon *p*-values (i.e. the anytime valid confidence will be smaller)

## Interpreting the results 

1. **Experiment is Conclusive**: Every time you view the experimentation report, Adobe analyzes the data that has accumulated in the experiment up to this point and will declare an experiment to be “Conclusive” when the anytime valid confidence crosses a threshold of 95% for *at least one* of the variants (with a Bonferonni correction applied when there are more than two arms, to correct for multiple hypothesis testing).  

2. **Best Performing Variant**: When an experiment is declared to be conclusive, the variant with the highest conversion rate is labeled as the "best performing variant". Note that this variant must either be the control or baseline variant, or one of the variants that crosses the 95% anytime valid confidence threshold (with Bonferonni corrections applied).

3. **Conversion Rate**: The conversion rate that is shown is a ratio of the success metric value, to the normalizing metric value. Note that this may sometimes be larger than 1, if the metric is not binary (1 or 0 for each unit in the experiment)

4. **Lift**: The Experiment report summary shows the Lift over Baseline, which is a measure of the percentage improvement in conversion rate of a given variant over the baseline. Defined precisely, it is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

5. **Confidence**: The Anytime Valid Confidence that is shown, is a probabilistic measure of how much evidence there is that a given variant is the same as the control variant. A higher confidence indicates less evidence for the assumption that control and non-control variant have equal performance. More precisely, the confidence that is displayed is a probability (expressed as a percentage) that we would have observed a smaller difference in conversion rates between a given variant and the control, if in reality there is no difference in the true underlying conversion rates. In terms of *p*-values, the confidence displayed is 1 - *p*-value. 
 
Note however that a full description of results should consider all available evidence (i.e. experiment design, sample sizes, conversion rates, confidence etc.), and not just the declaration of conclusive or not. Even when a result is not yet “conclusive”, there can still be compelling evidence for one variant being different from another (e.g. confidence intervals are nearly non-overlapping). Ideally, decision making should be informed by all statistical evidence, interpreted on a continuous spectrum.
