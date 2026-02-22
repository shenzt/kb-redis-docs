---
Title: CallNext
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Calls the next execution that overrides the command or the original command
  itself. A more flexible version of callNextArray.
id: 6dba143a
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: callNext
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/callnext.md
source_repo: https://github.com/redis/docs
title: Callnext
weight: 50
---

```java
public static java.lang.Object callNext(java.lang.String... args)
```

When you override a Redis command with the [`CommandOverrider`]({{< relref "/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/readers/commandoverrider" >}}), use `callNext` to run the next execution that overrides the command or the original command itself.

It is a more flexible version of [`callNextArray`]({{< relref "/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/callNextArray" >}}) since the list of string arguments does not have to be an explicit `String[]` object. This allows function calls like: <nobr>`callNext("key", "value")`.</nobr>

## Parameters

| Name | Type | Description |
|------|------|-------------|
| args | string | Redis command arguments |

## Returns

Returns the command result. It could be a string or an array of strings, depending on the command.

## Examples

Without `String[]`:

```java
GearsBuilder.callNext("restaurant:1", "reviews", "50");
```

With `String[]`:

```java
GearsBuilder.callNext(new String[]{"restaurant:1", "reviews", "50"});
```