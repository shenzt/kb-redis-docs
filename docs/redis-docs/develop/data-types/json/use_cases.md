---
categories:
- docs
- develop
- stack
- oss
- rs
- rc
- oss
- kubernetes
- clients
confidence: medium
description: 'JSON use cases

  '
id: 4d4f701e
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: Use cases
source_commit: a9ff1a3
source_path: content/develop/data-types/json/use_cases.md
source_repo: https://github.com/redis/docs
title: Use cases
weight: 4
---

You can of course use Redis native data structures to store JSON objects, and that's a common practice. For example, you can serialize JSON and save it in a Redis String.

However, Redis JSON provides several benefits over this approach.

**Access and retrieval of subvalues**

With JSON, you can get nested values without having to transmit the entire object over the network. Being able to access sub-objects can lead to greater efficiencies when you're storing large JSON objects in Redis.

**Atomic partial updates**

JSON allows you to atomically run operations like incrementing a value, adding, or removing elements from an array, append strings, and so on. To do the same with a serialized object, you have to retrieve and then reserialize the entire object, which can be expensive and also lack atomicity.

**Indexing and querying**

When you store JSON objects as Redis strings, there's no good way to query those objects. On the other hand, storing these objects as JSON using Redis Open Source lets you index and query them. This capability is provided by the Redis Query Engine.