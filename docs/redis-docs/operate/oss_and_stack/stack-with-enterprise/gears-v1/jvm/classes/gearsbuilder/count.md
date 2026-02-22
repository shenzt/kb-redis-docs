---
Title: Count
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Counts the number of records in the pipe.
id: 3c18026e
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: count
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/count.md
source_repo: https://github.com/redis/docs
title: Count
weight: 50
---

```java
public GearsBuilder<java.lang.Integer> count()
```

Counts the number of records in the pipe and returns the total as a single record.

## Parameters
 
None

## Returns

Returns a GearsBuilder object with a new template type of `Integer`.

## Example

```java
GearsBuilder.CreateGearsBuilder(reader).count();
```