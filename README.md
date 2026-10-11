# Repolex Knowledge Graph of sphinx-doc/sphinx-autobuild

RDF knowledge graph data for [sphinx-doc/sphinx-autobuild](https://github.com/sphinx-doc/sphinx-autobuild), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-doc/sphinx-autobuild
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c9b7cb990e9bec1c433f737329b92655adc39a9d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c9b7cb990e9bec1c433f737329b92655adc39a9d
│           └── chunk-001.nq.gz
├── blob
│   ├── 1144e1957a318c73971e21fe8f3414be26462d5f.nq.gz
│   ├── 13b6f300ca035e11d884e025361abe1c6ee05c9f.nq.gz
│   ├── 153796349c1c652484cf745df4a1025edcedd8b9.nq.gz
│   ├── 16e19fb29e4c52210bab33aba46d411cd9fa64c9.nq.gz
│   ├── 190b9a136436fc9f146b45ee3406a86e6517484c.nq.gz
│   ├── 22979e91707f60e2ae2ae4b6ed7212606ff6bb22.nq.gz
│   ├── 2a84b71bd12a400ff7c854416c66e76e703d87d3.nq.gz
│   ├── 30cf4d7ac7f0d36c691423778bf0aaa1ae9b2f9f.nq.gz
│   ├── 49a8571e5caec3d2f5c751edf4613203191bb1f8.nq.gz
│   ├── 4dc6edd73c27bb69f5d0d44ea3e7ecc6ccc505c2.nq.gz
│   ├── 4f4a70e10711d23bbaeac0f1c7218121ea8c07ee.nq.gz
│   ├── 5f4470a9e2b81159142299bc238b612acc623124.nq.gz
│   ├── 7c3340e511e8f74cf507b930fdac5f0a2ba7e470.nq.gz
│   ├── 7fda8282142e44f7e763c30311416fa93cc79817.nq.gz
│   ├── 84364ff025b8f0a30356969fbe30a6bb1d5c7390.nq.gz
│   ├── 87c4a9a1f5822d54cfd16873dc85281012f1f9f8.nq.gz
│   ├── 8dd0f9f54c2d69fe5244d3f6ff87933c49f9df7b.nq.gz
│   ├── 9672e6040d48d9ddd931cfedf0bfb2663d8029e6.nq.gz
│   ├── a903f4d0f965d5078b1faa52818f2e71413202c9.nq.gz
│   ├── adcb47b033f5ba14ad491ac17b330080f42457d8.nq.gz
│   ├── ae12575a5c929f72b5cd698faff370574fc8532f.nq.gz
│   ├── b1f058f9cb7083d68ac46763bec30880a8f420c7.nq.gz
│   ├── c32b3f27aabe4522b2eb3aa973c4ef9847eacb0d.nq.gz
│   └── e1e3be485181efe73a5df226439bc9c4862349d4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c9b7cb990e9bec1c433f737329b92655adc39a9d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[sphinx-doc/sphinx-autobuild](https://github.com/sphinx-doc/sphinx-autobuild)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
