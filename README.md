# Repolex Knowledge Graph of block/.github

RDF knowledge graph data for [block/.github](https://github.com/block/.github), parsed by [repolex](https://repolex.ai).

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
rlex download block/.github
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 51ce56759b8daf7b43bbe33bff6dcbeb4c2eda96
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 51ce56759b8daf7b43bbe33bff6dcbeb4c2eda96.nq.gz
│   └── repolex
│       └── 51ce56759b8daf7b43bbe33bff6dcbeb4c2eda96
│           └── chunk-001.nq.gz
├── blob
│   ├── 05aebd07ba8c49dfb7e310de4ec07d5f449b93f3.nq.gz
│   ├── 38a8704065c73eb6441deb835f516a3221a281dd.nq.gz
│   ├── aa2f1a03131611ba349c0df1b737341d9626806a.nq.gz
│   ├── ab6682c5277626e6f1c5460d8e78135b77f16f75.nq.gz
│   ├── b72282eb84b7f52004c29886afe3d63fccd28011.nq.gz
│   └── b8e821860d83644bfbb205068e569da6ace84d48.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 51ce56759b8daf7b43bbe33bff6dcbeb4c2eda96.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 14 files
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

[block/.github](https://github.com/block/.github)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
