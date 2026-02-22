---
Title: Execute
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Runs a Redis command. A more flexible version of executeArray.
id: 5951101c
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: execute
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/execute.md
source_repo: https://github.com/redis/docs
title: Execute
weight: 50
---

```java
public static java.lang.Object execute​(java.lang.String... command)
```

Runs a Redis command, similar to [`executeArray`]({{< relref "/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/executeArray" >}}). However, the `execute` function is more flexible. Unlike `executeArray`, the list of string arguments does not have to be an explicit `String[]` object. It allows function calls like this: <nobr>`execute("SET", "key", "value")`.</nobr>

## Parameters

| Name | Type | Description |
|------|------|-------------|
| command | string | A Redis command |

## Returns

Returns the command result. It could be a string or an array of strings, depending on the command.

## Examples

Without `String[]`:

```java
GearsBuilder.execute("SET", "age:maximum", "100");
```

With `String[]`:

```java
GearsBuilder.execute(new String[]{"SET", "age:maximum", "100"});
```