---
Title: Collect
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Collects all records to the origin shard.
id: 172cf870
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: collect
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/collect.md
source_repo: https://github.com/redis/docs
title: Collect
weight: 50
---

```java
public GearsBuilder<T> collect()
```

Collects all of the records to the shard where the RedisGears job started.

## Parameters
 
None

## Returns

Returns a GearsBuilder object with the same template type as the input builder.

## Example

```java
GearsBuilder.CreateGearsBuilder(reader).collect();
```