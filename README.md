# Repolex Knowledge Graph of sphinx-contrib/imageembed

RDF knowledge graph data for [sphinx-contrib/imageembed](https://github.com/sphinx-contrib/imageembed), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/imageembed
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── cf890a5c31239122736e4f47af7e0237c7d1f94c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── cf890a5c31239122736e4f47af7e0237c7d1f94c
│           └── chunk-001.nq.gz
├── blob
│   ├── 04777bc27f1cd2b3b9157bad5e0560d5f925a8ee.nq.gz
│   ├── 10e035b6d4af098bbd151c327b936b10483f5d39.nq.gz
│   ├── 1d45dc6ea30fb622e1c50396757105770b0b9685.nq.gz
│   ├── 20be8f40df9789cb38263b8b32a3e2f3c7265b30.nq.gz
│   ├── 2a4f842c5c4b918c24b86f20ab73ff13577671aa.nq.gz
│   ├── 43e9410848b5cf51dcb8177f1ea541522a078561.nq.gz
│   ├── 4f54037ca91561d2b06492b9f0f15585bee5da08.nq.gz
│   ├── 56ccb236a3d2a50b859c9c85b08f12827433fb56.nq.gz
│   ├── 70516c0fd5b58dde8cf737e885ddf0b44d3c6bfd.nq.gz
│   ├── 79dee1410f8b4d75781f445573023ada3101acd5.nq.gz
│   ├── 9f82debcb94ca84dbf53f2ca4515c11fde7a66e2.nq.gz
│   ├── ae0f862b865ef2f17cee6a962d8fb480d7229488.nq.gz
│   ├── b4b6cba899ea600291381ff3f7ce0cc00f199af9.nq.gz
│   ├── b917a2e7fd3f11723ca9680da7a01aa8083888ba.nq.gz
│   ├── bcf728486fc88f138c7be7533052e5ab258b8e2f.nq.gz
│   ├── c81b92dc9b791a4919ffc08cc2a0aee8b45bace2.nq.gz
│   ├── d20d6cb84c31d0ee09a54906c775f3ed942febf0.nq.gz
│   └── f7fce8751c7cf5519b1dcbeff315939f47ea406f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── cf890a5c31239122736e4f47af7e0237c7d1f94c.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 25 files
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

[sphinx-contrib/imageembed](https://github.com/sphinx-contrib/imageembed)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
