# Repolex Knowledge Graph of allenai/planteur-benchmark

RDF knowledge graph data for [allenai/planteur-benchmark](https://github.com/allenai/planteur-benchmark), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/planteur-benchmark
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 9f860eef93044cd43bcfc2185fa63a1d09d4b07f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 9f860eef93044cd43bcfc2185fa63a1d09d4b07f
│           └── chunk-001.nq.gz
├── blob
│   ├── 225380a615d5ca22bac730df54cd2312e73cdfd7.nq.gz
│   ├── 451213c169e954964eb9931c1fdad4b34bc19580.nq.gz
│   ├── 45e6fd1193a96bedb791a08c1b8d2bc1ca6e6604.nq.gz
│   ├── 4823ee5539fcb42f25e917c5bbc04ee8e1c05255.nq.gz
│   ├── 4afc257381e1b21d259cc2af9de7243269e582dc.nq.gz
│   ├── 6dad2bd6e1219f280464cfe98a4874450f794e75.nq.gz
│   ├── 7a1277cf03f8ecaf33ff1b1c6ee95d4d2490273d.nq.gz
│   ├── 7f1c2c8895390f3d68f04e9923d500865d40b352.nq.gz
│   ├── 83b6a8601fd55c7a22abae0feeee5d8326613e31.nq.gz
│   ├── 8f281b09010bf58155d2fb23ed239a8fff55913d.nq.gz
│   ├── 912265c450d13bd4f7043ed130764d50c43b6e51.nq.gz
│   ├── a4b7b10b4a58f7289725b4d8d5d4e563a3935df6.nq.gz
│   ├── ad8b0bb505b42eb1d3010c1e5bdab29dcddf3021.nq.gz
│   ├── b458cbeebbc2b5702dc6bab308b17995d4e1473e.nq.gz
│   ├── b7b876178b986f6d2a2c6658f8db71b6014b4d65.nq.gz
│   ├── b87ba94c9b73d5715c7f7df9af4aeef6ef825935.nq.gz
│   ├── bef4afb99981612a35fdac4772d2431e8c836296.nq.gz
│   ├── d06bef169b819f31f82fd25f4e626168e5b190bf.nq.gz
│   ├── d3dc734f4282db14f7a981ad50be7f64afbebe9d.nq.gz
│   ├── da377f96a8d5cb2027dc9dba565153c080edaefa.nq.gz
│   ├── dd3d8c803901890d9b190c173ff664abc7b8a816.nq.gz
│   ├── df0e32416a769a375c95d18adb651576903395ea.nq.gz
│   └── df8e974f7a244a66340365cc75050da7ac8494b5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 9f860eef93044cd43bcfc2185fa63a1d09d4b07f.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 30 files
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

[allenai/planteur-benchmark](https://github.com/allenai/planteur-benchmark)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
