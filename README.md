# Repolex Knowledge Graph of tox-dev/tox-ini-fmt

RDF knowledge graph data for [tox-dev/tox-ini-fmt](https://github.com/tox-dev/tox-ini-fmt), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/tox-ini-fmt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 862ac086ad15d25561e66cc5b4af7db6acafa80a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 862ac086ad15d25561e66cc5b4af7db6acafa80a
│           └── chunk-001.nq.gz
├── blob
│   ├── 017ee30ef7e3c7b859c234ac7d3d1a47ca7b48f7.nq.gz
│   ├── 103386f225c0216e2bb8cfb3d6d87d4e84946107.nq.gz
│   ├── 10853daffaf7654cc0ddf6407ab88b99355771eb.nq.gz
│   ├── 1528f168362b96d5f13149fe62bc264f70761074.nq.gz
│   ├── 17a712ab247c833b73f9d37dfbedfa9b6c233280.nq.gz
│   ├── 24d609a41ef04f8f9fee1545cce62791da87044a.nq.gz
│   ├── 2c57fc93258ca48fa7ee329721c4870f954530a1.nq.gz
│   ├── 364982344fbd94d55705e1f27a9a87abaa255333.nq.gz
│   ├── 416094ba21d8d1f6adb54ceaa924c18e1c20d2bd.nq.gz
│   ├── 452b5fdea56912e61df119dae268f87082461490.nq.gz
│   ├── 5f89818f9e63c2f6829c7706c57f223cdb5bbd38.nq.gz
│   ├── 6176e7643ef2d58bcc0c752e005468c4891bd1c4.nq.gz
│   ├── 62c39012b0a0cdacda6e5ad8b5b38bae4dafc8c0.nq.gz
│   ├── 69d0cfd202c019ca1d5a92d59faf9a1380c61930.nq.gz
│   ├── 6c393a4d4aeddff3fce4e6861311dfd4235a9243.nq.gz
│   ├── 6ce1badb31c74ab6f7c38e4b2a4af0bcdd468649.nq.gz
│   ├── 81a700ccb67854366fed962bd34adabc0c29645f.nq.gz
│   ├── 896be6ddf592b4489f556e7f040902468858eda2.nq.gz
│   ├── 8c728a4ab0d15b25179ee84271dfebfba34fbcad.nq.gz
│   ├── 94497e728f11eb5c0bb4a40f82e9a86184f5a0c0.nq.gz
│   ├── a58a84464429123022bfbd771fb3b833f40e0ca7.nq.gz
│   ├── a8d9ce0dd54a2d26eff1b01bd4390fe4d4175768.nq.gz
│   ├── ad6a69cda323193d5c55f6e2bcfadd870530b717.nq.gz
│   ├── c0fd26bfab64fab7b16f5ee8f66f2eadc728809d.nq.gz
│   ├── c7c1474827fdf6222ff590968f67620be436f393.nq.gz
│   ├── cb77e53aa95b66d14747b42b55e8923f6632ff75.nq.gz
│   ├── cdee51cbd91639531017237345fcaeebc2095dfd.nq.gz
│   ├── d2f2eac278f8e6199b473531af059e3dc248c6ff.nq.gz
│   ├── d2fe5c9ba31492880ad712b60a40b4cf2fcd972d.nq.gz
│   ├── d3b7677d49df85b163344288ed287cfc3730ef80.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e96f30cfb14775648a00766dd9fec03877ee91dc.nq.gz
│   ├── e9cc2d89a5451130b2c1c9150806cdd04d8b60d2.nq.gz
│   └── fdf8e9f760f5fbbdd8c53012f804247e39fb6f26.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 862ac086ad15d25561e66cc5b4af7db6acafa80a.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 42 files
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

[tox-dev/tox-ini-fmt](https://github.com/tox-dev/tox-ini-fmt)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
