---
Title: Filter
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Filters out records in the pipe based on a given condition.
id: 7043c0c8
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: filter
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/filter.md
source_repo: https://github.com/redis/docs
title: Filter
weight: 50
---

```java
public GearsBuilder<T> filter​(
    gears.operations.FilterOperation<T> filter)
```

Filters out records in the pipe based on a given condition.

The filter operation should contain a conditional statement and return a boolean for each record:
- If `true`, the record will continue through the pipe. 
- If `false`, it filters out the record.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| filter | FilterOperation<T> | A function that checks a condition for each record in the pipe. Returns a boolean. |

## Returns

Returns a GearsBuilder object with the same template type as the input builder.

## Example

Get all records that contain the substring "person:":

```java
GearsBuilder.CreateGearsBuilder(reader).
    filter(r->{
        return r.getKey().contains("person:");
});
```