---
title: Content Analytics JavaScript Library
description: Learn how to configure Content Analytics without using Experience Platform Data Collection Tags and use the Content Analytics JavaScript library instead.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
autotag-review: '2026-05-19T06:56:34.440Z'
TQID: 'https://experienceleague.adobe.com/GUYf0ZoTlAkoIIPWzfZTm0-eMvBjN8ieYSu6goHu3GA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---

# Content Analytics JavaScript library

The Adobe Content Analytics JavaScript library enables tracking of content-related events on websites by sending content data to Adobe Experience Platform via the Experience Platform Edge Network. Use this library when you want to implement Content Analytics without Adobe Experience Platform Tags.

>[!NOTE]
>
>This article applies to Content Analytics for the web channel.


>[!PREREQUISITES]
>
>* Adobe Experience Platform Web SDK (Alloy) must be initialized on the page before calling `initializeContentLibrary`.
>* Complete the Content Analytics guided configuration wizard to guide you through all steps required to set up the prerequisites for a configuration of Content Analytics.
>* After the guided configuration is finished, the JavaScript settings are available to use.


## Installation

You can install the library in two ways:

### npm package

Use `npm` to install the library.

1. On the command line, use:

    ```bash
    npm install @adobe/content-analytics
    ```

1. Import the library: 

    ```JavaScript
    import initializeContentLibrary from "@adobe/content-analytics";
    ```

### Script tag (CDN)

Load the library directly from the CDN.

1. Initialze the [Web SDK JavaScript library](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library) and load the Content Analytics bundle:

    ```html
    <!-- 1. Load and configure Alloy first -->
    <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
    <script>
    alloy("configure", {
        datastreamId: "YOUR_DATASTREAM_ID",
        orgId: "YOUR_ORG_ID@AdobeOrg",
    });
    </script>

    <!-- 2. Load Content Analytics -->
    <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
    <script>
    window.contentAnalytics({
        datastreamId: "YOUR_DATASTREAM_ID",
    });
    </script>
    ```

    where 
    * `alloy/2.x.x` refers to the version you want to use of the [Web SDK JavaScript library](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library).
    * `content-analytics/1.x.x` refers to the version you want to use of the Content Analytics SDK library.

2. The standalone build exposes `window.contentAnalytics` as the initialization function.


## Datastream configuration

The `datastreamId` option is required and must reference a datastream that has the Experience Platform service configured with an enabled Content Analytics experience event dataset. Ensure the sandbox associated with the datastream is not already associated with another Content Analytics setup.

You can supply separate datastream IDs per environment:

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## Experience capture and definition

Enable experience tracking and control how experiences are identified on your website. Experiences are defined by combining a **domain regular expression** with optional **query parameters** that distinguish one experience from another within matching pages.

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `includeExperiences` | boolean | `false` | Enable page/experience view tracking |
| `experienceConfigurations` | array | - | Define experiences by domain regex and query parameters |

Each entry in `experienceConfigurations` accepts:

| Property | Type | Description |
|----------|------|-------------|
| `regEx` | string | Domain regular expression matched against the page URL (e.g. `^(?!.*\b(store\|help\|admin)\b)`) |
| `queryParameters` | array | Query parameter names whose values distinguish experiences on matching pages (e.g. `["outdoors", "patio", "kitchen"]`) |

### Example

See below for an example of how to enable experience tracking with domain regex and query parameters.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## Event filtering

Control which page URLs and asset URLs are included in data collection using regular expressions. Use the pattern examples below as a starting point and validate the patterns with a regex tester before deployment.

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `pageUrlQualifier` | string (regex) | - | Only track pages whose URL matches this pattern |
| `assetUrlQualifier` | string (regex) | - | Only track assets whose URL matches this pattern |
| `excludeURLsFromTracking` | array | `[]` | List of URL strings to exclude from tracking |

### Example

See below for an example of how to exclude documentation pages from Content Analytics and to consider only product images for Content Analytics.

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```
