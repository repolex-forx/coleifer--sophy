# Repolex Knowledge Graph of coleifer/sophy

RDF knowledge graph data for [coleifer/sophy](https://github.com/coleifer/sophy), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/sophy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6ba13fb5eeba8664106830f90e5449dcc6819c47
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6ba13fb5eeba8664106830f90e5449dcc6819c47
│           └── chunk-001.nq.gz
├── blob
│   ├── 07d5fc6d1d68225457ec5a434ec507c940a577e9.nq.gz
│   ├── 1156dae80463fd710d80ea8604d1ba3887d4d7d6.nq.gz
│   ├── 3565a0958ec6b022d11c46f5a27d8262ee405b54.nq.gz
│   ├── 3aef21d5d5693135d8980f08f9f8e3326698f0ef.nq.gz
│   ├── 3c1cc0bfa279e5312873e9450db509f981929ccb.nq.gz
│   ├── 551a5c08de6cc63530c13bf756ca1c35448d197e.nq.gz
│   ├── 58519b61f5a93b06a1266c9ffe52ebe6e60c6e65.nq.gz
│   ├── 5d6375c8b03bd18caec8800a843d348664fd89d0.nq.gz
│   ├── 69c39fd3f5cfe429882ab58573b7d4b891605a84.nq.gz
│   ├── 75ad2d469853061303cbb0c407470a289bd46fab.nq.gz
│   ├── 862a18542c178ed738bdee3ab43628b08b44dec8.nq.gz
│   ├── 92d906595cbf1df47bd1628c1ff80d8b51922ba1.nq.gz
│   ├── a0637b46fe8716b0bde9f41fac121f6e26b77301.nq.gz
│   ├── b202e4ca0613397aca1189f49471479771ea5e7b.nq.gz
│   ├── c96c4828699ca3843db4631f687d7851d533691b.nq.gz
│   ├── ca2568f7d0e4bfcff875e02aeaf794abde3300b1.nq.gz
│   ├── d0af7d225c979ec8b441af52ad30ca2bd85f06b2.nq.gz
│   ├── d6af27343e586eb3fcb1e0eaaa43d639bc970e53.nq.gz
│   └── d90a5f3d4cbd693b2c8b17dc2c4dea1b4df5872c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6ba13fb5eeba8664106830f90e5449dcc6819c47.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 27 files
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

[coleifer/sophy](https://github.com/coleifer/sophy)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
