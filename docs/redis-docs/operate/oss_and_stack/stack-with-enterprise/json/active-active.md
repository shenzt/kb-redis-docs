---
Title: Store JSON in Active-Active databases
alwaysopen: false
categories:
- docs
- operate
- stack
confidence: medium
description: JSON support and conflict resolution rules for Active-Active databases.
id: 26c32096
ingested_at: '2026-02-14T15:01:27Z'
linkTitle: Active-Active databases
source_commit: a9ff1a3
source_path: content/operate/oss_and_stack/stack-with-enterprise/json/active-active.md
source_repo: https://github.com/redis/docs
title: Active Active
tocEmbedHeaders: true
weight: 50
---

RedisJSON v2.2 adds support for JSON in [Active-Active Redis Software databases]({{< relref "/operate/rs/databases/active-active" >}}).

The design is based on [A Conflict-Free Replicated JSON Datatype](https://arxiv.org/abs/1608.03960) by Kleppmann and Beresford, but the implementation includes some changes. Several [conflict resolution rule](#conflict-resolution-rules) examples were adapted from this paper as well.

## Create an Active-Active JSON database

To use JSON in an Active-Active database, you must enable JSON during database creation.

Active-Active Redis Cloud databases add JSON by default. See [Create an Active-Active database]({{< relref "/operate/rc/databases/active-active/create-active-active-database#select-capabilities" >}}) in the Redis Cloud documentation for details.

In Redis Software, Active-Active databases created with or upgraded to Redis version 8 or later automatically enable JSON. For earlier Redis versions, you can enable JSON during database creation:

1. See [Create an Active-Active geo-replicated database]({{< relref "/operate/rs/databases/active-active/create" >}}) in the Redis Software documentation for prerequisites and detailed steps.

1. In the **Capabilities** section of the **Create Active-Active database** screen, select **JSON**:

    {{<image filename="images/rs/screenshots/databases/active-active-databases/create-a-a-db-json-search.png" alt="Select JSON from the Capabilities section.">}}

    {{<note>}}
When you select **JSON**, **Search and Query** is also selected by default to allow you to index and query JSON documents. If you do not want to use these additional features, you can clear the **Search and Query** check box.
    {{</note>}}

1. Configure additional database settings.

1. Select **Create**.

{{<embed-md "json-active-active-command-differences.md">}}

{{<embed-md "json-active-active-conflict-resolution.md">}}