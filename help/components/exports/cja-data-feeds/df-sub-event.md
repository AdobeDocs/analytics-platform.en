---
title: Apply Data Transformations for Data Feeds
description: Learn about the different ways to transform data feed data, using component settings, derived fields, or SQL.
hide: true
feature: Components
---
# Export sub-events in data feeds

{{release-limited-testing}}

Need to explain that sub-events are represented in data feed exports with their hierarchy. In AA, they were represented as a single column. For example, product lists, list vars.

Depends on how you configure your schema. Anything that is an array (string or ) will be sub-event. 

When you are building the data feed, if you try to add a column that is a sub-event, you get a dialog that allows you to add all of the peer sub-events. All of these events will appear in a single column of the data feed output. 

Include example SQL for a product object array (Matt sent me something that could be simplified)

Even though data feeds doesn't flatten everything, it's completely flattened in Analysis Workspace. If you have an array of objects, individual objects are flattened in Workspace, but in data feeds they're represented as a group. The way it's represented in the schema is different from Workspace which is different from DF. 

