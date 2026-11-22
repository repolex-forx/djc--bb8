# Repolex Knowledge Graph of djc/bb8

RDF knowledge graph data for [djc/bb8](https://github.com/djc/bb8), parsed by [repolex](https://repolex.ai).

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
rlex download djc/bb8
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 70c96d69bfdff4fbf1cf5a770bf5a02b89426ecb
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 70c96d69bfdff4fbf1cf5a770bf5a02b89426ecb.nq.gz
│   └── repolex
│       └── 70c96d69bfdff4fbf1cf5a770bf5a02b89426ecb
│           └── chunk-001.nq.gz
├── blob
│   ├── 13e2bf9ebf8d0b4563632feca05cd2cef4ecba2f.nq.gz
│   ├── 16c3fb59ccd020a034dee109065a0518e467e062.nq.gz
│   ├── 34b2f7d0db65f003ea6647343ec289fd8d74ca1a.nq.gz
│   ├── 3f4f30f1793f6168415715d9e11629fac1249f01.nq.gz
│   ├── 3fdfb2854e03aa705c37444ca4f0d1328aacc13c.nq.gz
│   ├── 41ffe4b3823cb8ac5f6fc352db1db517a00f191b.nq.gz
│   ├── 4e9155975a12761e84044d311299a0304e179adb.nq.gz
│   ├── 61985017069995979570d10b21cd09eb2d3d22fd.nq.gz
│   ├── 6a80e703c0418d9f73332721a114478f97bae14a.nq.gz
│   ├── 7de5d30f360dc57dfcd63de1b0931318147ac690.nq.gz
│   ├── 8e6ac6c44937565bd146e77b8be0362d146cfa4c.nq.gz
│   ├── 90ee18eeb6dc1544f8510934c1db47966170ed42.nq.gz
│   ├── 947d948a45b525fa0ac219fa8cd3bac2aab9e1ef.nq.gz
│   ├── a949a24624f943f7cc5663a88fc4c569e25b3a1e.nq.gz
│   ├── aab5878fef4296ccf8d24000510d53d670b0b9bb.nq.gz
│   ├── b4abe577316d79b957e2f3d75fab336ad2ecb58e.nq.gz
│   ├── b98e990a2f13a259e600474ad1abedcb78c4b3b4.nq.gz
│   ├── d22911d1e898447f0fe6980b61131beac2a11abd.nq.gz
│   ├── d7ad1d5d922f0f30c26104022dbf98b6c282ce7e.nq.gz
│   ├── df3de748c67f02fe2d4870c8e0038be9a21e9c0b.nq.gz
│   ├── e1936afd58e7d5e4c6b05a7146e7c7585daa5c70.nq.gz
│   └── ea5b60640b01f74e295037aa8a6b7d4ea278a739.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 70c96d69bfdff4fbf1cf5a770bf5a02b89426ecb.nq.gz
├── filetree
│   └── 70c96d69bfdff4fbf1cf5a770bf5a02b89426ecb.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 32 files
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

[djc/bb8](https://github.com/djc/bb8)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
