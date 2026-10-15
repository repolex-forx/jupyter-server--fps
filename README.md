# Repolex Knowledge Graph of jupyter-server/fps

RDF knowledge graph data for [jupyter-server/fps](https://github.com/jupyter-server/fps), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter-server/fps
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b4e2d1f44f1d2e3826a79a8f587c816d86c5941e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b4e2d1f44f1d2e3826a79a8f587c816d86c5941e
│           └── chunk-001.nq.gz
├── blob
│   ├── 05fc0846d4973234667d8a7905e964f5a624c911.nq.gz
│   ├── 0f68ad2f0599da707d22880632a55c42d33d2ef8.nq.gz
│   ├── 1d560c6a321d80952759e2899a012ef6c91dfe80.nq.gz
│   ├── 201f8123d76d5f6e51935355c6abab89867c528a.nq.gz
│   ├── 27068ebfb7d9291f5f4c522d71015449a6d16edf.nq.gz
│   ├── 2b8d7502471e583a9c7079a294d14303664ab2a5.nq.gz
│   ├── 306b0982ab62ebc92e4aec21db0be80e44fa3475.nq.gz
│   ├── 39591f46e1d032c3c52fdd6710a6eb20eac9191c.nq.gz
│   ├── 3a3e4ada4f7804dd612a0d2444699cf422492226.nq.gz
│   ├── 42bf9613b8075545160adb8cd37b107d95eea6d0.nq.gz
│   ├── 4c594ba1e31f319b8028c7e86e0220954c0271aa.nq.gz
│   ├── 51d27ac05f67efdb36ae70b4e9975908ff685cc3.nq.gz
│   ├── 55e4726f134ea2b1e2087b7a2c4fad018e36adbd.nq.gz
│   ├── 5a3226ffad8031eef986cb86a171f4218aba9442.nq.gz
│   ├── 5ab855e9f2369db35ea806ee5dba3e2b8dcc820d.nq.gz
│   ├── 5aff6e6a7b2d8d963e123dd9c7b0f56ede1dc00a.nq.gz
│   ├── 67ecd988641591ea0ab8cda684d8ff78e9157810.nq.gz
│   ├── 6d51feffce57cd4019d694edcd89c1ca11065526.nq.gz
│   ├── 7dd7a8a00f5ba2d98127a3e5c40340a84736c625.nq.gz
│   ├── 88edae773a08e62718631d588546b9bae286a1c2.nq.gz
│   ├── 9dab837433d012aad751c16e29ae820fc7bcbc81.nq.gz
│   ├── a18144fe52d10831c423145ba25c58520419cfe6.nq.gz
│   ├── a188787f84cd500921dd8a37bea7ed311d2bc806.nq.gz
│   ├── ab255087431725b5ae37c0fe279a6572f1064252.nq.gz
│   ├── acc8b6052fcfda3cf9b6cc39d69b5eb140d55f1d.nq.gz
│   ├── b056811a14f42d11044556dc66dace0e1491aa2e.nq.gz
│   ├── b935bcd3da9312c928b798cbf95cbb0e6ad6db40.nq.gz
│   ├── c0c2be9b7f5756d9bc7d9e20e213068e2abeb7e5.nq.gz
│   ├── c1e64c12ed89689947b9ba34c61b10824b9b4bdc.nq.gz
│   ├── c7f93a35653d6aa0fc63a27c7619e638296eb883.nq.gz
│   ├── c9db729e1643321bf61473f041b3cf7d6eed31f4.nq.gz
│   ├── cf7e097b21beed2c242b4d73dbcb1956e63f75a3.nq.gz
│   ├── d2ac44a5d69616f237bb8f5957887200873a03f5.nq.gz
│   ├── d638c05fd7f8deb622f87d8f1f174bc102751c05.nq.gz
│   ├── d65d0d80d18983558d4729fb4c6e6fb19f1fc590.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── fd5bda1d2df845655c8d85d9a52d958be7ac722a.nq.gz
│   └── fdeccc7fb08ae55e480e462220f1fc8b7e87392f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b4e2d1f44f1d2e3826a79a8f587c816d86c5941e.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[jupyter-server/fps](https://github.com/jupyter-server/fps)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
