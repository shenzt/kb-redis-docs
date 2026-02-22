---
Title: FlatMap
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Maps a single input record to one or more output records.
id: 43446c20
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: flatMap
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/flatmap.md
source_repo: https://github.com/redis/docs
title: Flatmap
weight: 50
---

```java
public <I extends java.io.Serializable> GearsBuilder<I> flatMap​(
	gears.operations.FlatMapOperation<T,​I> flatmapper)
```

Maps a single input record to one or more output records.

The FlatMap operation must return an [`Iterable`](https://docs.oracle.com/javase/8/docs/api/java/lang/Iterable.html). RedisGears 
splits the elements from the `Iterable` object and processes them as individual records.

## Parameters
 
Type parameters:

| Name | Description |
|------|-------------|
| I | The template type of the returned builder object |

Function parameters:

| Name | Type | Description |
|------|------|-------------|
| flatmapper | <nobr>FlatMapOperation<T,​I></nobr> | For each input record, returns one or more output records |

## Returns

Returns a GearsBuilder object with a new template type.

## Example

```java
GearsBuilder.CreateGearsBuilder(reader).flatMap(r->{
   	return r.getListVal();
}); 
```