---
Title: AsyncFilter
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Asynchronously filters out records in the pipe based on a given condition.
id: e69dafb4
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: asyncFilter
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsbuilder/asyncfilter.md
source_repo: https://github.com/redis/docs
title: Asyncfilter
weight: 50
---

```java
public GearsBuilder<T> asyncFilter​(
    gears.operations.AsyncFilterOperation<T> filter)
```

The `asyncFilter` function allows you to use a [`GearsFuture`]({{< relref "/operate/oss_and_stack/stack-with-enterprise/gears-v1/jvm/classes/gearsfuture" >}}) object to asynchronously filter out records in the pipe based on a given condition.

The filter operation should contain a conditional statement and return a boolean for each record:
- If `true`, the record will continue through the pipe. 
- If `false`, it filters out the record.

## Parameters

| Name | Type | Description |
|------|------|-------------|
| filter | AsyncFilterOperation<T> | A function that checks a condition for each record in the pipe. Returns a boolean. |

## Returns

Returns a GearsBuilder object with the same template type as the input builder.

## Example

```java
GearsBuilder.CreateGearsBuilder(reader).map(r->r.getKey()).
	asyncFilter(r->{
		GearsFuture<Boolean> f = new GearsFuture<Boolean>();
		new Thread(new Runnable() {
				
			@Override
			public void run() {
				try {
					Thread.sleep(1);
						
					f.setResult(r.equals("x"));
				} catch (Exception e) {
					e.printStackTrace();
				}					
			}
		}).start();
		return f;
});
```