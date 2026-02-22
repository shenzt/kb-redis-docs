---
Title: RedisBloom 1.0 release notes
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: First GA release of RedisBloom.
id: 475c189e
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: v1.0 (September 2017)
min-version-db: 4.0.0
min-version-rs: 5.0.0
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/release-notes/redisbloom/redisbloom-1.0-release-notes.md
source_repo: https://github.com/redis/docs
title: Redisbloom 1.0 Release Notes
weight: 100
---

## Requirements

RedisBloom v1.0.3 requires:

- Minimum Redis compatibility version (database): 4.0
- Minimum Redis Enterprise Software version (cluster): 5.0

## v1.0.3 (December 2017)

This contains a single fix, issue #[19](https://github.com/RedisBloom/RedisBloom/issues/19).

From this version onwards, `EXISTS`/`MEXISTS` returns 0 if the (Redis) key does not exist in the database.  Earlier versions returned an error.

## v1.0.2 (November 2017)

This fixes a build issue (fixed s3 config in circle yaml).

## v1.0.0 (September 2017)

This is the first GA release of ReBloom.