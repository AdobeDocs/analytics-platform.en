---
title: Implement Conversation Insights
description: Learn how to instrument your agent application or service for Conversation Insights.
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
---
# Implement Conversation Insights

To produce conversation data as XDM Experience Events and ensure that these conversation experience events end up in Adobe Experience Platform as datasets, instrument your agent application or service to use Conversation Insights.

This article documents the required implementation steps.

>[!PREREQUISITES]
>
>You must have an Experience Platform environment (organization and sandbox) available to collect the data.
Your Adobe organization must be enabled for the experimental agentic and conversation field groups.

## Schema and datasets

Configure datasets for the primary conversation events: prompt, response, feedback. These datasets can be based on the same schema (for example, a generic Conversation Insights schema) or based on individual schemas. 
You can define separate datasets for prompts, responses, and feedback or combine data into datasets. For example, use one dataset for prompts and responses and another dataset for feedback. Or use a single dataset for all conversation events. 

The schema used for the prompt, response, and feedback datasets must extend the XDM Experience Event base schema with required field groups. And can extend the XDM Experience Event base schema with additional field groups.

### Agentic Information field group

The **[!UICONTROL Agentic Information]** field group is a required field group and uses the `agenticExperience` object.

+++ Details

| Field Path (Dot Notation) | Type | Example Value | Notes |
|---|---|---|---|
| `conciergeID` | string | `"concierge-abc123"` | **New.** Unique identifier for the concierge |
| `name` | string | `"Brand Concierge"` | Name of the concierge combining a set of agents |
| `version` | string | `"1.0.0"` | Version of the concierge combining a set of agents |
| `environment` | string | `"prod"` | Environment this event originated from (dev, stage, prod) |
| `mode` | string | `"release"` | Mode the agent is in (test, preview, release) |
| `agents[]` | array | See agent object below | Array of agents used |
| `agents[].agentID` | string | `"agent-001"` | **New.** Unique identifier for the agent, referenced by `skills[].agentID` below |
| `agents[].name` | string | `"Chatbot Assistant"` | Agent name |
| `agents[].version` | string | `"2.1.3"` | Agent version |
| `agents[].score` | number | `0.92` | Agent confidence score in its the returned values |
| `agents[].skills[]` | array | See skill object below | **Deprecated** — use the top-level `skills[]` array below instead, which owns the full ordered list of skill calls and links each one to its agent via `agentID` |
| `agents[].skills[].name` | string | `"Intent Recognition"` | Skill name (deprecated array) |
| `agents[].skills[].version` | string | `"1.0.0"` | Skill version (deprecated array) |
| `agents[].skills[].score` | number | `0.95` | Skill confidence score (0-1) (deprecated array) |
| `agents[].skills[].parameters[]` | array | See parameters below | Parameters sent to the skill (key-value pairs) (deprecated array) |
| `agents[].skills[].parameters[].key` | string | `"language"` | Parameter key |
| `agents[].skills[].parameters[].value` | string | `"en-US"` | Parameter value |
| `skills[]` | array | See skill invocation object below | **New, experimental.** Full, ordered list of skill invocations for this experience, across all agents. Replaces the deprecated per-agent `agents[].skills[]` array |
| `skills[].skillID` | string | `"skill-intent-recognition"` | Identifier of the skill definition that was called |
| `skills[].skillInvocationID` | string | `"inv-9f2a-001"` | Unique identifier for this individual skill invocation, consistent even with redeliveries. De-duplication key when merging skill arrays downstream |
| `skills[].name` | string | `"Intent Recognition"` | Name of the skill that was called |
| `skills[].version` | string | `"1.0.0"` | Version of the skill that was called |
| `skills[].agentID` | string | `"agent-001"` | Identifier of the agent that invoked this skill, correlating to `agents[].agentID`. Grouping key consumers use to order skills within an agent, since subagents run in parallel |
| `skills[].invocationSource` | string | `"main"` | Whether invoked by the main agentic loop (`main`) or by a subagent (`subagent`) |
| `skills[].score` | number | `0.95` | Score resulting from matching the skill |
| `skills[].failed` | boolean | `false` | Flag stating that the skill execution failed |
| `skills[].errorReason` | string | `"timeout"` | Reason the skill failed, when `failed` is true |
| `skills[].sequenceNumber` | integer | `1` | Monotonically increasing index of this skill call within a single agent execution — not turn-global, since subagents run in parallel. Consumers order by `agentID`, then `sequenceNumber`, then `timestamp` as tiebreaker. Optional |
| `skills[].timestamp` | string (date-time) | `"2026-09-11T00:03:15Z"` | Time the skill was invoked, ISO 8601 UTC. Ordering key used after `sequenceNumber`. Producers should always populate this |
| `skills[].skillSource` | string | `"inline"` | How the skill definition was delivered to the runtime: `inline` (loaded inline into context) or `deferred` (loaded on demand) |
| `skills[].executionContext` | string | `"inline"` | Where the skill executes relative to the calling agent: `inline` or `forked` (runs in a forked sub-agent context) |
| `skills[].reasoning.narration` | string | `"Recognized an intent to verify a geography fact"` | Natural-language explanation of why this skill was called |
| `skills[].parameters[]` | array | See parameters below | Parameters passed in to the skill |
| `skills[].parameters[].key` | string | `"language"` | Parameter key |
| `skills[].parameters[].value` | string | `"en-US"` | Parameter value |

+++

To implement events propagating the Agentic Information field group with data, you should ensure:

* Agent configuration
  
  * Each agent has a unique agentID, name, and version combination.
  * Agent scores are normalized between `0.0` and `1.0`.
  * Use the `agentID` to reference agents by skill invocation.

* Skills invocation

  * Emit only one entry per skill call, across all agents, instead of nesting skills under each agent.
  * Populate skillInvocationID so downstream blending can remove duplicate redelivered events.
  * Order consumers properly. Group by `agentID`, then sort by `sequenceNumber`, falling back to `timestamp`. Ordering is required because subagents can execute in parallel
  * Use `invocationSource` and `executionContext` to distinguish primary versus subagent skills and inline versus forked execution.
  * Avoid using the deprecated `agents[].skills[]` array. If you have used the array in the past, treat the array as a read-only object.

* Skill Parameters

  * Parameters use the Adobe XDM key-value datatype and use common parameter types for language settings, thresholds, model configurations. For example, `"key":"language", "value":"en-US"`.

+++ Example usage of Agentic Information field group 

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffe",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"agent.interaction",
  "identityMap":{
    "ECID":[
      {
        "id": "12345678901234567890123456789012345678",
        "primary": true
      }
    ]
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      {
        "agentID":"agent-001",
        "name":"Chatbot Assistant",
        "version":"2.1.3",
        "score":0.92
      },
      {
        "agentID":"agent-002",
        "name":"Voice Assistant",
        "version":"3.0.0",
        "score":0.88
      }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline",
        "reasoning":{
          "narration":"Recognized an intent to verify a geography fact"
        },
        "parameters":[
          { "key":"language", "value":"en-US" },
          { "key":"confidenceThreshold", "value":"0.8" }
        ]
      },
      {
        "skillID":"skill-faq-retrieval",
        "skillInvocationID":"inv-9f2a-002",
        "name":"FAQ Retrieval",
        "version":"1.2.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.89,
        "failed":false,
        "sequenceNumber":2,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"inline",
        "executionContext":"forked",
        "parameters":[
          { "key":"maxResults", "value":"5" }
        ]
      },
      {
        "skillID":"skill-speech-recognition",
        "skillInvocationID":"inv-9f2a-003",
        "name":"Speech Recognition",
        "version":"2.0.1",
        "agentID":"agent-002",
        "invocationSource":"main",
        "score":0.91,
        "failed":false,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:15Z",
        "skillSource":"deferred",
        "executionContext":"inline",
        "parameters":[
          { "key":"languageModel", "value":"general" },
          { "key":"noiseSuppression", "value":"true" }
        ]
      }
    ]
  }
}
```

+++


### Conversation Event field group

The **[!UICONTROL Conversation Event]** field group is a required field group and uses  the `conversation` object.

The conversation object captures data for:

#### Conversation

A unique `conversationID` identifies a conversation. For example: `conversationID = "conv-001"`. The schema also supports `conversationName`. A human-readable name that describes the overall context of the conversation, such as: `France Geography Q&A`.

The `conversationID` allows all related turns events to be grouped into the same conversational experience.

#### Turn

A turn is one interaction cycle within a conversation.

`turnID` A unique `turnID` identifies a turn. For example:

`conversationID = "conv-001"`
`turnID = "turn-001"`

The same `conversationID` and `turnID` are used to correlate the prompt, response, and feedback associated with that turn. That correlation works across records that are delivered separately or end up in different datasets.


#### Prompt

A prompt is the input submitted to the agent. In most customer scenarios, this input is the user's question, request, instruction, or message.

The prompt uses the following representation: `conversation.prompt`

Important prompt fields include:

|Field |   Meaning |
|---|---|
|`prompt.source`  |  Who or what produced the prompt, commonly end-user. |
| `prompt.raw[]` | One or more raw content segments. |
| `prompt.raw[].text`  |  The actual prompt text or content. |
| `prompt.raw[].purpose` | The purpose of the content, such as User Input or link. |

A prompt can contain multiple raw segments. For example, a user enters text and includes a URL. 

* `Prompt`
  * `"What is the capital of France"`
  * `"https://example.com/france"`


#### Response

A response is the content returned by the agent or another responding party.

`conversation.response` A unique `responseID` represents the response. 

Important response fields include:

| Field | Meaning |
|---|---|
| `response.source` | Who or what produced the response. |
| `response.raw[]` | One or more response-content segments |
| `response.raw[].text` | The response text or content. |
| `response.raw[].purpose` | The purpose of the content segment. |

The documented source types include:

| Source |  Meaning |
|---|----|
| `bot`  | Automated agent response. |
| `canned` |   Predefined or templated response. |
| `concierge` | Human agent response. |
| `end-user` | Human user-generated content where applicable. |

#### Feedback

Feedback is the user's explicit evaluation or reaction to the interaction.

The feedback structure includes: `conversation.feedback`.

Examples:

* `feedback.raw[].text: "Great help"`
* feedback.rating.score: 1
* feedback.rating.classification: "Thumbs Up"
* `feedback.rating.reasons[]: ["Accurate", "Quick response"]`

The documented rating score range is from `-1.0` to `1.0`.

A feedback event can be represented as a feedback-only event using: `eventType = "conversation.feedback"`.

When feedback applies to a particular turn, preserve the appropriate `conversationID` and `turnID` so that the conversation blender can associate the feedback with the relevant interaction.


#### Signal

A signal is a structured analytical observation about conversation content. The signal extraction service extracts signals.

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


#### Conversation

See below for the full details of a conversation object.

+++ Details 

| Field Path (Dot Notation) | Type | Example Value | Notes |
|---|---|---|---|
| `conversationID` | string | `"conv-001"` | Groups multiple turns together |
| `conversationName` | string | `"France Geography Q&A"` | **New.** Name given to a conversation representing its overall context |
| `turnID` | string | `"turn-001"` | Unique ID for this turn |
| `prompt.source` | string | `"end-user"` | Source of prompt, other options might include a cached value, canned value, etc. |
| `prompt.raw[]` | array | See raw object below | Raw prompt data |
| `prompt.raw[].text` | string | `"What is the capital of France?"` | Actual text content |
| `prompt.raw[].purpose` | string | `"User Input"` | Purpose of this text segment |
| `response.source` | string | `"bot"` | Source of response |
| `response.raw[]` | array | See raw object below | Raw response data |
| `response.raw[].text` | string | `"The capital of France is Paris."` | Response text content |
| `response.raw[].purpose` | string | `"main"` | Purpose of response segment, other options might include links, pictures, etc. |
| `feedback.source` | string | `"end-user"` | Source of feedback |
| `feedback.raw[]` | array | See raw object below | Raw feedback data |
| `feedback.raw[].text` | string | `"Great help"` | Feedback text |
| `feedback.raw[].purpose` | string | `"free-form text"` | Purpose of feedback segment, other options might include screen-shots, media, etc. |
| `feedback.rating.score` | number | `1` | Numerical rating score from -1.0 to 1.0 |
| `feedback.rating.classification` | string | `"Thumbs Up"` | Rating classification |
| `feedback.rating.reasons[]` | array | `["Accurate", "Quick response"]` | Array of rating reasons |
| `signals[]` | array | See signal object below | Derived signals based on this event and the conversation to date. Each entry is a single named signal with its own scope |
| `signals[].scope` | string | `"turn"` | Scope of inputs from which this set of signals is derived (turn, conversation-to-date, last-N-turns, feedback) |
| `signals[].attributes` | object | See attributes below | **Deprecated.** Container for signal attributes. Each attribute is an object with value or values in it. This is to accommodate the anticipated need to support population of ML/agent information used to generate the signal. |
| `signals[].attributes.subjects` | object | See subjects below | **Deprecated.** Subjects container |
| `signals[].attributes.subjects.values[]` | array | See subject values below | **Deprecated.** Array of subject values |
| `signals[].attributes.subjects.values[].phrase` | string | `"product pricing"` | **Deprecated.** A phrase or keyword extracted from the scoped input |
| `signals[].attributes.subjects.values[].qualifiers[]` | array | `["important", "urgent"]` | **Deprecated.** List of qualifiers for the phrase |
| `signals[].attributes.intents` | object | See intents below | **Deprecated.** Intents container |
| `signals[].attributes.intents.values[]` | array | `["make a purchase", "learn more"]` | **Deprecated.** Intents derived from the scoped input |
| `signals[].attributes.tones` | object | See tones below | **Deprecated.** Tones container |
| `signals[].attributes.tones.values[]` | array | `["thrilled", "contemplative"]` | **Deprecated.** Tones derived from the scoped input |
| `signals[].attributes.sentiment` | object | See sentiment below | **Deprecated.** Sentiment container |
| `signals[].attributes.sentiment.value` | number | `0.71` | **Deprecated.** Score from -1 (negative) to 1 (positive) indicating sentiment |
| `signals[].name` | string | `"sentiment"` | **New** (replaces the deprecated `attributes` container). Identifier for this signal, e.g. "subjects", "intents", "tones", "sentiment", or any producer-defined name — producers can add new signal types without a schema change |
| `signals[].type` | string | `"number"` | **New.** Data type of this signal's values (`string`, `number`, or `boolean`) — tells consumers which typed value field is populated on each entry of `values[]` |
| `signals[].values[]` | array | See values object below | One or more values for this signal |
| `signals[].values[].stringValue` | string | `"curious"` | Populated when `type` is "string" — a categorical value such as an intent, tone, or extracted phrase |
| `signals[].values[].numberValue` | number | `0.71` | Populated when `type` is "number" — for example a sentiment score from -1 to 1, or an intensity |
| `signals[].values[].booleanValue` | boolean | `true` | Populated when `type` is "boolean" — a true/false flag |
| `signals[].values[].confidence` | number | `0.9` | **New.** Confidence the producer assigns to this value, from 0 to 1 |
| `signals[].values[].qualifiers[]` | array | `["important", "urgent"]` | Additional descriptors for this value, similar to keywords but more meaningful |
| `signals[].values[].metadata[]` | array | See parameters below | **New.** Producer-defined metadata for this value as key/value pairs, e.g. context about the ML/agent that generated the signal |

+++


The signal extraction service populates the `signals` object for the signals dataset. 

The previous `signals[].attributes.{subjects,intents,tones,sentiment}` container is deprecated.


### Additional field groups

You can add optional field groups to the schema you use for prompt, response, and feedback datasets. For example:

* **Web Details** field group. To capture details of the web page the conversation was embedded in.
* **Commerce Details** field group. To capture the product details of the recommended product mentioned as part of the conversation.
  


The customer is responsible for producing the source conversation events. Adobe Platform subsequently performs signal extraction and data blending. The customer does not need to implement the signal-extraction or blending services.

This document covers the Conversation Insights MVP input requirements and the current Agentic Schema Update. It does not include Conversation Insights 1.0 capabilities or later-release requirements.

### Event type

You need to set one of the following values for `eventType` (String) for each conversation event:

| Value| Explanation |
|---|---|
| `conversation turn` |Complete conversation turn with prompt and response |
| `conversation recommendation` | Conversation-based recommendation |
| `conversation feedback` | Feedback-only event |


### Source type

You need to set one of the following values for `source` for each `prompt`, `response`, or `feedback` object in an event:

| Value | Description |
|---|---|
| `end-user` |Human user input |
| `bot` | Automated agent response |
| `canned` | Pre-defined/templated response |
| `concierge` | Human agent response |

### Purpose type (raw text)

You need to set one of the following values for the `purpose` attribute on any element of the `raw` object in a `prompt`, `response`, or `feedback` object.

| Value | Description |
|---|---|
| `User Input` | Primary user input |
| `main` | Main response content |
| `advertisement` | Promotional content |
| `citation` | Reference/source links |
| `link` | External links |
| `image` | Image references |
| `enum picker` | Structured feedback selection |


### Example

See below for example usage of the Conversation Event field group in various scenarios.

+++ Details 

>[!BEGINTABS]

>[!TAB Turn event example]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What is the capital of France? This link says it is Lyon.", "purpose": "User Input" },
        { "text": "https://wrong.geography.com/france", "purpose": "link" }
      ]
    }
  }
}
```

>[!TAB Response event example]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffd",
  "timestamp":"2026-09-11T00:03:16Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "turnID": "int-001",
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "The capital of France is Paris.", "purpose": "main" },
        { "text": "Would you like to plan a trip to Paris?", "purpose": "advertisement" },
        { "text": "https://en.wikipedia.org/wiki/France", "purpose": "citation" }
      ]
    }
  }
}
```

>[!TAB Feedback event example]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffb",
  "timestamp":"2026-09-12T00:03:15Z",
  "eventType":"conversation.feedback",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "conversation": {
    "conversationID": "conv-001",
    "conversationName": "France Geography Q&A",
    "feedback": {
      "source": "end-user",
      "raw": [
        { "text": "Great help", "purpose": "text box" }
      ],
      "rating": {
        "score": 1,
        "classification": "Thumbs Up",
        "reasons": ["Accurate", "Quick response"]
      }
    }
  }
}
```

>[!TAB Product recommendations event example]

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827ffa",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.recommendation",
  "identityMap":{
    "ECID":[
      { "id": "12345678901234567890123456789012345678", "primary": true }
    ]
  },
  "web": {
    "webPageDetails": { "URL": "https://www.adobe.com", "name": "Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-xyz789",
    "name":"Product Concierge",
    "version":"1.0.0",
    "environment":"prod",
    "mode":"release",
    "agents":[
      { "agentID":"agent-010", "name":"Product Advisor", "version":"1.0.0", "score":0.92 }
    ]
  },
  "conversation": {
    "conversationID": "conv-001",
    "turnID": "int-099",
    "prompt": {
      "source": "end-user",
      "raw": [
        { "text": "What product do you recommend for a new user trying to create a poster?", "purpose": "User Input" }
      ]
    },
    "response": {
      "source": "concierge",
      "raw": [
        { "text": "To create a poster, we would recommend Adobe Express - https://express.adobe.com.", "purpose": "main" },
        { "text": "https://express.adobe.com", "purpose": "link" }
      ]
    }
  },
  "productListItems": [
    { "SKU": "express" }
  ]
}
```

>[!ENDTABS]

+++

## Data collection

Use the following data collection strategy for Conversation Insights.


### Event types

Your agent application or service sends an event as soon as possible. Ensure the app or service does not wait for a response before sending the prompt across with the information available at the time of the event.

This recommendation implies that: 

* Prompt, response, and feedback objects are populated independently and should not be forced to be part of a single event.
* Multiple events with the same `conversationID` and `turnID` are expected across datasets.

### Event correlation

The agent application or service must preserve stable identifiers across all related events.

| Field path | Description |
|---|---|
| `conversation.conversationID` | Unique identifier for the overall conversation. |
| `conversation.turnID` |Unique identifier for an individual turn within the conversation. |
| `_id` | Experience Event record identifier. |
| `timestamp` | Time at which the event occurred. |
| `eventType` | Identifies the type of conversation event. |

* The same `conversationID` must be used for all events belonging to the same conversation.

* The same `turnID` must be used for the prompt, response, and any feedback associated with the same turn. Multiple events with the same `turnID` can exist across the prompt, response, and feedback datasets.
  
The agent application or service generates IDs that remain stable during retries or redelivery. This allows downstream processing to associate events correctly and avoid unintended duplicate events.

## Signal extraction

Signal extraction takes place after data collection. Your agent application or service does not populate additional signals.

+++ Example turn event with signals

```json
{
  "_id":"a33e1068-3966-468b-8682-e5e493827fff",
  "timestamp":"2026-09-11T00:03:15Z",
  "eventType":"conversation.turn",
  "identityMap":{
    "ECID":[
      { "id":"12345678901234567890123456789012345678", "primary":true }
    ]
  },
  "web":{
    "webPageDetails":{ "URL":"https://www.adobe.com", "name":"Home Page" }
  },
  "agenticExperience":{
    "conciergeID":"concierge-abc123",
    "name":"Customer Support Experience",
    "version":"1.0.0",
    "environment":"dev",
    "mode":"preview",
    "agents":[
      { "agentID":"agent-001", "name":"Chatbot Assistant", "version":"2.1.3", "score":0.92 }
    ],
    "skills":[
      {
        "skillID":"skill-intent-recognition",
        "skillInvocationID":"inv-9f2a-001",
        "name":"Intent Recognition",
        "version":"1.0.0",
        "agentID":"agent-001",
        "invocationSource":"main",
        "score":0.95,
        "sequenceNumber":1,
        "timestamp":"2026-09-11T00:03:14Z",
        "skillSource":"inline",
        "executionContext":"inline"
      }
    ]
  },
  "conversation":{
    "conversationID":"conv-001",
    "conversationName":"France Geography Q&A",
    "turnID":"int-001",
    "signals":[
      {
        "scope":"turn",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"capital of France", "confidence":0.93, "qualifiers":["geographical","factual-question"] },
          { "stringValue":"Lyon", "confidence":0.87, "qualifiers":["incorrect","misinformation"] }
        ]
      },
      {
        "scope":"turn",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"seek-information" },
          { "stringValue":"verify-facts" }
        ]
      },
      {
        "scope":"turn",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"curious" },
          { "stringValue":"uncertain" }
        ]
      },
      {
        "scope":"turn",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.1 }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"subjects",
        "type":"string",
        "values":[
          { "stringValue":"unreliable source", "qualifiers":["external-link","potentially-misleading"] },
          { "stringValue":"geography knowledge", "qualifiers":["educational","basic-facts"] }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"intents",
        "type":"string",
        "values":[
          { "stringValue":"fact-checking" },
          { "stringValue":"learn-correct-information" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"tones",
        "type":"string",
        "values":[
          { "stringValue":"questioning" },
          { "stringValue":"seeking-clarification" }
        ]
      },
      {
        "scope":"conversation-to-date",
        "name":"sentiment",
        "type":"number",
        "values":[
          { "numberValue":0.3 }
        ]
      }
    ],
    "prompt":{
      "source":"end-user",
      "raw":[
        { "text":"What is the capital of France? This link says it is Lyon.", "purpose":"User Input" },
        { "text":"https://wrong.geography.com/france", "purpose":"link" }
      ]
    }
  }
}
```

+++

## Data blending

The conversation blender service merges events from prompt, response, feedback, and signal events datasets into a dedicated blended conversation events dataset. That dataset is used in Customer Journey Analytics as part of a connection. The components within that dataset are added to the data views you have specified for a Conversation Insights configuration.
