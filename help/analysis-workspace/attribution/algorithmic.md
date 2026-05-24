---
title: Algorithmic Attribution
description: Understand the details of the algorithmic attribution model.
feature: Attribution
role: User, Admin
exl-id: dd2b2a5b-9c36-4534-999f-f96604f29eab
autotag-review: '2026-05-19T07:20:44.651Z'
TQID: 'https://experienceleague.adobe.com/XPFzwdaB2d1PaGEyiYSlzri7Luo4E2uqlMdKClsExdw'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: c91f8bd2-df97-4c6a-afcd-f1cde8221302
    internal-label: Attribution
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
---
# Algorithmic attribution

The Algorithmic [attribution model](models.md) in Analysis Workspace differs from other models in that it uses statistical techniques to allocate credit across the dimension items in your report or freeform table. Like all other attribution models in Analysis Workspace, algorithmic attribution can be used on any dimension or metric. Algorithmic attribution supports unlimited segmentation and breakdowns, and distributes 100% of conversions to one or more dimensions in the table (also known as "fractional" attribution).

<!-- 

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Algorithmic attribution](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/attribution-iq/algorithmic-model-in-attribution-iq){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

The algorithm used for attribution is based on the Harsanyi Dividend from cooperative game theory. The Harsanyi dividend is a generalization of the Shapley value solution (named after Lloyd Shapley, a Nobel Laureate economist) to distribute credit among players in a game with unequal contributions to the outcome.

At a high level, the attribution calculation of the conversion credit for each touchpoint considers each of the marketing touchpoints within a lookback window as a coalition of players. To that coalition of players, a surplus must be equitably distributed. Each coalition's surplus distribution is determined from to the surplus that each subcoalition recursively created previously. 

For more details, see John Harsanyi's and Lloyd Shapley's original papers:

* Shapley, Lloyd S. (1953). A value for n-person games. *Contributions to the Theory of Games, 2(28)*, 307-317.
* Harsanyi, John C. (1963). A simplified bargaining model for the n-person cooperative game. *International Economic Review 4(2)*, 194-220.

>[!NOTE]
>
>The outcome of Algorithmic attribution only differs from other models when multiple touchpoints exist within the given lookback window. Conversions with a single touchpoint receive 100% credit regardless of attribution model.
