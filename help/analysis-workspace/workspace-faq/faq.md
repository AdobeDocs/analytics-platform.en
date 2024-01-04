---
description: Learn about Workspace FAQs and troubleshooting tips.
title: Frequently asked questions
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
role: User
---
# Frequently asked questions

| Question | Answer |
|--- |--- |
| **What are the prerequisites for using Analysis Workspace?** | Using Analysis Workspace in Customer Journey Analytics requires a working Customer Journey Analytics implementation. Make sure your organization is sending data to the Adobe Experience Platform before using the tool.|
| **What are the Administration and access requirements for Analysis Workspace?** | See [Administration Requirements](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md).|
| **Will using Analysis Workspace affect data collection?** | Since Analysis Workspace is a reporting tool, it has no impact on data collection. There are no repercussions to indiscriminately dragging components into a project to see what works. Drag different combinations of dimensions and metrics into your workspace project to see what is available to you. If you accidentally drag an invalid component to your workspace project or would like to go back a step, press ctrl+Z (Windows) or cmd+Z (Mac) to undo the last action made. You can also start with a clean slate by clicking *[!UICONTROL Project] > [!UICONTROL New]* in the upper left menu.|
| **How do I implement Analysis Workspace?** | No special implementation is required. Analysis Workspace is available to all companies Customer Journey Analytics. However, standard permissions to content (such as project components) apply, and for curating and sharing projects. See [Administration and Access Requirements](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md). |
| **How can I optimize performance of Analysis Workspace?** | See [Optimizing Performance](/help/admin/optimizing-performance.md). |

## Troubleshooting

**When I drag a metric over, it says 'Invalid data'.**

Invalid data means that Adobe cannot return data using the combination of dimensions and metrics used in the report. For example, two metrics stacked on top of each other cannot be returned as data, as there is no way to display two metrics that way. Instead, place the metrics side by side.

**When I drag a metric over, I don't see any actual data - just zeros.**

If you successfully created a workspace report but there's no data, there are a few things you can check:

* If you applied a filter in your report, the filter criteria might not match any data. Try removing the filter or adjusting the filter definition.
* Check the date range in the upper right corner and make sure it's set to a value that you'd expect.
* Navigate to your website and use the [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.
