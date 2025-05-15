---
title: Validate stitching
description: How to validate stitching
solution: Customer Journey Analytics
feature: Stitching, Cross-Channel Analysis
role: Admin
hide: yes
hidefromtoc: yes
---
# Validate stitching

The goal of [identity stitching](/help/stitching/overview.md) (or simply, stitching) is to elevate the suitability of an event dataset for cross-channel analysis. This elevation is achieved when all rows of data i the dataset contain the desired highest order of identity that is available. This elevation allows you then to:

* Create person-centric reports, while not missing out on anonymous people.
* Connect multiple devices to a single person.
* Connect a person across channels.

This article outlines analysis methods to measure the elevation on the newly created stitched dataset(s) and to provide confidence that stitching is delivering these benefits. 

The analysis methods involve Data View settings that are typically accessible to admins and those who work in an Analysis Workspace project to calculated metrics and visualizations. While these analysis methods can be used for both Field-based stitching (FBS) and Graph-based stitching (GBS), some elements may not be present in the dataset especially in the GBS scenario. These missing elemement can make it difficult to calculate lift directly in Analysis Workspace.

This article does not capture the value of a Customer Journey Analytics configuration that has all datasets in AEP aligned to the same identity namespace, has all datasets joined together, and enables users of Customer Journey Analytics to perform analysis across an entire customer journey.

## Data view prerequisites

For the stitching validation measurement plan you need to ensure you have all required dimensions and metrics from your stitched dataset defined in a Data view. You need to verify that both stitchedID and stitchedNamespace are added as dimensions. While the stitched dataset is an exact copy of the original dataset, the stitching process adds two new columns (dimensions):

* `stitchedNamespace`, which contains one of two values, the namespace of the identity that the row was elevated to, for example `Email`, `Phone`. Or the namespace the stitching process fallbacks to, such as `ECID`. 
* `stitchedID`, which contains the raw value of the identity, i.e. hashed email, hashed phone, ECID. This value is used in conjunction with `stitchedNamespace`.


<!--The screenshot below displays these field paths and friendly names as dimensions in the Data View administration "Components" section.-->

Furthermore, you need to add two stitching metrics that are based on the presence of values in a dimension. To add these metrics, use the Data view Included components definition:

1. Drag the Custom Conversion variable (eVar) or corresponding XDM field containing the Person ID from the stitched dataset onto the Metrics list within Component and provide a friendly Component Name. Add this Person ID even if you're using Graph-based stitching as the Person ID helps to establish a baseline. In case the Person ID is not contained within the dataset, your baseline is 0%. In the example below, email address serves as the identity. 
1. In a similar way, add the previously created Stitched Namespace dimension as a metric, provide a name. Additionaly specify an include filter to only consider values of the namespace you are trying to elevate rows of data to.  In the example, since events are being elevated to the Email namespace, specify Equals email.


Stitched dimensions
With both of these dimensions added to the Data View, let's add them to a freeform table to check the data that each has.
 
For the Stitched Namespace dimension, you will typically see two values for each dataset, one represents when the stitching process had to use the fallback method while the other line item shows events associated with the desired identity namespace, in this case ECID and email.


Device or Person-Centric Reporting
When creating a Connection, we have a choice to make, what field/identity will be used for my person Id. For instance, on a web dataset if you choose a device id as the person id, then you are creating device centric reports and lose the ability to join this data with other offline channels. On the other hand, if you select just the field/identity where you have a cross-channel identity like an email you will lose out on any unauthenticated events. To understand this impact, it is important to see how much of your traffic is unauthenticated and how much of it is authenticated.

First, we need to create a calculated metric "Unauthenticated events over total" with the formula of the following:

Now with this new metric and the metric we created from a dimension in the " Stitching Validation Data View Prerequisites" section we can create some summary visualizations showing the number of events in the dataset that are unauthenticated and those that are authenticated

Stitching Identification Rates
Now let's look at how we measure the identification performance before and after Stitching by creating four calculated metrics.
1.    First, we need to create a calculated metric that lets us look at the number of events that have an identity present over the total. Here is the definition (email set events divided by total events in the reporting range):
1.    
1.    2.    The next calculated metric we need to create lets us look at the number of events where the Stitched Namespace is set to the desired identity. When we first set up our Data View, we created a metric from the dimension of Stitched Namespace. With this metric we added a filter only counting times when an event is set with "email", since in this example that is what we are trying to elevate rows of data to. Using this earlier created metric and dividing that over all the events we get a sense of what percent of the data has the desired identity on them. Here is the definition:
1.    3.    The next calculated metric we need to create lets us look at the shows the raw percentage change between the current identification rate and the stitched one. Here is the definition:
1.    4.    Lastly, we need to create a calculated metric that lets us look at the lift between the current identification rate and the stitched one. Here is the definition:



Conclusion
Putting it all together in an Analysis Workspace Freeform table you can start to see the impact and value that Stitching provides inclusive of:
*    Current Authentication Rate – The baseline of the number of events that already had the correct person id over the total number of events.
*    Stitched Authentication Rate - The new number of events that have the correct person id over the total number of events.
*    Percent Increase – The raw percentage increase from the stitched authentication rate minus the baseline Current Authentication Rate.
*    Lift – The percent change over the baseline Current Authentication Rate.

Key takeaways from constructing this analysis:

*    Provides a comprehensive custom view of authentication effectiveness by comparing current vs. stitched rates
*    Enables clear measurement of improvement through percentage increases and lift metrics
*    Helps identify the true impact of implementing stitching on user authentication
*    Creates a standardized way to communicate authentication performance across teams
*    Allows for data-driven decisions about authentication strategy and optimization

These metrics together give stakeholders a complete picture of how CJA Stitching affects authentication success rates and overall CJA Person identification performance.
