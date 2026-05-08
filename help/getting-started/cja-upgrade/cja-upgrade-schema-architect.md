---
title: Architect your schema for use with Customer Journey Analytics
description: Learn how to design an XDM schema that unlocks Customer Journey Analytics flexibility, while supporting a practical migration path from Adobe Analytics.
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
---
# Architect your schema for use with Customer Journey Analytics {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="Architect a schema"
>abstract="Discuss within your organization the requirements of data collection, and determine how you want to build a schema for use in Adobe Experience Platform. This step appears because you want to use the recommended process of using a schema tailored to your organization. Performing this step correctly is pivotal, as a schema that all teams within your organization align on makes data ingestion significantly easier.<br><br>The estimated time to bring together all relevant parties in your organization to align upon a unified schema is 1-2 months. This time frame heavily depends on the number of teams required to coordinate, and the number of dimensions + metrics to align on."

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe recommends creating a custom [Experience Data Model](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/home) (XDM) schema for Customer Journey Analytics when implementing [Adobe Experience Platform Data Collection](https://experienceleague.adobe.com/en/docs/experience-platform/collection/home). Creating this schema is typically done before any implementation changes or code is touched. A custom schema lets you design a concise, organization-specific data contract without inheriting constraints from Adobe Analytics. See [Choose your schema for Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md) to learn more about the types of schemas available to your organization.

Schemas are intended to be polished versions of how you want your data to be structured long-term. Changes to schemas are expensive because they impact data collection, validation, and downstream services. You can add to schemas over time as business requirements allow; however, schema fields cannot be removed once data starts flowing into them.

## Compare schemas to data views

The data pipeline for Customer Journey Analytics contains separate areas for data collection and data interpretation. When upgrading from Adobe Analytics, a common misstep is trying to recreate props and eVars with their behaviors in XDM. Instead, use the Web SDK to collect the data and use [Data views](/help/data-views/data-views.md) to determine how that data is interpreted in reports.

| Layer | Primary purpose | Flexibility | What belongs | What does not belong |
|---|---|---|---|---|
| **XDM schema** | Define the durable structure and meaning of collected data | Rigid; considered immutable data points | Event and entity shape, field meaning, relationships, allowed values, reuse across channels | Numbered "slots" (eVar1/prop1), attribution/persistence logic, reporting-specific workarounds |
| **Data views** | Define how collected data behaves in analysis | Flexible; can be freely modified and can retroactively re-interpret data | Component settings, attribution and persistence behavior, derived fields, filtered metrics, calculated metrics | Fundamental meaning of fields; that meaning should be stable in the schema |

## Compare schemas to Adobe Analytics data collection

The Experience Data Model that Customer Journey Analytics uses enables significantly more flexibility than most other Analytics solutions (including Adobe Analytics). Establishing a solid schema is your organization's opportunity to avoid carrying forward constraints that exist in other Analytics products.

| Common Adobe Analytics habit | Better approach in XDM + Customer Journey Analytics |
|---|---|
| Designing around numbered slots (`eVar1`–`eVar250`, `prop1`–`prop75`) | Create fields with stable meaning (for example, `search.term`, `content.category`, `user.membershipTier`) and reuse them consistently |
| Encoding persistence/allocation/expiration into the data model | Capture durable facts in the schema; apply attribution and persistence behavior at the data view level |
| Duplicating the same value in multiple variables to achieve reporting behaviors | Store the value once and create multiple components (dimensions/metrics) from it in data views |
| Creating a unique "metric field" for every count that you might want | Capture the right facts once (often as enums/booleans/strings), then define metrics as filtered counts in data views |
| Designing variables to "pre-solve" reporting | Design your schema to capture facts and use data views to solve reporting semantics |

## Establish a schema using common attributes

A unified schema across channels becomes possible when you standardize a set of reusable attributes that appear across many events. Some examples include:

* **Experience context:** site/app name, environment, locale, channel, brand
* **Journey context:** campaign identifiers, referring context, experiment identifiers
* **User state:** logged-in status, membership tier, account type
* **Interaction details:** interaction name/type, UI region, element label, error category

The key is to standardize what the field represents regardless of channel. Avoid modeling the same concept differently across channels unless they truly represent different concepts. For example, it might be wise to avoid having separate schema fields for web campaign IDs and mobile campaign IDs. Separate schema fields make it more difficult to establish cross-channel return on ad spend data. If a differentiation is required in reporting, you can segment by channel or concatenate multiple fields to provide that distinction. The same schema field can be used in any number of dimensions or metrics.

A practical way to support multiple channels while keeping a single schema strategy is to use a **core + extensions** pattern:

* **Core:** fields that apply broadly across channels and teams
* **Extensions:** channel- or domain-specific field groups that apply only where needed (web interaction, commerce, mobile lifecycle, server-side specifics)

This pattern supports a single organizational schema strategy without forcing teams to populate unnecessary fields.

## Prefer standard field groups where they fit

Adobe recommends using standardized field groups where they match your needs, and extending with custom fields for organization-specific concepts.

Standard field groups typically help you:

* Reduce ambiguity by using known field semantics
* Align across teams more easily
* Support interoperability across Adobe Experience Platform applications

Custom fields are appropriate when:

* Your organization has concepts that do not map cleanly to standard fields
* You need additional attributes to meet reporting, governance, or activation requirements
* You want to represent a business-specific taxonomy (for example, internal content categories)

## Determine how metrics are counted

In Adobe Analytics, many teams treat the `events` variable as the only means to track metrics. In Customer Journey Analytics, you can track metrics in multiple ways depending on what you need to count and how you want to interpret it.

When architecting a schema, stick to facts. For example, `error.type = "validation"`, `user.isLoggedIn = true`, `checkout.step = "shipping"`. Define metrics in the data view as counts and filtered counts over those facts. For example:

* `checkout.step` (enum/string) can power:
  * "Checkout: Shipping step reached" (count where `checkout.step == "shipping"`)
  * "Checkout: Payment step reached"
* `error.type` (enum/string) can power:
  * "Validation errors"
  * "Authorization errors"
* `user.isLoggedIn` (boolean) can power:
  * "Authenticated sessions"
  * "Authenticated conversions"

>[!TIP]
>
>When deciding whether something should be a dedicated field in the schema vs. a derived field later, prefer capturing the durable fact in the schema if it is broadly useful and stable. You can use derived fields to correct or reshape data after collection.

## Maintain parity with Adobe Analytics during transition without schema baggage

Some organizations need to continue Adobe Analytics reporting while upgrading to Customer Journey Analytics. You can maintain parity without introducing Analytics-specific artifacts into your long-term schema design using the following approach:

1. **Use XDM field paths that Adobe Analytics recognizes and automatically maps:** When you send recognized XDM fields through the Edge Network to Adobe Analytics, they are [mapped automatically](https://experienceleague.adobe.com/en/docs/analytics/implementation/aep-edge/xdm-var-mapping) without extra configuration.
1. **Use custom XDM fields for organization-specific concepts:** Any XDM fields that are not automatically mapped to an Analytics variable are forwarded as [Context data variables](https://experienceleague.adobe.com/en/docs/analytics/implementation/vars/page-vars/contextdata) in Adobe Analytics.
1. **Use Adobe Analytics processing rules to map those context data variables to props/eVars:** [Processing rules](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/processing-rules/pr-overview) ultimately enable you to map any custom XDM field into any eVar or prop. This concept supports parity reporting in Adobe Analytics while keeping your schema clean and centered on Customer Journey Analytics.

## Identify stakeholders and define ownership

Schema design succeeds when field meaning is agreed upon and maintained. While organizational structures vary, the following roles commonly participate:

* **Analytics admin/analyst**: Defines reporting questions, validates that fields represent meaningful concepts, and reviews analysis semantics in data views.
* **Developer/implementation owner**: Ensures that fields can be collected reliably using the Web SDK and aligns with the data layer/app instrumentation.
* **Data architect/engineer**: Ensures schema consistency, reuse across domains, and compatibility with downstream services.
* **Privacy/governance stakeholder**: Reviews data minimization, consent expectations, and data usage constraints.

Define a clear owner for schema changes. A stable schema with disciplined change control prevents downstream breakage and reduces rework. Consider using a tracking governance workflow or tooling to democratize requests and manage change control over time.

## Privacy and governance considerations

Schema design should reflect privacy and governance expectations, according to your organization's privacy policies. Consider the following points as you architect your schema:

* Collect only what you need to support defined use cases.
* Ensure that consent and data usage requirements are reflected in your collection strategy. See [Use the Web SDK to process customer consent data](https://experienceleague.adobe.com/en/docs/experience-platform/landing/governance-privacy-security/consent/sdk) for more information.
* Consider how sensitive fields are labeled and controlled within Adobe Experience Platform governance tools. See [Adobe Customer Journey Analytics and Data Governance](/help/privacy/privacy-overview.md) for more information.

## Next steps

Once you have established and agreed upon a schema architecture, you can begin creating it in Adobe Experience Platform. See [Create a custom schema to use with Customer Journey Analytics](cja-upgrade-schema-create.md) for more information.
