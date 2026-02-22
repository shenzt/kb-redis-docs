---
Title: Foreach
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: For each record in the pipe, runs some operations.
id: 8d1f35ec
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: foreach
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/foreach.md
source_repo: https://github.com/redis/docs
title: Foreach
weight: 50
---

```java
public GearsBuilder<T> foreach​(
    gears.operations.ForeachOperation<T> foreach)
```

Defines a set of operations to run for each record in the pipe.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| foreach | ForeachOperation<T> | The set of operations to run for each record |

## Returns

Returns a GearsBuilder object with a new template type.

## Example

For each person hash, add a new full_name field that combines their first and last names:

```java
GearsBuilder.CreateGearsBuilder(reader).foreach(r->{
    String firstName = r.getHashVal().get("first_name");
    String lastName = r.getHashVal().get("last_name");
   	r.getHashVal().put("full_name", firstName + lastName);
}); 
```