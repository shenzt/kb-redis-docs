---
Title: CreateGearsBuilder
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Creates a new GearsBuilder object.
id: 054de87b
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: CreateGearsBuilder
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/creategearsbuilder.md
source_repo: https://github.com/redis/docs
title: Creategearsbuilder
weight: 50
---

```java
public static <I extends java.io.Serializable> GearsBuilder<I> CreateGearsBuilder​(
    gears.readers.BaseReader<I> reader)

public static <I extends java.io.Serializable> GearsBuilder<I> CreateGearsBuilder​(
    gears.readers.BaseReader<I> reader, 
    java.lang.String desc)
```

Creates a new `GearsBuilder` object. Use this function instead of a `GearsBuilder` constructor to avoid type warnings.

## Parameters

Type Parameters:

| Name | Description |
|------|-------------|
| I | The template type of the returned builder. The reader determines the type. |

Parameters:

| Name | Type | Description |
|------|------|-------------|
| desc | string | The description |
| reader | BaseReader<I> | The pipe reader |

## Returns

Returns a new GearsBuilder object.

## Example

```java
GearsBuilder.CreateGearsBuilder(reader);
```