# Repolex Knowledge Graph of celery/celery-wheelhouse

RDF knowledge graph data for [celery/celery-wheelhouse](https://github.com/celery/celery-wheelhouse), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download celery/celery-wheelhouse
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fbe99121ac8d0aa50e0f55abeb1f0814c4b098f7
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fbe99121ac8d0aa50e0f55abeb1f0814c4b098f7
│           └── chunk-001.nq.gz
├── blob
│   ├── 06e8ff0498d72347ab6e9b9b277132d63c384e3f.nq.gz
│   ├── 0afbe2e7b0131f25ca29284fd15914835b57cc40.nq.gz
│   ├── 1940b878c6205de740ed42e6984ee0caa58aa360.nq.gz
│   ├── 471ce3eabff260bb71a6b70efee1f200dd72a1c4.nq.gz
│   ├── 676684dddfa147d37f4e95694cac2ffaf8c5c171.nq.gz
│   ├── 9226161cfcf4383951b872d42f5a45c3f5d7bb21.nq.gz
│   ├── 94fca1da0f5197d21b81e6002ac4087dc2a6a2f1.nq.gz
│   ├── bab6cc57a7cb6697416c167cde85a46f38302340.nq.gz
│   ├── bc06b66f9c7eb98027576ce2c90c5bcea17cf566.nq.gz
│   ├── c18ad033d8bc913f2b22fbf6e86764aeb49d5f1b.nq.gz
│   ├── c6a9047550389ada98b370dfe8db741fe9a6c925.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fbe99121ac8d0aa50e0f55abeb1f0814c4b098f7.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 20 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[celery/celery-wheelhouse](https://github.com/celery/celery-wheelhouse)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
