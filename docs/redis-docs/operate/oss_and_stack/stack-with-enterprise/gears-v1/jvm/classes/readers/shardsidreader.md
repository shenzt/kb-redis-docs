---
Title: ShardsIDReader
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Gets the shard ID for each shard in a database.
id: 6bbbc5f7
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: ShardsIDReader
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/readers/shardsidreader.md
source_repo: https://github.com/redis/docs
title: Shardsidreader
weight: 60
---

The `ShardsIDReader` creates a single record on each shard that represents the current shard's ID.
 
Use this reader when you want to run an operation on each shard in the database.

## Parameters

None

## Output records

Creates a record for each shard with the shard's cluster identifier.

## Example

```java
ShardsIDReader reader = new ShardsIDReader();
```