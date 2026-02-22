---
Title: RedisJSON 2.2 release notes
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Preview of Active-Active support for JSON.
id: d7cf7abf
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: v2.2 (July 2022)
min-version-db: 6.0.0
min-version-rs: 6.2.12
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/release-notes/redisjson/redisjson-2.2-release-notes.md
source_repo: https://github.com/redis/docs
title: Redisjson 2.2 Release Notes
weight: 98
---

## Requirements

RedisJSON v2.2.0 requires:

- Minimum Redis compatibility version (database): 6.0.0
- Minimum Redis Enterprise Software version (cluster): 6.2.18

## v2.2.0 (July 2022)

A preview of RedisJSON 2.2 is available for Free and Fixed subscription plans in Redis Cloud.

### Headlines

This release adds support for the JSON data structure as a CRDT (Conflict-free Replicated Data Type) when used with Redis Enterprise [Active-Active databases]({{< relref "/operate/oss_and_stack/stack-with-enterprise/json" >}}active-active/).

Active-Active JSON requires Redis Enterprise Software v6.2.12. Contact your account manager or support to access the preview of RedisJSON 2.2. 

### Details

- Enhancements:

  - [#758](https://github.com/RedisJSON/RedisJSON/pull/758) Add support for [`COPY`]({{< relref "/commands/copy" >}})