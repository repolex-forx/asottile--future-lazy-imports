# Repolex Knowledge Graph of asottile/future-lazy-imports

RDF knowledge graph data for [asottile/future-lazy-imports](https://github.com/asottile/future-lazy-imports), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/future-lazy-imports
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── dbde88318526116b30df6592d5582ffaf53ceba4
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── dbde88318526116b30df6592d5582ffaf53ceba4
│           └── chunk-001.nq.gz
├── blob
│   ├── 063b90947572cd45ac98b71234984f7e0c78c4ee.nq.gz
│   ├── 58859313750f2c7a9720940740a5b83bcdf9cdc7.nq.gz
│   ├── 649379c41a072b8adc33d1bf91bf029ac6bf8c09.nq.gz
│   ├── c2e8a5d1bb522dbeb48c312adcc125a96bf93b98.nq.gz
│   ├── c484d49d5bc6539b1b517b686535d60c2b0954e5.nq.gz
│   └── ca1d90ea180858ae143c0e62d920e350d3acc62d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── dbde88318526116b30df6592d5582ffaf53ceba4.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 13 files
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

[asottile/future-lazy-imports](https://github.com/asottile/future-lazy-imports)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
