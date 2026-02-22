---
Title: SetResult
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Sets a computation to run asynchronously.
id: e12db60e
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: setResult
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsfuture/setresult.md
source_repo: https://github.com/redis/docs
title: Setresult
weight: 50
---

```java
public void setResult​(I result) 
	throws java.lang.Exception
```

Sets a computation to run asynchronously.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| result | template type I | The result of a computation |

## Returns

None

## Example

```java
GearsBuilder.CreateGearsBuilder(reader).map(r->r.getKey()).
	asyncFilter(r->{
		GearsFuture<Boolean> f = new GearsFuture<Boolean>();
		try {
			f.setResult(r.equals("x"));	
		} catch (Exception e) {
			e.printStackTrace();
		}			
		return f;
});
```