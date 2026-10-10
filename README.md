# Repolex Knowledge Graph of marshmallow-code/marshmallow-sqlalchemy

RDF knowledge graph data for [marshmallow-code/marshmallow-sqlalchemy](https://github.com/marshmallow-code/marshmallow-sqlalchemy), parsed by [repolex](https://repolex.ai).

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
rlex download marshmallow-code/marshmallow-sqlalchemy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a04b4a8bf4200a50bc40b688f0d7949e42d0fd1e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a04b4a8bf4200a50bc40b688f0d7949e42d0fd1e
│           └── chunk-001.nq.gz
├── blob
│   ├── 1430d36b3dc50a0780b641c5a85967db3e2caebe.nq.gz
│   ├── 228c271554cdb10ec8f5fa00af116794f67bd912.nq.gz
│   ├── 260d67ff65e242df45c9f8cc5521fff10603bf16.nq.gz
│   ├── 2b7c6703e1d8e0bfcc7dba86f7b925b95e8af139.nq.gz
│   ├── 2b99ff8dfb9cd6a09c8cd20038b2ff59d3f614de.nq.gz
│   ├── 35c6f5449af69098b16ea61d8de2277b24562cb4.nq.gz
│   ├── 38531ad826ecd90260d1448c31d2ee6b45cd98fc.nq.gz
│   ├── 386e89c7d7779b4d5ad8719d7814c59e80d5663c.nq.gz
│   ├── 3c0dee57e4f66dd150e965fd2b597954b332fa15.nq.gz
│   ├── 41314db9c38431cd1513a0a47fd083cd70401270.nq.gz
│   ├── 509090666fa61f5c095b62e78adadf2d1ca7b142.nq.gz
│   ├── 5156479c46c663fccbec2f5786eab962de684449.nq.gz
│   ├── 5928069dd32514c4dbea9062b1c1bc1af7a9f076.nq.gz
│   ├── 5b5be9ddc317badd88ab970282ac4667190aeca7.nq.gz
│   ├── 64c3fc113a0231f9ea2f631f75aaddae087b0e95.nq.gz
│   ├── 6c0058da70a328d718b3f17d1066309991cc669a.nq.gz
│   ├── 80563bf8f787c910af98ae574bca54bceece2f57.nq.gz
│   ├── 842c0cd3a7404287d1a9e26a165b023fc346391c.nq.gz
│   ├── 893e0df82f4bee9666705b2562c78cdc8078f8d6.nq.gz
│   ├── 91da19127b03b24814239ff131a52a9e9f4be5e4.nq.gz
│   ├── 92ec2bb600a1e1f3ad8666d355b485b696332790.nq.gz
│   ├── a327f6c153b7a2674604aa1680aaa3ed8e6f49bb.nq.gz
│   ├── b20df7cab259cfce3d02bd8da515ce65870612b7.nq.gz
│   ├── d1ece785041792651335ae8343c1efa819d01377.nq.gz
│   ├── db1d978a52b34ffd602f7f3bdf7b1f251bf03de9.nq.gz
│   ├── dc2127a9cee268f4b11c9c1b0017454cd4276af4.nq.gz
│   ├── dd467cc905fed7240299aa6e17f176e4edd149b0.nq.gz
│   ├── e122f914a87b277e565fc9567af1a7545ec9872b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ea486477436bce194d59da33c5ba3026f0d3b472.nq.gz
│   ├── f1afdf595a879a94d1f40531aa6a2a0fda10d92f.nq.gz
│   ├── f40ce91be5fa3ae6afbf5457462f0d87000e4f1b.nq.gz
│   └── fa07e9e9a0a642238290e1e531c015e7134401fa.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a04b4a8bf4200a50bc40b688f0d7949e42d0fd1e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 41 files
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

[marshmallow-code/marshmallow-sqlalchemy](https://github.com/marshmallow-code/marshmallow-sqlalchemy)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
