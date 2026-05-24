---
title: Domains used by Customer Journey Analytics
description: If your organization's firewall blocks IP addresses that originate from Adobe, use this list to update your firewall settings.
role: Admin
exl-id: 0c3e7b2e-cb48-4e14-ae18-65258ebce1b4
autotag-review: '2026-05-19T09:27:11.172Z'
TQID: 'https://experienceleague.adobe.com/y3FgZsfqtozN8IaJlBvmfybUIH3s7fiiw2Rc4iNLyGI'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
    internal-label: Data governance
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
    internal-label: Privacy
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
---
# Domains used by Customer Journey Analytics

Some firewall configurations block domains that Customer Journey Analytics rely on for its product interface. You can use this list of domains to alter your organization's network settings to allow product access from within your organization. Adobe recommends allowing these domains through your organization's firewall for an optimal experience.

| Technology | Domain |
| --- | --- |
| Customer Journey Analytics domains | `adobe.com`, `adobe.net`, `adobe.io` |
| Amazon AWS | `aaui-879784980514.s3.us-east-2.amazonaws.com` |
| Amazon CloudFront | `d30ln29764hddd.cloudfront.net` |
| Gainsight | `esp.aptrinsic.com`, `esp-m.aptrinsic.com` |
| LaunchDarkly | `app.launchdarkly.com` |
| Microsoft&reg; Azure Blob Storage | `awaascicdprodva7.blob.core.windows.net` |
| Microsoft&reg; Azure CDN | `aauicdnva7.azureedge.net` |

{style="table-layout:auto"}

## CX Enterprise domains

In addition to the above domains, CX Enterprise relies on several domains for data collection and exporting reports. See [Domains used by CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains) for this list of domains.

>[!MORELIKETHIS]
>
>[IP addresses used by Customer Journey Analytics](ip-addresses.md)
>
>[Domains used by CX Enterprise](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/domains)
