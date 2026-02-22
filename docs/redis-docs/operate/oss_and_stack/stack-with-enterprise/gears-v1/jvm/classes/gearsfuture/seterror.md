---
Title: SetError
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Sets an error message.
id: ab08dfeb
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: setError
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsfuture/seterror.md
source_repo: https://github.com/redis/docs
title: Seterror
weight: 50
---

```java
public void setError​(java.lang.String error) 
	throws java.lang.Exception
```

Sets an error message for an asynchronous computation.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| error | string | An error message |

## Returns

None

## Example

```java
GearsFuture<Boolean> f = new GearsFuture<Boolean>();
try {
	f.setError("An error has occurred during asyncForeach");
} catch (Exception e) {
	e.printStackTrace();
}
```