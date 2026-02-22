---
Title: AsyncMap
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Asynchronously maps records one-to-one.
id: 46faaadf
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: asyncMap
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/asyncmap.md
source_repo: https://github.com/redis/docs
title: Asyncmap
weight: 50
---

```java
public <I extends java.io.Serializable> GearsBuilder<I> asyncMap​(
	gears.operations.AsyncMapOperation<T,​I> mapper)
```

The `asyncMap` function allows you to use a [`GearsFuture`]({{< relref "/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsfuture" >}}) object to asynchronously map each input record in the pipe to an output record, one-to-one.

## Parameters
 
Type parameters:

| Name | Description |
|------|-------------|
| I | The template type of the returned builder |

Function parameters:

| Name | Type | Description |
|------|------|-------------|
| mapper | <nobr>AsyncMapOperation<T,​I></nobr> | For each input record, returns a new output record |

## Returns

Returns a GearsBuilder object with a new template type.

## Example

```java
GearsBuilder.CreateGearsBuilder(reader).
	asyncMap(r->{
		GearsFuture<String> f = new GearsFuture<String>();
		new Thread(new Runnable() {
				
			@Override
			public void run() {
				try {
					Thread.sleep(1);
					
					f.setResult("done");
				} catch (Exception e) {
					e.printStackTrace();
				}					
			}
		}).start();
		return f;
});
```