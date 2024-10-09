---
title: Reference - advanced functions
description: Access these functions by checking Show Advanced in the Functions drop-down list.
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
---
# Reference - advanced functions

Access these functions by selecting **[!UICONTROL Show all]** below ![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Functions]** list in the Components panel. Scroll down to see the list of Advanced functions.

## Table functions versus row functions 

A table function is one where the output is the same for every row of the table. A row function is one where the output is different for every row of the table. Where applicable and relevant, a function is annotated with the type of function.

## What does the include-zeros parameter mean?

It tells whether to include zeros in the computation. Sometimes zero means *nothing*, but sometimes it's important.

For example, if you have a Revenue metric, and then add a Page Views metric to the report, there are suddenly more rows for your revenue which are all zero. You probably don't want this to affect any [MEAN](cm-functions.md#mean), [MIN](cm-functions.md#row-min), [QUARTILE](cm-functions.md#quartile), and more calculations that you have on the revenue column. In this case, you would check the `include-zeros` parameter.

On the other hand, if you have two metrics that you are interested in, it may not be fair to say that one has a higher average or minimum because some of its rows were zeros, so you would not check the parameter to include the zeros.


## And

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**


Conjunction. Not equal to zero is considered to be true and equals zero is considered to be false. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| logical_test| Requires at least one parameter but can take any number of parameters. Any value or expression that can be evaluated to TRUE or FALSE |

## Approximate Count Distinct

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


Returns the approximated distinct count of dimension items for the selected dimension.


| Argument | Description |
|---|---|
| dimension| The dimension for which you want the approximated distinct item count |

### Example

A common use case for this function is when you want to get approximate number of customers.




## Arc Cosine

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE Row]{type="Neutral"} Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).


| Argument | Description |
|---|---|
| metric| The cosine of the angle you want from -1 to 1 |



## Arc Sine

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE Row]{type="Neutral"} Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).


| Argument | Description |
|---|---|
| metric| The sine of the angle you want from -1 to 1 |



## Arc Tangent

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE Row]{type="Neutral"} Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).


| Argument | Description |
|---|---|
| metric| The tangent of the angle you want from -1 to 1 |



## Cdf-T

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**


Returns the probability that a random variable with student-t distribution with n degrees of freedom will have a z-score less than col.


| Argument | Description |
|---|---|
| metric| The metric for which you would like the Cumulative Distribution Function of the student t-distribution |
| number| The degrees of freedom for the Cumulative Distribution Function of the student t-distribution |

### Example

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )

```


## Cdf-Z

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**


Returns the probability that a random variable with normal distribution will have a z-score less than col.


| Argument | Description |
|---|---|
| metric| The metric for which you would like the Cumulative Distribution Function of the Standard Normal Distribution |

### Examples

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Ceiling

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**


[!BADGE Row]{type="Neutral"} Returns the smallest integer not less than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula CEILING(Revenue) to round revenue up to the nearest dollar, or $570.


| Argument | Description |
|---|---|
| metric| The metric that you want to round |


## Confidence (Lower)

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calculate the any-time-valid confidence **lower** using the WASKR method as described in [Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476.pdf).

Confidence is a probabilistic measure of how much evidence there is that a given variant is the same as the control variant. A higher confidence indicates less evidence for the assumption that control and non-control variant have equal performance. 

| Argument | Description |
| --- | --- |
| normalizing-container | The basis (People, Sessions, or Events) on which a test will be run. |
| success-metric | The metric or metrics that a user is comparing variants with. |
| control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |
| significance-threshold | The threshold in this function is set to a default of 95%. |

## Confidence (Upper)

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

Calculate the any-time-valid confidence **upper** using the WASKR method as described in [Time-uniform central limit theory and asymptotic confidence sequences](https://arxiv.org/pdf/2103.06476.pdf).

Confidence is a probabilistic measure of how much evidence there is that a given variant is the same as the control variant. A higher confidence indicates less evidence for the assumption that control and non-control variant have equal performance. 

| Argument | Description |
| --- | --- |
| normalizing-container | The basis (People, Sessions, or Events) on which a test will be run. |
| success-metric | The metric or metrics that a user is comparing variants with. |
| control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |
| significance-threshold | The threshold in this function is set to a default of 95%. |


## Cosine

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE Row]{type="Neutral"} Returns the cosine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

| Argument | Description |
|---|---|
| metric| The angle in radians for which you want the cosine |


## Cube Root

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


Returns the positive cube root of a number. The cube root of a number is the value of that number raised to the power of 1/3.


| Argument | Description |
|---|---|
| metric| The metric for which you want the cube root |



## Cumulative

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

Returns the sum of the last n elements of column x. If n > 0, sum the last n elements or x. If n < 0, sum all of the preceding elements.

| Argument | Description |
| --- | --- |
| number | The last N number of rows to return the sum for. If N <= 0 use all previous rows. |
| metric | The metric for which you would like the Cumulative Sum. |

### Examples

| Date | Revenue  | CUMULATIVE(0, Revenue) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| May  | $500 | $500         | $500         |
| June | $200 | $700         | $700         |
| July | $400 | $1100        | $600         |


## Cumulative (Average)

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

Returns the average of the last n elements of column x. If n > 0, sum the last n elements or x. If n < 0, sum all of the preceding elements.

| Argument | Description |
| --- | --- |
| number | The last N number of rows to return the average for. If N <= 0 use all previous rows. |
| metric | The metric for which you would like the Cumulative Average. |

>[!NOTE]
>
>This does not work as you might expect with rate metrics like revenue/person: it averages the rates instead of summing revenue over the last N and summing persons over the last N and then dividing them. <br/>Instead, use [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![Divide](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative).
>


## Equal

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**


Equal. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| metric_X | |
| metric_Y | |

### Example

`Metric 1 = Metric 2`



## Exponential regression: Correlation coefficient

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Exponential regression: Y = a exp(X) + b. Returns the correlation coefficient.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to correlate with metric_Y |
| metric_Y| A metric that you would like to correlate with metric_X |
| include_zeros | Whether or not to include zero values in the calculations |

## Exponential regression: Predicted Y

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Row]{type="Neutral"} Exponential regression: Y = a exp(X) + b. Returns Y.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the independent data. |
| metric_Y| A metric that you would like to designate as the dependent data. |
| include_zeros | Whether or not to include zero values in the calculations |


## Exponential regression: Intercept

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Exponential regression: Y = a exp(X) + b. Returns b.

| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |


## Exponential regression: Slope

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Exponential regression: Y = a exp(X) + b. Returns a.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |


## Floor

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE Row]{type="Neutral"} Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR(Revenue) to round revenue down to the nearest dollar, or $569.

| Argument | Description |
|---|---|
| metric | The metric that you want to round. |


## Greater Than

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**


Greater than. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| metric_X | |
| metric_Y | |

### Example

`Metric 1 > Metric 2`

## Greater Than or Equal

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**


Greater than or equal. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| metric_X ||
| metric_Y||

### Example

`Metric 1 >= Metric 2`



## Hyperbolic Cosine

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE Row]{type="Neutral"} Returns the hyperbolic cosine of a number.


| Argument | Description |
|---|---|
| metric| The angle in radians for which you want to find the hyperbolic cosine |



## Hyperbolic Sine

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**


[!BADGE Row]{type="Neutral"} Returns the hyperbolic sine of a number.


| Argument | Description |
|---|---|
| metric| The angle in radians for which you want to find the hyperbolic sine |



## Hyperbolic Tangent

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**


[!BADGE Row]{type="Neutral"} Returns the hyperbolic tangent of a number.


| Argument | Description |
|---|---|
| metric| The angle in radians for which you want to find the hyperbolic tangent |


## If

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE Row]{type="Neutral"} If the value of the condition parameter is non-zero (true), then the result will be the value of the then parameter. Otherwise it will be the value of the else parameter.


| Argument | Description |
|---|---|
| logical_test| Required. Any value or expression that can be evaluated to TRUE or FALSE |
| value_if_true| The value that you want to be returned if the logical_test argument evaluates to TRUE. (This argument defaults to 0 if not included.) |
| value_if_false| The value that you want to be returned if the logical_test argument evaluates to FALSE. (This argument defaults to 0 if not included.) |


## Less Than

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**


Less than. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| metric_X | |
| metric_Y | |


### Example

`Metric 1 < Metric 2`

## Less Than or Equal

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

Less than or equal. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| metric_X | |
| metric_Y | |

### Example

`Metric 1 <= Metric 2`



## Linear regression: Correlation coefficient

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"}  Linear regression: Y = a X + b.  Returns the correlation coefficient


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to correlate with metric_Y |
| metric_Y| A metric that you would like to correlate with metric_X |
| include_zeros | Whether or not to include zero values in the calculations |



## Linear regression: Intercept

[!BADGE Table]{type="Neutral"}  ![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


Linear regression: Y = a X + b. Returns b.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Linear regression: Predicted Y

[!BADGE Row]{type="Neutral"}  ![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


Linear regression: Y = a X + b. Returns Y.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Linear regression: Slope

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"}  Linear regression: Y = a X + b. Returns a.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |


## Log Base 10

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE Row]{type="Neutral"} Returns the base-10 logarithm of a number.


| Argument | Description |
|---|---|
| metric| The positive real number for which you want the base-10 logarithm |


## Log regression: Correlation coefficient

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} [!BADGE Table]{type="Neutral"} Log regression: Y = a ln(X) + b. Returns the correlation coefficient.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to correlate with metric_Y |
| metric_Y| A metric that you would like to correlate with metric_X |
| include_zeros | Whether or not to include zero values in the calculations |


## Log regression: Intercept

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


Log regression: Y = a ln(X) + b. Returns b.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Log regression: Predicted Y

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Row]{type="Neutral"} Log regression: Y = a ln(X) + b. Returns Y.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Log regression: Slope

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Log regression: Y = a ln(X) + b. Returns a.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Natural Log

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**


Returns the natural logarithm of a number. Natural logarithms are based on the constant e (2.71828182845904). LN is the inverse of the EXP function.


| Argument | Description |
|---|---|
| metric| The positive real number for which you want the natural logarithm |



## Not

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**


Negation as a boolean. The output will be either 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| logical| Required. A value or expression that can be evaluated to TRUE or FALSE |



## Not Equal

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


Not Equal. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| metric_X | |
| metric_Y | |

### Example

`Metric 1 != Metric 2`


## Or

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE Row]{type="Neutral"} Disjunction. Not equal to zero is considered to be true and equals zero is considered to be false. The output will be either a 0 (false) or 1 (true).


| Argument | Description |
|---|---|
| logical_test| Requires at least one parameter but can take any number of parameters. Any value or expression that can be evaluated to TRUE or FALSE |


>[!NOTE]
>
>0 (zero) means False, and any other value is True.


## Pi

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

Returns Pi: 3.14159...


## Power regression: Correlation coefficient

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Power regression: Y = b X ^ a. Returns the correlation coefficient.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to correlate with metric_Y |
| metric_Y| A metric that you would like to correlate with metric_X |
| include_zeros | Whether or not to include zero values in the calculations |



## Power regression: Intercept

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Power regression: Y = b X ^ a. Returns b.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |


## Power regression: Predicted Y

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Row]{type="Neutral"} Power regression: Y = b X ^ a. Returns Y.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Power regression: Slope

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Power regression: Y = b X ^ a. Returns a.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Quadratic regression: Correlation coefficient

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Quadratic regression: Y = ( a + b X ) ^ 2, Returns the correlation coefficient.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to correlate with metric_Y |
| metric_Y| A metric that you would like to correlate with metric_X |
| include_zeros | Whether or not to include zero values in the calculations |

## Quadratic regression: Intercept

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Quadratic regression: Y = ( a + b X ) ^ 2, Returns a.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |


## Quadratic regression: Predicted Y

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Row]{type="Neutral"} Quadratic regression: Y = ( a + b X ) ^ 2, Returns Y.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |

## Quadratic regression: Slope

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Quadratic regression: Y = ( a + b X ) ^ 2, Returns b.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |



## Reciprocal regression: Correlation coefficient

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Reciprocal regression: Y = a + b X ^ -1. Returns the correlation coefficient.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to correlate with metric_Y |
| metric_Y| A metric that you would like to correlate with metric_X |
| include_zeros | Whether or not to include zero values in the calculations |


## Reciprocal regression: Intercept

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Reciprocal regression: Y = a + b X ^ -1. Returns a.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |


## Reciprocal regression: Predicted Y

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE Row]{type="Neutral"} Reciprocal regression: Y = a + b X ^ -1. Returns Y.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |


## Reciprocal regression: Slope

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE Table]{type="Neutral"} Reciprocal regression: Y = a + b X ^ -1. Returns b.


| Argument | Description |
|---|---|
| metric_X| A metric that you would like to designate as the dependent data |
| metric_Y| A metric that you would like to designate as the independent data |
| include_zeros | Whether or not to include zero values in the calculations |




## Sine

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE Row]{type="Neutral"} Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.


| Argument | Description |
|---|---|
| metric| The angle in radians for which you want the sine |




## T-Score

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**


The deviation from the mean divided by the standard deviation. Alias for [Z-Score](#z-score).


| Argument | Description |
|---|---|
| metric| The metric for which you would like the T Score |
| include_zeros | Whether or not to include zero values in the calculations |


## T-Test

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**


Performs an m-tailed t-test with t-score of x and n degrees of freedom.


| Argument | Description |
|---|---|
| metric| The metric on which you would like to perform a T Test |
| degrees| The degrees of freedom |
| tails| The length of the tail to be used to perform the T Test |

### Details

The signature is T-TEST( x, n, m). Underneath, it simply calls ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL Cdf-T(-abs(x),n)]](#cdf-t)** . This is similar to the z-test function which runs  ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL Cdf-Z(-abs(x))]](#cdf-z)**.

Here, ***m*** is the number of tails, and ***n*** is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. Combine it with [IF](#if) to ignore very high or low bounce rates, and count sessions on everything else:

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```




## Tangent

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**


Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.


| Argument | Description |
|---|---|
| metric| The angle in radians for which you want the tangent |



## Z-Score

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**


[!BADGE Row]{type="Neutral"} The deviation from the mean divided by the standard deviation.


| Argument | Description |
|---|---|
| metric| The metric for which you would like the Z Score |
| include_zeros | Whether or not to include zero values in the calculations |

A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.



## Z-Test

![Effect](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**


Performs an n-tailed z-test with z-score of x.


| Argument | Description |
|---|---|
| metric| The metric on which you would like to perform a Z Test |
| tails| The length of the tail to be used to perform the Z Test |

>[!NOTE]
>
>Assumes that the values are normally distributed.









<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->