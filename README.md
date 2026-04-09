# Repolex Knowledge Graph of pytest-dev/pytest-mock

RDF knowledge graph data for [pytest-dev/pytest-mock](https://github.com/pytest-dev/pytest-mock), parsed by [repolex](https://repolex.ai).

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
lexq download pytest-dev/pytest-mock
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e1b5c62a38c5a05cae614aef3847f240ba50d269
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── e1b5c62a38c5a05cae614aef3847f240ba50d269.nq.gz
│   └── repolex
│       └── e1b5c62a38c5a05cae614aef3847f240ba50d269
│           └── chunk-001.nq.gz
├── blob
│   ├── 05bdbb13dc5255175ce21a68cb5192346263b6cf.nq.gz
│   ├── 125df317d76ee7f2381c4de97c0187882420d504.nq.gz
│   ├── 20273f7e7216d29ed718e432bc23154208fa9e48.nq.gz
│   ├── 281a894aec52074c27cb2f3ba085a4881e11aae1.nq.gz
│   ├── 2daaec50b207a05ba53a359193592711c86a1c4b.nq.gz
│   ├── 469c2508809ac8365ad32bc3848243347662f770.nq.gz
│   ├── 46a5d5b1a4029a07c6f9d5be0fd89cb2859662d2.nq.gz
│   ├── 61a1dc47f951b7c5ad625b7dd5154f7f230a6dab.nq.gz
│   ├── 635d81ff29393acf47ddee31fd5fec2b20adf7b7.nq.gz
│   ├── 6e1ee5d5b8aec4601f7151828373617c3b1004c9.nq.gz
│   ├── 7269d56e40de0e6c7961f81fb722d93b4b82c87e.nq.gz
│   ├── 75fd27afdeb80523c9286831da6376414e573f2e.nq.gz
│   ├── 79d59e1f01eef55a92e3a47d767e7d19adaff71e.nq.gz
│   ├── 80d7c663d23fe4f768949c6fa07ceb66760b4f96.nq.gz
│   ├── 987407c7c3fc9bb04589473181a50478a9766b72.nq.gz
│   ├── a5dd8a4e2fc7b924fce3dd97bd8e0b6ea356380c.nq.gz
│   ├── aff0f0f5da36bdc6e99b65c53eaf5416bcba8f12.nq.gz
│   ├── b4757e4963f846dbbfb323048cf10bb5b1689262.nq.gz
│   ├── be006de9a1ae3b9628e796c74277cd6d61e0a34a.nq.gz
│   ├── c2dd3548734ae43216797cac8e85038c012942d2.nq.gz
│   ├── d1701d5dd16346b2f119d0e7b0f0ad4f9fc3cc77.nq.gz
│   ├── d3a732ac278ba2cc89d2ce6fe8e5d164adf191cb.nq.gz
│   ├── d6b7ef32c8478a48c3994dcadc86837f4371184d.nq.gz
│   ├── dff5d99b53744ac10310220e334379696e7c2943.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── eed47e00df092f73c0a93045e8ab589ad554d25c.nq.gz
│   ├── ef4ea682317e28bfeedbdf45d452d964fdb848ac.nq.gz
│   ├── ef996121333968e1e73b783a103543d26437b461.nq.gz
│   ├── f00d66e1a0b0c9e13c0db9dabec8dbed15201e24.nq.gz
│   ├── f60eb426c9cc7f808b491cb4c0da0ec86ebe9bb4.nq.gz
│   └── f8d07db8827a10de430a75cf96fef473aac531a2.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── e1b5c62a38c5a05cae614aef3847f240ba50d269.nq.gz
├── filetree
│   └── e1b5c62a38c5a05cae614aef3847f240ba50d269.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 41 files
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

[pytest-dev/pytest-mock](https://github.com/pytest-dev/pytest-mock)

---
*Parsed on 2026-04-09 by [repolex](https://repolex.ai)*
