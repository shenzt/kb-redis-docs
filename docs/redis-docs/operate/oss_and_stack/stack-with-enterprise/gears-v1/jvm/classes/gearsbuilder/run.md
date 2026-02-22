---
Title: Run
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Runs the pipeline of functions immediately.
id: d69bb14a
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: run
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/run.md
source_repo: https://github.com/redis/docs
title: Run
weight: 50
---

```java
public void run()

public void run​(boolean jsonSerialize, boolean collect)
```

Runs the pipeline of functions immediately upon execution. It will only run once.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| collect | boolean | Whether or not to collect the results from the entire cluster before returning them |
| jsonSerialize | boolean | Whether or not to serialize the results to JSON before returning them |

## Returns

None

## Example

```java
GearsBuilder.CreateGearsBuilder(reader).run();
```