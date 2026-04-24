---
title: Content Analytics components
description: Details on the specific Content Analytics components, like dimensions, (calculated) metrics and derived fields
solution: Customer Journey Analytics
feature: Content Analytics
role: User
exl-id: 79bf235a-6f6e-4b04-bcd8-1ff884536648
TQID: https://experienceleague.adobe.com/grwbNht938ivCsnzlFBzP8Ga8h1udmQLcZngxY6s0-4
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
    internal-label: Calculated metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
---
# Content Analytics components

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

| Title | Description | Type |
|---|---|---|
| Experience Channel | Channel for the experience. | Dimension |
| Experience ID | Unique id for the experience. | Dimension |
| Experience Thumbnail URL | URL for the thumbnail of the experience. | Dimension |
| Experience Horizontal Percentage Depth | Quantifiable value of the horizontal percentage depth of the experience. | Dimension<br/>Derived Field |
| Experience Vertical Percentage Depth | Quantifiable value of the vertical percentage depth of the experience. | Dimension<br/>Derived Field |

{style="table-layout:fixed"}



## Experience attributes

| Title | Description | Type |
|---|---|---|
| Experience Attributes | ![AI generated](/help/assets/icons/AI.svg)  Full list of all Experience Attribute names and values | Dimension<br>Derived Field |
| Experience Readability Score | ![AI generated](/help/assets/icons/AI.svg)  Readability score fo the experience | Dimension |
| Experience Keywords | ![AI generated](/help/assets/icons/AI.svg) Keywords for the experience. | Dimension<br>Derived Field |
| Experience Persuasion Strategies | ![AI generated](/help/assets/icons/AI.svg)  Persuasion strategies that are present in the given experience. The possible values are: Social Identity, Social Proof, Authority, Concreteness, Foot in the Door, Overcoming Reactance, Reciprocity, Anchoring and Comparison, Social Impact, Scarcity, and Anthropomorphism. | Dimension<br/>Derived Field |
| Experience Narratives | ![AI generated](/help/assets/icons/AI.svg) Narratives which the experience is building based on relevance from a marketer's view point. | Dimension<br/>Derived Field |
| Experience Tones | ![AI generated](/help/assets/icons/AI.svg)  Tones which the experience is building based on relevance from a marketer's view point | Dimension<br/>Derived Field |
| Experience Marketing Emotions | ![AI generated](/help/assets/icons/AI.svg) The emotion invoked in the reader when reading the text used as part of the experience: Urgency, Exclusivity, Encouragement, Challenge, Curiosity, Achievement, Trust, Simplicity, and Fascination. | Dimension<br/>Derived Field |
| Experience Emojis Count | ![AI generated](/help/assets/icons/AI.svg) Number of emojis for the experience. | Metric |
| Experience Hashtags Count | ![AI generated](/help/assets/icons/AI.svg) Number of hashtags for the experience. | Metric |
| Experience Sentences Count | ![AI generated](/help/assets/icons/AI.svg) Number of sentences for the experience. | Metric |
| Experience Stop Words Ratio | ![AI generated](/help/assets/icons/AI.svg) Number of stop words for the experience. | Metric |
| Experience Text Quotes Count | ![AI generated](/help/assets/icons/AI.svg) Number of text quotes for the experience. | Metric |
| Experience Words Count | ![AI generated](/help/assets/icons/AI.svg) Number of words for the experience. | Metric |
| Experience Words Count Per Sentence | ![AI generated](/help/assets/icons/AI.svg) Number of words per sentence for the experience. | Metric |

{style="table-layout:fixed"}


## Experience events 

| Title | Description | Type |
|---|---|---|
| Experience Views | Quantifiable measure of the number of views of the experience. | Metric |
| Experience Clicks | Quantifiable measure of the number of clicks of the experience. | Metric |

{style="table-layout:fixed"}


## Asset metadata

| Title | Description | Type |
|---|---|---|
| Asset ID | Unique identifier of the asset. The asset binary determines the uniqueness. If the asset binary changes, the id does change. The unique id can be the URL but can also be a hash created. | Dimension |
| Asset HTML Path | Concatenated HTML path for the asset. | Dimension |
| Asset Link URL | Nearest page anchor for the asset. | Dimension |
| Asset Display Width | Content asset display width. | Dimension |
| Asset Display Height | Content asset display height. | Dimension |
| Asset Absolute Left | Content asset absolute left. | Dimension |
| Asset Absolute Top | Content asset absolute top. | Dimension |

{style="table-layout:fixed"}


## Asset attributes

| Title | Description | Type |
|---|---|---|
| Asset Attributes | ![AI generated](/help/assets/icons/AI.svg)  Full list of all Asset attribute names and values | Dimension<br>Derived Field |
| Asset Orientation | ![AI generated](/help/assets/icons/AI.svg) Orientation of the asset. | Dimension<br/>Derived Field |
| Asset Overall Tone | ![AI generated](/help/assets/icons/AI.svg) Overall tone of the asset. | Dimension<br/>Derived Field |
| Asset Foreground Colors | ![AI generated](/help/assets/icons/AI.svg) Foreground colors of the asset. | Dimension<br/>Derived Field |
| Asset Background Colors | ![AI generated](/help/assets/icons/AI.svg) Background colors of the asset. | Dimension<br/>Derived Field |
| Asset Tags | ![AI generated](/help/assets/icons/AI.svg) Tags for the asset. | Dimension<br/>Derived Field |
| Asset Scenes | ![AI generated](/help/assets/icons/AI.svg) Scenes for the asset. | Dimension<br/>Derived Field |
| Asset Objects | ![AI generated](/help/assets/icons/AI.svg) Objects of the asset. | Dimension<br/>Derived Field |
| Asset Photography Styles | ![AI generated](/help/assets/icons/AI.svg) Photography styles of the asset. | Dimension<br/>Derived Field |
| Asset Image Type | ![AI generated](/help/assets/icons/AI.svg) Image type of the asset. Possible values are: photograph, sketch, painting, digital_cartoon, infographics, graphic_design, collage, and software_screenshot. | Dimension<br/>Derived Field |
| Asset Camera Positions | ![AI generated](/help/assets/icons/AI.svg) Camera positions of the asset. | Dimension<br/>Derived Field |
| Asset Camera Proximities | ![AI generated](/help/assets/icons/AI.svg) Camera proximities of the asset. | Dimension<br/>Derived Field |
| Asset People Categories | ![AI generated](/help/assets/icons/AI.svg) People categories for the asset. Possible values are: person, man, woman, social group, crowd, people, boy, girl, and kid. | Dimension<br/>Derived Field |
| Asset Visual Content Density | ![AI generated](/help/assets/icons/AI.svg) Visual content density of the asset. Possible values are: low, medium, or high. Low content density implies a small amount of information present per unit area of the image. | Dimension |
| Asset Visual Attention Spread | ![AI generated](/help/assets/icons/AI.svg) Visual attention spread of the asset. Possible values are: low, medium, or high. Attention spread refers to the degree to which the attention of a viewer is divided between different parts of a picture. | Dimension<br/>Derived Field |
| Asset Lighting Condition | ![AI generated](/help/assets/icons/AI.svg) Lighting condition of the asset. Possible values are: golden hour, blue hour, midday, overcast, night, high-key, low-key, daylighting, incandescent, fluorescent, colorful, and studio. | Dimension<br/>Derived Field |
| Asset Camera Setting | ![AI generated](/help/assets/icons/AI.svg) Camera setting of the asset. Possible values are: fast shutter speed, long exposure. bokeh blur, motion blur, tilt-shift blur, flash, wide-angle, black and white, surreal, double-exposure, macro, and normal mode. | Dimension<br/>Derived Field |

{style="table-layout:fixed"}


## Asset events

| Title | Description | Type |
|---|---|---|
| Asset Views | Quantifiable measure of the number of views of the asset. | Metric |
| Asset Clicks | Quantifiable measure of the number of clicks of the asset. | Metric |

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

| Title | Description | Type |
|---|---|---|
| Asset Click-Trough Rate | Asset Clicks / Asset Views | Calculated metric |
| experience Click-Through Rate | Experience Clicks / Experience Views | Calculated metric |

{style="table-layout:fixed"}

