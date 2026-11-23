# Repolex Knowledge Graph of sfackler/streaming-iterator

RDF knowledge graph data for [sfackler/streaming-iterator](https://github.com/sfackler/streaming-iterator), parsed by [repolex](https://repolex.ai).

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
rlex download sfackler/streaming-iterator
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 69069dc9e46facef6caa79ee48e47420de92633d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 69069dc9e46facef6caa79ee48e47420de92633d.nq.gz
│   └── repolex
│       └── 69069dc9e46facef6caa79ee48e47420de92633d
│           └── chunk-001.nq.gz
├── blob
│   ├── 169f3a6058d7a916e9a4ba17550d2772e30acfe9.nq.gz
│   ├── 3b874ca574de0550d0ee2608988aeb9655940377.nq.gz
│   ├── 4867f3f568b2baa37f00410e0c5686b7261ae6a1.nq.gz
│   ├── 59787cb1b88a11964eedd059cc24ffeaed6b6fe7.nq.gz
│   ├── 8f71f43fee3f78649d238238cbde51e6d7055c82.nq.gz
│   ├── 900b8353f5276fe9f656a1ce4e6bfab5c2e93ff7.nq.gz
│   ├── 9e3651168bde413cf9837157dc58cf4175dcc260.nq.gz
│   ├── e083179d4015d82bde1496bf9b52fa83d9b412b4.nq.gz
│   └── ff7ccd8a1b098cfa4b53aae48f3208be2963296b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 69069dc9e46facef6caa79ee48e47420de92633d.nq.gz
├── filetree
│   └── 69069dc9e46facef6caa79ee48e47420de92633d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 19 files
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

[sfackler/streaming-iterator](https://github.com/sfackler/streaming-iterator)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
