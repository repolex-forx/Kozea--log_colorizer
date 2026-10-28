# Repolex Knowledge Graph of Kozea/log_colorizer

RDF knowledge graph data for [Kozea/log_colorizer](https://github.com/Kozea/log_colorizer), parsed by [repolex](https://repolex.ai).

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
rlex download Kozea/log_colorizer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 93b7e3489202626fe7f05fe06b5a1ff90af36643
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 93b7e3489202626fe7f05fe06b5a1ff90af36643
│           └── chunk-001.nq.gz
├── blob
│   ├── 21f8ff9741e0f314717128ea8a04d3707d602fd3.nq.gz
│   ├── 254b3bf953db1fcb1791bc36226da9a8c5f4f4f4.nq.gz
│   ├── 3154d1ea26044b476b2b4604c16e07f0f2d26be5.nq.gz
│   ├── 3493dafb04088c32598571d5afeb944229345af7.nq.gz
│   ├── 57648e8cc24238c2645cc74bebc9151fd93b56c4.nq.gz
│   ├── 9a9c4c2cff08701c5639fe64e03a7907b41421d1.nq.gz
│   ├── b01c9215795c40d21d7e9f610b990b733e98a385.nq.gz
│   ├── ca49943f47b93cd5a54c07536989ec7b6a197e63.nq.gz
│   └── d276d523f7979449e31e0d74aadcbea269577abd.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 93b7e3489202626fe7f05fe06b5a1ff90af36643.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 17 files
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

[Kozea/log_colorizer](https://github.com/Kozea/log_colorizer)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
