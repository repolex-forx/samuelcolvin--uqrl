# Repolex Knowledge Graph of samuelcolvin/uqrl

RDF knowledge graph data for [samuelcolvin/uqrl](https://github.com/samuelcolvin/uqrl), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/uqrl
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e10907542ed81e620864b638b44230c86d5a2342
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e10907542ed81e620864b638b44230c86d5a2342
│           └── chunk-001.nq.gz
├── blob
│   ├── 0dfd5ccc6d592268a4478942911dab091d42e7fe.nq.gz
│   ├── 13d36323a2f207c9212e434151240d33327959c0.nq.gz
│   ├── 1af3f4c6e8d43d824416a3ca8a1670400e00c26a.nq.gz
│   ├── 2246c2c268c677f05a6d2884faad9bc74fb53611.nq.gz
│   ├── 658794a3aa6ddea083370494c1c103dfdde3e8fc.nq.gz
│   ├── 744d0f670a36f22d9f4e212c36baf2ab7dc738d5.nq.gz
│   ├── a7a79d2e53e9b1e1a85c765b534de1fd45c832e7.nq.gz
│   ├── d0d0a37307bb45d13fe4b45cd256c357a97c49d2.nq.gz
│   └── ed105194af0d51f4fd1af036e3a274068db6ab0e.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e10907542ed81e620864b638b44230c86d5a2342.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 15 files
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

[samuelcolvin/uqrl](https://github.com/samuelcolvin/uqrl)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
