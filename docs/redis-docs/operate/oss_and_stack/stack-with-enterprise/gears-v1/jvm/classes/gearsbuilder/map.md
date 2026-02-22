---
Title: Map
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Maps records one-to-one.
id: 4700ce88
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: map
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/map.md
source_repo: https://github.com/redis/docs
title: Map
weight: 50
---

```java
public <I extends java.io.Serializable> GearsBuilder<I> map​(
	gears.operations.MapOperation<T,​I> mapper)
```

Maps each input record in the pipe to an output record, one-to-one.

## Parameters
 
Type parameters:

| Name | Description |
|------|-------------|
| I | The template type of the returned builder |

Function parameters:

| Name | Type | Description |
|------|------|-------------|
| mapper | <nobr>MapOperation<T,​I></nobr> | For each input record, returns a new output record |

## Returns

Returns a GearsBuilder object with a new template type.

## Example

Map each record to its string value:

```java
GearsBuilder.CreateGearsBuilder(reader).
 		map(r->{
    		return r.getStringVal();
});
```