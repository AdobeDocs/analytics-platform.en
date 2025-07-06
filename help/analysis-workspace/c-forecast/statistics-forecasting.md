---
description: Learn about how forecasting in Analysis Workspace uses a series of advanced statistical techniques to determine forecast values.
title: Statistical Techniques
feature: Visualizations
role: User
exl-id: f042a6dd-6af5-4bdd-afc9-07546d8ded6e
---
# Statistical techniques

The forecasting service currently supports Prophet and has been shown to work efficiently and reliably for most data. Prophet is a widely used open-source forecasting package developed by Meta. It decomposes data into trends, seasonalities, and events components. The Prophet model is efficient and scales well to many forecasting applications. Besides, the model works robustly against outliers and missing data.  
 
In the future, there are plans to select models based on heuristics, for example choose Online Approximate Gaussian Process for streaming data, or NeuralProphet when users specify best forecasting accuracy and can tolerate longer wait time. 
 
The service automatically downscales data when there are too many data points, to ensure response time. The target response time is set to be ~3 seconds. Currently, when the number of data points exceed 5500, the time series data is down-sampled adaptively, depending on the length of data. The output is converted back to the original data frequency, so the adaptive sampling process will not affect user experiences.
 
The holiday effects are considered when multiple years of data are available. Currently, the list of holidays in consideration are: 

* Martin Luther King Day 
* Presidents Day 
* Memorial Day 
* July 4 
* Thanksgiving 
* Black Friday 
* Cyber Monday 
* Christmas 

The service can also do a simple anomaly (outliers) removal, for example by removing data points that are outside of six sigma range. This is not enabled by default as it is assumed all data points are valid. Anomalies can have a negative influence on model quality even though the Prophet model is resilient to outliers in general. 
 
The service accepts user-specified seasonality settings, for example daily and weekly seasonality. Otherwise, the model automatically selects the seasonality. For different data granularity, the service uses different lengths of historical data to build forecasting models. For example, for daily data, it pulls more than a year of data (if available). For hourly data, it pulls eight weeks of data (if available). Pulling data can be time-consuming and sometimes causes longer wait time. 

The historical data required for different time granularity: 

| Granularity | Historical data required |
|---|--:|
| Minute | 3 days |
| Hour | 2 weeks |
| Day | 8 weeks |
| Week | 2 years |
| Month | 2 years |
| Quarter | 8 quarters |
| Year | 8 years |
 
 
The forecasting result for each specified time comes with a prediction interval (defined by the lower and upper bound), which is expected to contain the future observed value 95% of the time, often, referred to as confidence interval. There is no limit to how far the service can forecast into the future. However, uncertainty in forecasting increases with dates further into the future, reflected by a wider prediction interval over time. 
 
The service doesn't make any assumptions about user data. For example, the service doesn't assume the data are non-negative. This means that the predictions and/or their bounds can be negative, if the data exhibits a strong downward trend, even though all observed data points are non-negative. 
 

## References

1. Taylor, Sean J., and Benjamin Letham: *Forecasting at scale.* The American Statistician 72.1 (2018): 37-45. 
1. Triebe, Oskar, et al.: *Neuralprophet: Explainable forecasting at scale.* arXiv preprint arXiv:2111.15397(2021). 
1. Zhang and Arbour: *Time-series anomaly detection.* US patent application #18/057883.
