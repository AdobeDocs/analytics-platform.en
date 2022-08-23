# Statistical Calculations in CJA's Experimentation Panel: Details

This page documents the detailed statistical calculations used in CJA's Experimentation Panel. It is intended for technical users.


## Conversion Rate
The conversion rate or **mean**, *μ<sub>ν</sub>* for each variant *ν* in an Experiment is defined as a ratio of the sum of the metric to the number of units assigned to that metric, *N<sub>ν</sub>*:
<p style="text-align:center;"><img width=15% src="img/mean_definition.png" alt="metric-mean"></p>
Here, 

- *Y<sub>iν</sub>* is the value of the metric for each unit *i*, that has been assigned to a given variant *ν*. 
- The sum over units *i* depends on the choice of normalizing metric. 
    - If *People* is the normalizing metric, each unit is a unique person/profile. 
    - If *Sessions* is the normalizing metric, each unit is a unique session.
    - If *Events* is the normalizing metric, each unit is a unique event.

In general, this normalizing metric should be chosen to be equivalent to your unit of independence, i.e., if the behavior of a user in one session will be independent of their behavior in another session, then sessions is a reasonable normalizing metric. 

Wherever needed, the sample standard deviation is used, with the expression


<p style="text-align:center;"><img width=30% src="img/stdev_definition.png" alt="metric-mean"></p>


## Lift
The lift between a variant  *ν*, and the control variant  *ν<sub>0</sub>* is the relative "delta" in conversion rates, defined as 
<p style="text-align:center;"><img width=15% src="img/lift_definition.png" alt="metric-mean"></p>
where the individual conversion rates are as defined above.


## Confidence Sequences
While not displayed in the CJA Experimentation panel, the confidence sequence for an individual variant *ν* is central to the statistical methodology used by Adobe, and so is defined here (reproduced from [Waudby-Smith et al.](
https://doi.org/10.48550/arXiv.2103.06476)). 

> Suppose one is interested in estimating a target parameter *ψ* (like the conversion rate of a variant in an Experiment). Then, the dichotomy between a sequence of ‘fixed-time’ Confidence Intervals (CIs), and a time-uniform Confidence Sequence (CS) can be summarized as follows: 
<p style="text-align:center;"><img width=60% src="img/ci_vs_cs.png" alt="metric-mean"></p>

In words - for a regular Confidence Interval , the probabilistic guarantee that the target parameter lies within the range of values *Ċ<sub>t</sub>* is valid only at a single fixed value of *n* (where *n* is the number of samples). Conversely for a Confidence Sequence, we are guaranteed that at all times/ all values of the sample size *t*, the "true" value of the parameter of interest lies within the bounds *<SPAN STYLE="text-decoration:overline">C</SPAN><sub>t</sub>*.

This has a few deep implications which are very important for online testing:
- The CS can be optionally updated whenever new data becomes available.
- Experiments can be continuously monitored, adaptively stopped, or continued.
- The type-I error is controlled at all stopping times, including data-dependent times.

Adobe uses Asymptotic Confidence Sequences, which for an individual variant with mean estimate *μ* has the form

<p style="text-align:center;"><img width=45% src="img/confidence_sequence_individual.png" alt="metric-mean"></p>

Where:
- *N* is the number of units for that variant
- *σ* is a sample estimate of the standard deviation (defined previously)
- *α* is the desired level of type-I error (or miscoverage probability)
- *ρ*<sup>2</sup> is a constant that tunes the sample size at which the CS is tightest. Adobe has chosen a universal value of *ρ*<sup>2</sup> = 10<sup>-2.8</sup>, which is appropriate for the types of conversion rates seen in online experiments. 


## Confidence
The confidence used by Adobe is an "anytime valid" confidence, which is obtained by inverting the confidence sequence for the average treatment effect. 

To be precise, we note that in a two sample *t* test for the difference in means between two variants, there is a 1:1 mapping between the *p*-value for this test, and the confidence interval for the difference in means. By analogy, an anytime valid *p*-value can be obtained by inverting the (anytime valid) confidence sequence for the average treatment effect estimator:
<p style="text-align:center;"><img width=22% src="img/ate_definition.png" alt="metric-mean"></p>

The estimator we use is an inverse propensity weighted (IPW) estimator. Consider *N = N<sub>0</sub>* + *N<sub>1</sub>* units, the variant assignments for each unit $i$ labeled by *A<sub>i</sub>=0,1* if the unit is assigned to variant ν=0,1. If the users are assigned with fixed probability (propensity) *π<sub>0</sub>, (1-π<sub>0</sub>)*, and their outcome metric is *Y<sub>i</sub>*, then the IPW estimator is 
<p style="text-align:center;"><img width=45% src="img/ipw_definition.png" alt="metric-mean"></p>

Noting that *f* is the influence function, Waudby-Smith et al. showed that the Confidence Sequence for this estimator is:
<p style="text-align:center;"><img width=55% src="img/cs_ate_definition1.png" alt="metric-mean"></p>

Replacing the assignment probability by its empirical estimates: *π<sub>0</sub> = N<sub>0</sub>/N*, the variance term can be expressed in terms of individual sample mean estimates  *μ<sub>{0,1}</sub>* and standard deviation estimates,  *σ<sub>{0,1}</sub>* as:

<p style="text-align:center;"><img width=55% src="img/cs_ate_var.png" alt="metric-mean"></p>


Recalling that for a regular hypothesis test with test statistic *z =  (μ<sub>1</sub> - μ<sub>0</sub>)/ σ<sub>p</sub>*, there is a correspondence between $p$-values and confidence intervals:

<p style="text-align:center;"><img width=55% src="img/pvalue_ci_correspondence.png" alt="metric-mean"></p>

where *Φ* is the cumulative distribution of the standard normal. For anytime valid *p*-values, given the confidence sequence for the average treatment effect defined above, we can invert this relationship:
<p style="text-align:center;"><img width=75% src="img/anytimevalid-pvalue.png" alt="metric-mean"></p>

Finally, the **anytime valid *confidence*** is 
<p style="text-align:center;"><img width=22% src="img/anytimevalid-confidence.png" alt="metric-mean"></p>


## Declaring an Experiment to be Conclusive
For an Experiment with two arms, the CJA Experimentation panel displays a message stating that an Experiment is **conclusive** when the anytime valid confidence exceeds 95% (i.e., the anytime valid *p*-value is below 5%). 

When more than two variants are present, the Bonferonni correction is applied. For an experiment with *K* treatments, and a single baseline (control) treatment, there are *K-1* independent hypothesis tests. The Bonferonni correction means that we reject the null hypothesis that the control and a given variant have equal means, if the anytime valid *p*-value is below a threshold of 0.05/(K-1). 


## Best performing arm
When an experiment is declared conclusive, the best performing arm is displayed. This is the arm with the best performance (highest mean or conversion rate), among the Set that includes the control, and all arms that have a *p*-value that is below the Bonferonni threshold. 