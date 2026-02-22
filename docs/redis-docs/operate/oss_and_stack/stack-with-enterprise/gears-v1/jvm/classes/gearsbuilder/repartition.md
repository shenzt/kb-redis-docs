---
Title: Repartition
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Moves records between shards according to the extracted data.
id: edc12a33
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: repartition
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/repartition.md
source_repo: https://github.com/redis/docs
title: Repartition
weight: 50
---

```java
public GearsBuilder<T> repartition​(
	gears.operations.ExtractorOperation<T> extractor)
```

Moves records between the shards. The extracted data determines the new shard location for each record.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| extractor | <nobr>ExtractorOperation<T></nobr> | Extracts a specific value from each record |

## Returns

Returns a GearsBuilder object with a new template type.

## Example

Repartition by value:

```java
GearsBuilder.CreateGearsBuilder(reader).
   	repartition(r->{
   		return r.getStringVal();
});
```