---
Title: Hashtag
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Returns a string that maps to the current shard.
id: fc831b04
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: hashtag
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/hashtag.md
source_repo: https://github.com/redis/docs
title: Hashtag
weight: 50
---

```java
public static java.lang.String hashtag()
```

Returns a string that maps to the current shard according to the cluster slot mapping.

{{<note>}}
You can use the `hashtag` function when you need to create a key that resides on the current shard. 
{{</note>}}

## Parameters

None

## Returns

Returns a string that maps to the current shard.

## Example

The following example uses the `hashtag` function to calculate the hslot. The string maps to the current shard.

```java
GearsBuilder.execute(
    "SET", 
    String.format("key{%s}", GearsBuilder.hashtag()), 
    "1"
);
```