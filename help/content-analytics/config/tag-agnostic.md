---
title: Content Analytics Tags Agnositc Configuration
description: Learn how to configure Content Analytics without using Experience Platform Data Collection Tags.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
---

# Content Analytics Tags agnostic configuration

The Adobe Content Analytics JavaScript library enables tracking of content-related events on websites by sending content data to Adobe Experience Platform via the Experience Platform Edge Network. Use this library when you want to implement Content Analytics without Adobe Experience Platform tags (Launch).

>[!PREREQUISITES]
>
>Adobe Experience Platform Web SDK (Alloy) must be initialized on the page before calling `initializeContentLibrary`.

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


## Datastream Configuration

The `datastreamId` option is required and must reference a datastream that has the Experience Platform service configured with an enabled Content Analytics experience event dataset. Ensure the sandbox associated with the datastream is not already associated with another Content Analytics setup.

You can supply separate datastream IDs per environment:

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## Experience Capture & Definition

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

## Event Filtering

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

>[!NOTE]
>
>After a Content Analytics configuration has been set up in the [guided configuration](/help/content-analytics/config/guided.md) interface, the JavaScript settings specific to your configuration are available in that configuration view.

