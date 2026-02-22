---
Title: KeysOnlyReader
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Gets key names from a database.
id: 1458af31
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: KeysOnlyReader
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/readers/keysonlyreader.md
source_repo: https://github.com/redis/docs
title: Keysonlyreader
weight: 60
---

The `KeysOnlyReader` only extracts the key names from a database.

## Constructors

You can use one of these constructors to create a new `KeysOnlyReader` object:

```java
public KeysOnlyReader()

public KeysOnlyReader(int scanSize, String pattern)
```

## Parameters

| Name | Type | Default value | Description |
|------|------|---------------|-------------|
| pattern | string | "\*" (match all keys) | Get all keys that match this pattern |
| scanSize | integer | 10000 | The scan command's size limit |

## Output records

Each output record is a string that represents the key's name.

## Examples

Get all keys in the database:

```java
KeysOnlyReader reader = new KeysOnlyReader();
```

Only get keys that start with "user:":

```java
KeysOnlyReader reader = new KeysOnlyReader(1000, "user:*");
```