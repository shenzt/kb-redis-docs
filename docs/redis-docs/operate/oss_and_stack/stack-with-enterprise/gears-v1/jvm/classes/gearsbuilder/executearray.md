---
Title: ExecuteArray
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Runs a Redis command.
id: aaf128fd
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: executeArray
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/executearray.md
source_repo: https://github.com/redis/docs
title: Executearray
weight: 50
---

```java
public static native java.lang.Object executeArray(
    java.lang.String[] command)
```

Runs a Redis command. It accepts an array of strings, which represents the command to execute.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| command | array of strings | A Redis command |

## Returns

Returns the command result. It could be a string or an array of strings, depending on the command.

## Example

```java
GearsBuilder.executeArray(new String[]{"SET", "age:maximum", "100"});
```