---
title: Report on Google Analytics data in Customer Journey Analytics
description: Shows useful reports on Google Analytics data in Customer Journey Analytics
---

# Report on Google Analytics data in Customer Journey Analytics

Now that you have [ingested the Google Analytics data into Experience Platform and Customer Journey Analytics (CJA)](/help/use-cases/ga-to-cja.md), we will show you some useful scenarios for reporting on that data.

## Visualize web data and app data as combined datasets

This Venn diagram shows the overlap of users on your website (from your Google Analytics data) and on your mobile app (from your Firebase data) and from your call center. You can also see the top performing products - not just on the web, but also in the mobile app. You can even get the total the revenue from both, using a calculated metric. Notice how the top products tell a different story when you look at the combined revenue. Without the combined datasets, you would never have known that the "Twill cap" was such a strong performer.

![](assets/combined-datasets.png)

## Identify call reasons and reduce call volume 

To verify that you have been getting a lot of calls, you can trend our call center time spent for over the period of the last 2 months. It’s easy to see the increasing trend. This is worrisome, since every minute your call center reps are on the phone costs you money. This can definitely impact your bottom line.

Let’s look at the top reasons causing the increased calls to call center. Notice that "Credit Card Denied", “Remove Credit card", and “Damaged product” are the top reasons. This can already hint at ways to improve the experience online. You can also trend those call reasons and see which have contributed the most to the overall spike. It’s interesting to see that customers with "Damaged Product" have spent more than 3 minutes per call.

![](assets/call-volume.png)

Let’s look further and see which products are causing most of the calls to your call center and how many customers made those calls. The bubble chart indicates that 20,000 people called, spent more than 4hrs 30 mins and returned 33 units of the "Men's short Sleeve Tee" product. 

We can break that insight down and see why those people returned the product by dragging in the dimension "Call Reason". As you can see, the reason this product is getting so many calls is due to "Damaged Product". The next step would be to contact the quality control department and see why customers have been receiving damaged T-shirts.

![](assets/call-reason.png)

Now let’s look at which web site pages drove the incoming calls at the call center. This lets you know where under-performing experiences are on the web site are and help your Product Managers solve those challenges.

We do this by

* Using a calculated metric to filter the data down to only sessions that ended with a call center call.
* Using the “participation” model in CJA’s [Attribution IQ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/attribution/models.html?lang=en#cja-workspace).

You can easily see which pages most frequently participate in a session that ends in a call. You can see that the "Shopping Cart" and "Checkout Information" pages drove most of the calls. Since you have also included the firebase mobile app data, you can even see page errors and app crashes generating the calls. This is a really important data point if you want to deliver great web and mobile app experiences.

![](assets/contributing-pages.png)

Finally, using the cohort table in Analysis Workspace, it’s easy to see how long it typically takes for users to call our call center after having visited the website. Here you can see the average time is between 3 and 4 weeks. 

![](assets/cohort.png)

## Use advanced marketing attribution

CJA allows you to use sophisticated attribution models on your cross-channel data. In the following example, you can see a comparison of applying Last touch, first touch, u-shaped, and algorithmic attribution of revenue to the Google Analytics Channel Grouping dimension. 

![](assets/mktg-attribution.png)

Using a calculated metric, you can apply that attribution to your web revenue, mobile app revenue, and even remove product returns. As a result, you can see true net revenue for each marketing channel. 

![](assets/calc-metric.png)

Attribution IQ also lets you easily filter your data. You can see attribution against only specific sets of users, such as those who are using more than one device.

![](assets/filter.png)

Last, you can also attribute your Web and App revenue to your Google Ad Content. You will notice that you gained more revenue from the mobile app being driven by our online Google Ads than from the web. By sorting ads by web and app revenue, you get a very different picture of what your top performing Google ads were. 

![](assets/google-ad.png)

Without CJA, you could not have known that your online ads were having any impact to products purchased on your mobile app. Now you can see that mobile app revenue from Google Ads represents an additional $14k - $5k, compared to the web alone.

![](assets/google-ad2.png)