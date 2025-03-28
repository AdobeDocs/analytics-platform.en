---
title: Content Analytics components
description: Details on the specific Content Analytics components, like dimensions, (calculated) metrics and derived fields
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
---
# Content Analytics components

{{release-limited-testing}}

Content Analytics adds the following categories of components (dimensions, (calculated) metrics, derived fields) to the already available components in Customer Journey Analytics:

* [Experience metadata](#experience-metadata)
* [Experience attributes](#experience-attributes)
* [Experience events](#experience-events)
* [Asset metadata](#asset-metadata)
* [Asset attributes](#asset-attributes)
* [Assets events](#asset-events)
* [Calculated metrics](#calculated-metrics)

In the tables below, ![AI generated](/help/assets/icons/AI.svg) indicates an AI/ML generated attribute / value pair. 

## Experience metadata

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Channel | Channel for the experience. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Experience Source | Source URL of the experience. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Experience ID | Unique id for the experience. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Experience Name | Name for the experience. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Experience Description | Description for the experience. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Experience Thumbnail URL | URL for the thumbnail of the experience. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Experience Horizontal Percentage Depth | Quantifiable value of the horizontal percentage depth of the experience. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Experience Vertical Percentage Depth | Quantifiable value of the vertical percentage depth of the experience. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |

{style="table-layout:fixed"}



## Experience attributes

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Keywords | ![AI generated](/help/assets/icons/AI.svg) Keywords for the experience. | Dimension<br>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Experience Persuasion Strategies | ![AI generated](/help/assets/icons/AI.svg)  Persuasion strategies that are present in the given experience. The possible values are: Social Identity, Social Proof, Authority, Concreteness, Foot in the Door, Overcoming Reactance, Reciprocity, Anchoring and Comparison, Social Impact, Scarcity, and Anthropomorphism. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Experience Narratives | ![AI generated](/help/assets/icons/AI.svg) Narratives which the experience is building based on relevance from a marketer's view point. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Experience Tones | ![AI generated](/help/assets/icons/AI.svg)  Tones which the experience is building based on relevance from a marketer's view point | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Experience Marketing Emotions | ![AI generated](/help/assets/icons/AI.svg) The emotion invoked in the reader when reading the text used as part of the experience: Urgency, Exclusivity, Encouragement, Challenge, Curiosity, Achievement, Trust, Simplicity, and Fascination. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Experience Emojis Count | ![AI generated](/help/assets/icons/AI.svg) Number of emojis for the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Experience Hashtags Count | ![AI generated](/help/assets/icons/AI.svg) Number of hashtags for the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Experience Sentences Count | ![AI generated](/help/assets/icons/AI.svg) Number of sentences for the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Experience Stop Words Ratio | ![AI generated](/help/assets/icons/AI.svg) Number of stop words for the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Experience Text Quotes Count | ![AI generated](/help/assets/icons/AI.svg) Number of text quotes for the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Experience Words Count | ![AI generated](/help/assets/icons/AI.svg) Number of words for the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Experience Words Count Per Sentence | ![AI generated](/help/assets/icons/AI.svg) Number of words per sentence for the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |

{style="table-layout:fixed"}


## Experience events 

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Views | Quantifiable measure of the number of views of the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Experience Clicks | Quantifiable measure of the number of clicks of the experience. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |

{style="table-layout:fixed"}


## Asset metadata

| Title | Description | Type | Settings |
|---|---|---|---|
| Asset Source | Public accessible source URL for the asset. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset ID | Unique identifier of the asset. The asset binary determines the uniqueness. If the asset binary changes, the id does change. The unique id can be the URL but can also be a hash created. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset HTML Path | Concatenated HTML path for the asset. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset Link URL | Nearest page anchor for the asset. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset Display Width | Content asset display width. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset Display Height | Content asset display height. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset Absolute Left | Content asset absolute left. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset Absolute Top | Content asset absolute top. | Dimension | Show \| No value<br/>Most Recent \| Session |

{style="table-layout:fixed"}


## Asset attributes

| Title | Description | Type | Settings |
|---|---|---|---|
| Asset Orientation | ![AI generated](/help/assets/icons/AI.svg) Orientation of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Overall Tone | ![AI generated](/help/assets/icons/AI.svg) Overall tone of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Foreground Colors | ![AI generated](/help/assets/icons/AI.svg) Foreground colors of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Background Color | ![AI generated](/help/assets/icons/AI.svg) Background colors of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Tags | ![AI generated](/help/assets/icons/AI.svg) Tags for the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Scenes | ![AI generated](/help/assets/icons/AI.svg) Scenes for the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Objects | ![AI generated](/help/assets/icons/AI.svg) Objects of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Photography Styles | ![AI generated](/help/assets/icons/AI.svg) Photography styles of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Image Type | ![AI generated](/help/assets/icons/AI.svg) Image type of the asset. Possible values are: photograph, sketch, painting, digital_cartoon, infographics, graphic_design, collage, and software_screenshot. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Camera Positions | ![AI generated](/help/assets/icons/AI.svg) Camera positions of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Camera Proximities | ![AI generated](/help/assets/icons/AI.svg) Camera proximities of the asset. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset People Categories | ![AI generated](/help/assets/icons/AI.svg) People categories for the asset. Possible values are: person, man, woman, social group, crowd, people, boy, girl, and kid. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Visual Content Density | ![AI generated](/help/assets/icons/AI.svg) Visual content density of the asset. Possible values are: low, medium, or high. Low content density implies a small amount of information present per unit area of the image. | Dimension | Show \| No value<br/>Most Recent \| Session |
| Asset Visual Attention Spread | ![AI generated](/help/assets/icons/AI.svg) Visual attention spread of the asset. Possible values are: low, medium, or high. Attention spread refers to the degree to which the attention of a viewer is divided between different parts of a picture. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Lighting Condition | ![AI generated](/help/assets/icons/AI.svg) Lighting condition of the asset. Possible values are: golden hour, blue hour, midday, overcast, night, high-key, low-key, daylighting, incandescent, fluorescent, colorful, and studio. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |
| Asset Camera Setting | ![AI generated](/help/assets/icons/AI.svg) Camera setting of the asset. Possible values are: fast shutter speed, long exposure. bokeh blur, motion blur, tilt-shift blur, flash, wide-angle, black and white, surreal, double-exposure, macro, and normal mode. | Dimension<br/>Derived Field | Show \| No value<br/>Most Recent \| Session |

{style="table-layout:fixed"}


## Asset events

| Title | Description | Type | Settings |
|---|---|---|---|
| Asset Views | Quantifiable measure of the number of views of the asset. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |
| Asset Clicks | Quantifiable measure of the number of clicks of the asset. | Metric | Count values<br/>Decimal \| Decimal Places: 0 |

{style="table-layout:fixed"}


<!--
## Other derived fields

| Title | Description | Type | Settings |
|---|---|---|---|
| Experience Path | Full path to the experience. | Derived Field | |
| Experience Path Root | Root path to the experience. | Derived Field | |
| Asset Location | Location of the asset. | Derived Field | |
| Asset Percenption ID + Asset ID | Combiination of asset perception identifier and asset identifier | Derived Field | |

{style="table-layout:fixed"}
-->

## Calculated metrics

| Title | Description | Type | Settings |
|---|---|---|---|
| Asset Click-Trough Rate | Asset Clicks / Asset Views | Calculated metric | |
| experience Click-Through Rate | Experience Clicks / Experience Views | Calculated metric | |

{style="table-layout:fixed"}

