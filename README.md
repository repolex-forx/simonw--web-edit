# Repolex Knowledge Graph of simonw/web-edit

RDF knowledge graph data for [simonw/web-edit](https://github.com/simonw/web-edit), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/web-edit
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 0a24583937e16a8ed8391a7dfa36640b55c5729b
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 0a24583937e16a8ed8391a7dfa36640b55c5729b
│           └── chunk-001.nq.gz
├── blob
│   ├── 03f95a03d6edc062f4cf3da4396a6d113bc1d1a1.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2835b4cdc961a96fd11c7023eb65f9214f5fa2f2.nq.gz
│   ├── 2e66ba6af3fe0212c1096169a45606063c490936.nq.gz
│   ├── 33e2b6821295af43f959ffc0da3d72a2e1ba6948.nq.gz
│   ├── 36d251b6431aa9fd2552f2378ce0cd1133754be0.nq.gz
│   ├── 3ce4deaa552c8822d8c9ee603ed69320d28bd437.nq.gz
│   ├── 413b21755c5108b72fe94cd0925b796c834e8b6c.nq.gz
│   ├── 636b09edc4c55db72dead9cd274ed7908190a5ce.nq.gz
│   ├── 7c961034f0ad4df7abb1c8daab788bc508fc9171.nq.gz
│   ├── 89fda9a463566126638868f6cdb7a11ef1b38fd7.nq.gz
│   ├── 93f81f1bfe23a4c1465b169b44e708e78ec72b4d.nq.gz
│   ├── 98bb42940b6580e0e162875e802fbf20e88430f5.nq.gz
│   ├── 98dcca0c2836ae53d67260be8a5431b855e461bb.nq.gz
│   ├── a9bb68ac9c6b51a1e0c86731e82228b7a0d28ce0.nq.gz
│   ├── aaaa6c97a816758acc5a3f9a305e7c23a4873366.nq.gz
│   ├── ad34b5d42a27b7deac7f1cf07e46880f5e8b7c6b.nq.gz
│   ├── aee7d8ab041cd703eb0fb30eef6fc2883d2d73c6.nq.gz
│   ├── b4b86475d86f9420d7eac9488e663f97d2c8dba5.nq.gz
│   ├── b6227e7e08ed74ff517d0bbbb9a0fed1996bf82a.nq.gz
│   ├── b91400287a1bae07e0742eddf41c463c927d277c.nq.gz
│   ├── ba010c11b4c8601233f0d727284504f6afc2e672.nq.gz
│   ├── cafe8b8d068b623fc5d0e22ebd834d0ff55c5e73.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── efa43aaa668357171169d49f03b82f2078adf872.nq.gz
│   └── f9cf6ef049ef1ac250ba2e1607210543b5afa396.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 0a24583937e16a8ed8391a7dfa36640b55c5729b.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 34 files
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

[simonw/web-edit](https://github.com/simonw/web-edit)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
