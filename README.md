# kb-redis-docs

Redis 文档知识库 — 预处理后的文档 + Qdrant 快照。

供 [knowledge-base-search](https://github.com/shenzt/knowledge-base-search) 项目作为 git submodule 使用。

## 结构

```
docs/redis-docs/     # 预处理后的 Markdown 文档
snapshots/           # Qdrant collection 快照（Git LFS）
```

## 使用

在主项目中作为 submodule 引入：

```bash
git submodule add git@github.com:shenzt/kb-redis-docs.git kb/kb-redis-docs
```

恢复快照到 Qdrant：

```bash
python scripts/index.py --snapshot-import kb/kb-redis-docs/snapshots/knowledge-base.snapshot
```
