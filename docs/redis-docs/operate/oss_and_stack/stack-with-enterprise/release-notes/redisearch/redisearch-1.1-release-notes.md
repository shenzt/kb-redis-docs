---
Title: RediSearch 1.1 release notes
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: Aggregations engine.
id: 55480b11
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: v1.1 (April 2018)
min-version-db: 4.0.0
min-version-rs: 5.0.0
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/release-notes/redisearch/redisearch-1.1-release-notes.md
source_repo: https://github.com/redis/docs
title: Redisearch 1.1 Release Notes
weight: 99
---

## Requirements

RediSearch v1.1.0 requires:

- Minimum Redis compatibility version (database): 4.0.0
- Minimum Redis Enterprise Software version (cluster): 5.0.0

## RediSearch 1.1.0 (April 2018)

This is a major version (we almost named it 2.0), which includes months of work, mostly on the brand new aggregations engine.

### Aggregations

Aggregations are a way to process the results of a search query, group, sort and transform them - and extract analytic insights from them. Much like aggregation queries in other databases and search engines, they can be used to create analytics report, or to perform Faceted Search style queries.

#### Example aggregation request

For example, indexing a web-server's logs, we can create report for unique users by hour. Suppose our schema includes the **SORTABLE** fields `timestamp` (Unix-timestamp) and `userId`:

```sh
FT.AGGREGATE idx "*"
   APPLY hour(@timestamp) AS hour
   GROUPBY 1 @hour
      REDUCE COUNT_DISTINCT 1 @userId AS unique_users
   SORTBY 2 @hour ASC
```

See [the full documentation on aggregations for more details](http://redisearch.io/Aggregations/)

### Bug fixes over 1.0.10

- Fixed #[313](https://github.com/RediSearch/RediSearch/issues/313) - removed -mpopcnt compile flag.

- Fixed #[312](https://github.com/RediSearch/RediSearch/issues/312) - crash on highlighting