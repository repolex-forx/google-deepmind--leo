# Repolex Knowledge Graph of google-deepmind/leo

RDF knowledge graph data for [google-deepmind/leo](https://github.com/google-deepmind/leo), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/leo
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── de9a0c2a77dd7a42c1986b1eef18d184a86e294a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── de9a0c2a77dd7a42c1986b1eef18d184a86e294a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0ff336b47f8d55cd4f537f54cf5ec6d3902cbd1e.nq.gz
│   ├── 1ce3143f2d3c03d73ff496c0d43938e8e006604a.nq.gz
│   ├── 20cdcf1e94acfb7bca31e76c88972b8605a2b3f7.nq.gz
│   ├── 423a074a59472922dbf5391def720b439d343a8b.nq.gz
│   ├── 7c04b91fd2e4c3f16f5b7876dd2e64b49a916180.nq.gz
│   ├── a749c42b2559f624a894bce841d4da997b45bad7.nq.gz
│   ├── b92b7bf7a121a197b0f31d139413d800dcd9becf.nq.gz
│   ├── dada83ed95717cba9822e160b6ce491a9b29c4bb.nq.gz
│   └── f9b04dacb7f933119d2e716e96ca05154d47b8de.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── de9a0c2a77dd7a42c1986b1eef18d184a86e294a.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 16 files
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

[google-deepmind/leo](https://github.com/google-deepmind/leo)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
