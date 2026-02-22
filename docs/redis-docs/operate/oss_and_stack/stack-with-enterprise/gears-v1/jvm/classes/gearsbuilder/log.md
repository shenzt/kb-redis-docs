---
Title: Log
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Writes a log message to the Redis log file.
id: cbb7535b
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: log
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/log.md
source_repo: https://github.com/redis/docs
title: Log
weight: 50
---

```java
public static void log​(java.lang.String msg)

public static void log​(java.lang.String msg, LogLevel level)
```

Writes a log message to the Redis log file. If you do not specify a `LogLevel`, it will default to `NOTICE`.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| msg | string | The message to write to the log |
| level | LogLevel | The log level (DEBUG, NOTICE, VERBOSE, WARNING) |

## Returns

None

## Example

```java
GearsBuilder.log(
    "Setting keys to expire after 1 month", 
    LogLevel.WARNING
);
```