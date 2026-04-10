# Repolex Knowledge Graph of expressjs/vhost

RDF knowledge graph data for [expressjs/vhost](https://github.com/expressjs/vhost), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download expressjs/vhost
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 2dff3f358265380328067d1ffc91e342b665f586
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 2dff3f358265380328067d1ffc91e342b665f586.nq.gz
│   └── repolex
│       └── 2dff3f358265380328067d1ffc91e342b665f586
│           └── chunk-001.nq.gz
├── blob
│   ├── 3c26fab6d8922012e9971d36c9bf5dda476e9cc6.nq.gz
│   ├── 3cd27afdb6d88edd8bd83ee7adbc7313084a48e7.nq.gz
│   ├── 7f77e502600ff170220a48e5eb01eb52ccd2fbfc.nq.gz
│   ├── 803d78d33377644dc06a2075aea983899ee9761f.nq.gz
│   ├── 82843eb17fd0f08a5d25d171f5a7ada0ef20f713.nq.gz
│   ├── b94cbbd9b709877a8d99406bc6487236745e7e85.nq.gz
│   ├── e4f87180fefc62a5bb8359ec2c83428d437acdc1.nq.gz
│   └── f3538757770ef482522250624c0c9edb5f30e281.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 2dff3f358265380328067d1ffc91e342b665f586.nq.gz
├── filetree
│   └── 2dff3f358265380328067d1ffc91e342b665f586.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 18 files
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

## Source repository

[expressjs/vhost](https://github.com/expressjs/vhost)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
