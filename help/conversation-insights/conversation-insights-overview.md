---
title: Conversation Insights Overview
description: Learn about the Conversation Insights value and terminlogy and learn how Conversation Insights works.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
---
# Conversation Insights

Conversation Insights enables you to analyze conversations from the agent experiences you offer to your customers. Those agent experiences can be based on large language models (LLM) or based on human conversations. Conversation Insights analyzes the conversations at scale and provides context for these conversations  within the full customer journey. Through Conversation Insights you are able to understand the impact of agents on actual user outcomes.

Conversation Insights addresses problems you might experience. Such as:

* You do not have insight into what happens when customers interact with agents (LLM or human) within the context of the journey.
* You do not have the ability to understand:
  * what agents are telling customers at scale.
  * how customer interact with agents at scale.
  * what is the overall impact on KPIs as a result of these interaction.
* You create agentic experiences under pressure to accomodate shifting user preferences.

With Conversation Inghts you are able to understand:

* What agents are telling users.
* What users are asking from agents.
* How the conversations impact your KPIs.

Ultimately, you are able to determine how your agents are performing against the directives, how close the agents are sticking to brand guidelines, and whether the cost of running agents is worth the outcomes.


## Model

Conversation Insights analyzes agent interactions at two levels:

* Conversation level: The complete interaction between a user and an agent, which may contain many turns.
* Turn level: One interaction cycle within that conversation, generally consisting of a user prompt and an agent response.

The agent application emits conversation-related experience events into Experience Platform. Prompt, response, and feedback event data can arrive independently. Platform services correlate and blend those events into a turn-level record, optionally enrich the data with extracted signals, and make the resulting data available for Customer Journey Analytics reporting.

### Conversation

A conversation is the complete interaction between a user and an agent. It can contain one or many turns.

A conversation is identified by a unique `conversationID`. For example: `conversationID = "conv-001`". The schema also supports `conversationName`. A human-readable name that describes the overall context of the conversation, such as: `France Geography Q&A`.

The `conversationID` allows all related turns events to be grouped into the same conversational experience.

A conversation is therefore the container or grouping level. That container is useful for questions such as:

* How many conversations occurred?
* What was the overall topic of a conversation?
* How did sentiment change across a conversation?
* Which conversations eventually led to a conversion?

### Turn

A turn is one interaction cycle within a conversation.

A turn is identified by: `turnID`. For example:

`conversationID = "conv-001"`
`turnID = "turn-001"`

The same `conversationID` and `turnID` are used to correlate the prompt, response, and feedback associated with that turn. That correlation works across records that are delivered separately or end up in different datasets.

A typical turn consists of

* User prompt
* Agent response
* (optional) User feedback

The turn is the primary analytical object for reporting purposes. The Conversation Blender service combines the available prompt, response, feedback, and signal information into turn-level records.

### Prompt

A prompt is the input submitted to the agent. In most customer scenarios, this is the user's question, request, instruction, or message.

The prompt is represented by: `conversation.prompt`

Important prompt fields include:

|Field |   Meaning |
|---|---|
|`prompt.source`  |  Who or what produced the prompt, commonly end-user. |
| `prompt.raw[]` | One or more raw content segments. |
| `prompt.raw[].text`  |  The actual prompt text or content. |
| `prompt.raw[].purpose` | The purpose of the content, such as User Input or link. |

A prompt can contain multiple raw segments. For example, a user might enter text and include a URL. 

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`

The prompt is the primary input from which Conversation Insights can derive analytical information such as:

* The user's intent
* The subject or topic
* The user's tone
* The user's sentiment
* Other supported signals

### Response

A response is the content returned by the agent or another responding party.

The response is represented by: `conversation.response`. 

Important response fields include:

| Field | Meaning |
|---|---|
| response.source | Who or what produced the response. |
| response.raw[] | One or more response-content segments |
| response.raw[].text | The response text or content. |
| response.raw[].purpose | The purpose of the content segment. |


The documented source types include:

| Source |  Meaning |
|---|----|
| bot  | Automated agent response. |
| canned |   Predefined or templated response. |
| concierge | Human agent response. |
|end-user | Human user-generated content where applicable. |

A response may contain different types of content. For example:

* Response
  * Main answer
  * Citation or reference
  * Link
  * Image
  * Promotional content

This distinction is useful because the analysis may need to separate the main answer from supporting links, citations, advertisements, or other response components.

### Feedback

Feedback is the user's explicit evaluation or reaction to the interaction.

It can contain:

* Free-form feedback text
* A numerical rating
* A rating classification
* One or more reasons for the rating


The feedback structure includes: `conversation.feedback`.

Examples:

* `feedback.raw[].text: "Great help"`
* `feedback.rating.score: 1`
* `feedback.rating.classification: "Thumbs Up"`
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`


The documented rating score range is from `-1.0` to `1.0`.

Feedback is not necessarily available at the same time as the prompt or response. You can send the feedback at a later time from the app or service, after the user has evaluated the answer.

The feedback event can be represented as a feedback-only event using: `eventType = "conversation.feedback"`.

When feedback applies to a particular turn, you should preserve the appropriate `conversationID` and `turnID` so that the Conversation Blender can associate the feedback with the relevant interaction.


### Signal

A signal is a structured analytical observation about conversation content. 

Signals can be:

* Extracted by the Signal extraction service.
* Provided by your agent experience application if that application has its own signal-generation capability.

#### Signal fields

A signal has the following fields.


| Field |   Meaning|
|---|----|
| `scope` |   The input range used to derive the signal, such as turn or conversation-to-date. |
| `name`  |  The signal identifier, such as subjects, intents, tones, or sentiment. Poducer-defined signal names are also supported. |
| `type` |   The value type: string, number, or boolean. |
| `values[]`  |  One or more values associated with the signal. |
| `stringValue`  |  A string signal value, such as an intent, tone, or subject. |
| `numberValue`  |  A numeric signal value, such as a sentiment score. |
| `booleanValue`  |  A true/false signal value. |
| `confidence`  |  Optional producer confidence in the signal value, normally between 0 and 1. |
| `qualifiers[]` |   Optional descriptors that add context to a signal value. |
| `metadata[]` |   Optional producer-defined key/value metadata. |

#### Skill invocations

Skills represent capabilities invoked during agent processing.

Each skill invocation can include:

| Value | Description |
|---|---|
| `skillID` | identifier of the skill definition. |
| `skillInvocationID` | unique identifier for that invocation. |
| `agentID` | the agent that invoked the skill. |
| `sequenceNumber` | ordering within that agent execution.|
| `timestamp` | invocation time. |
| `invocationSource` | whether the skill was invoked by the main loop or a subagent. |
| `executionContext` | whether it ran inline or in a forked context. |
| `failed and errorReason` | execution status. |
| `parameters[]` | input parameters passed to the skill.|

New producers should not populate the deprecated nested agents[].skills[] array.

## How it works

Conversation Insights is built upon three core functionalities:

* **Data collection**: collects all the necessary datapoints for users to be able to understand how well LLM and agents perform their tasks.
* **Signal extraction**: transforms the unstructured prompts and responses (also known as turns) into reportable datapoints, like intent and sentiment. So users can report on those datapoints at scale.
* **Reporting**: analyze conversations at scale in the context of the customer journey to determine an agent's effacy and ROI.

![Conversation Insights How It Works illustration](assets/conversation-insights.png){zoomable="yes"}

| | Description | 
|---|---|
| 1 | You instrument your agent experience application to create events in prompts ![CommentText](/help/assets/icons2/CommentText.svg), responses ![CommentReply](/help/assets/icons2/CommentReply.svg), and feedback ![Feedback](/help/assets/icons2/Feedback.svg) datasets.<br/>For details on how to instrument your agent experience application, refer to the implementation documentation. |
| 2 | The Signal extraction service extracts signals from the prompts ![CommentText](/help/assets/icons2/CommentText.svg), responses ![CommentReply](/help/assets/icons2/CommentReply.svg), and feedback datasets ![Feedback](/help/assets/icons2/Feedback.svg) as signal events ![OnAir](/help/assets/icons/OnAir.svg) and stores these signal events in a new dataset.<br>Implemented as part of the definition a [Conversation Insights configuration](./conversation-insights-configure.md). |
| 3 | The Blend service blends the events from the prompts ![CommentText](/help/assets/icons2/CommentText.svg), responses ![CommentReply](/help/assets/icons2/CommentReply.svg), feedback ![Feedback](/help/assets/icons2/Feedback.svg), and signals ![OnAir](/help/assets/icons/OnAir.svg) event datasets and outputs the blended ![Merge](/help/assets/icons/Merge.svg)events into a new dataset.<br>Implemented as part of the definition a [Conversation Insights configuration](./conversation-insights-configure.md). |
| 4 | The blended ![Merge](/help/assets/icons/Merge.svg) dataset becomes part of the connection and the components defined in the schema used for the blended dataset become part of the dataview.<br>Implemented as part of the definition a [Conversation Insights configuration](./conversation-insights-configure.md). |

