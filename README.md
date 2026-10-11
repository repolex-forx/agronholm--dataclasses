# Repolex Knowledge Graph of agronholm/dataclasses

RDF knowledge graph data for [agronholm/dataclasses](https://github.com/agronholm/dataclasses), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/dataclasses
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ae712dd993420d43444f188f4525d9bf72f8f219
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ae712dd993420d43444f188f4525d9bf72f8f219
│           └── chunk-001.nq.gz
├── blob
│   ├── 1bfe03202f0cc61032cb4b15e8debe641302726d.nq.gz
│   ├── 31f2ade383ff5705410c156e66cea7031e468666.nq.gz
│   ├── 57c0cd5e97383c0de8f6c34fadf213942ba2aa6e.nq.gz
│   ├── 68fb733e29925dac47a2bc370d8dc68548712eb3.nq.gz
│   ├── 6a430376561ab0208d7ddde76e9fef0dec1a4be4.nq.gz
│   ├── 6ecee8b6e1605dc61cc5613f5f8a016e7bbbc61f.nq.gz
│   ├── 7324060928a404f354290fafce8c17edf0cd409b.nq.gz
│   ├── 87a33f8191d3da0d7aaf84e894ee5301326c5103.nq.gz
│   ├── a09a0dbeb070bbce4100451f2790e6ab21638d23.nq.gz
│   ├── ae068900554c20fcbe614548d49e41b4c7602c36.nq.gz
│   ├── ba34f6b098406249f87cdaa7683bd079ae8727cd.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── d84d48c11f1ece9f1dccf22e8033fd1ee178cadd.nq.gz
│   ├── de8b49469b534115a4a7491fc55ea81b5197202e.nq.gz
│   └── f1fd917ecfc136204e7bbc9f3047fe15e20dd29d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ae712dd993420d43444f188f4525d9bf72f8f219.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 21 files
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

[agronholm/dataclasses](https://github.com/agronholm/dataclasses)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
