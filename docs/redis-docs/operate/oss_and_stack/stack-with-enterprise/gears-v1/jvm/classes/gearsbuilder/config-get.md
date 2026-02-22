---
Title: ConfigGet
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Gets the value of a RedisGears configuration setting.
id: 3dad244b
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: configGet
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/config-get.md
source_repo: https://github.com/redis/docs
title: Config Get
weight: 50
---

```java
public static java.lang.String configGet​(java.lang.String key)
```

Gets the value of a RedisGears [configuration setting]({{< relref "/operate/oss_and_stack/stack-with-enterprise/deprecated-features/triggers-and-functions/Configuration" >}}).

{{<note>}}
You can set configuration values when you load the module or use the `RG.CONFIGSET` command.
{{</note>}}

## Parameters

| Name | Type | Description |
|------|------|-------------|
| key | string | The configuration setting to get |

## Returns

Returns the configuration value of a RedisGears configuration setting.

## Example

```java
GearsBuilder.configGet("ExecutionMaxIdleTime");
```