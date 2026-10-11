# Repolex Knowledge Graph of psf/sboms-for-python-packages

RDF knowledge graph data for [psf/sboms-for-python-packages](https://github.com/psf/sboms-for-python-packages), parsed by [repolex](https://repolex.ai).

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
rlex download psf/sboms-for-python-packages
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a399bc2f1e948c043b92db9d125aface091cbafa
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a399bc2f1e948c043b92db9d125aface091cbafa
│           └── chunk-001.nq.gz
├── blob
│   ├── 09dd6f8a47b3b045be2fcef94796f85e24add0db.nq.gz
│   ├── 0e259d42c996742e9e3cba14c677129b2c1b6311.nq.gz
│   ├── 22e15d1f7d2ef831f984594a51e1383eda88be1b.nq.gz
│   ├── 24b3277cc088229f04b1ed28cea57d1358091416.nq.gz
│   ├── 3758c32599d5da53bbeee342c7cf301b10444012.nq.gz
│   ├── 42ff1f28a6b697de9841918f9dd9a689a192d9b8.nq.gz
│   ├── 49fe68836b69f3469445f2a1b4e7976365f1741d.nq.gz
│   ├── 4bea3785dc822b69a7c6afa468ae5b688ca81929.nq.gz
│   ├── 6723ff9ddf9e4caa5d25a0086f26c55bedc6a895.nq.gz
│   ├── 78e90830633cbf9378622e9be4dfe9a836393975.nq.gz
│   ├── 7dc0ec5988c44d46d1e8cc106e48e2e744394f3c.nq.gz
│   ├── 8604f70f1f56b39f8e9429548e84507fa906a673.nq.gz
│   ├── 96df6753cd3802213965a24150af12b692abc0b7.nq.gz
│   ├── 9e2a58a1ec7900c990131297704c7f8de01adbfe.nq.gz
│   ├── a145822a72c72e00b5bb14701c94a809cbfd9012.nq.gz
│   ├── a3b303ef4fc1597e66a87aed4424d6f129673623.nq.gz
│   ├── b3e0110bfd688a6cab46e5918ac9ee905cbba94a.nq.gz
│   ├── b3fac2cdff3625482fd73b288006a8aa9d6e087e.nq.gz
│   ├── b8da36ac0f2fb31868aeb86787765e754577fef7.nq.gz
│   ├── bb6ee259eaa8bb64faa8be2c02b5cf3af02a25d0.nq.gz
│   ├── c31fa199bd4fe8096ee1f7443064ea94a6fc9410.nq.gz
│   ├── c382703a7489af6c6c74992c9ddcb09d94926a51.nq.gz
│   ├── cf9559417afbaa7d689b23c7b7667f85a405fd96.nq.gz
│   ├── e6dd2dfbccfd086a81562efda33ebae82eebbc0c.nq.gz
│   ├── ea57b5019d1df3e50b919b1894e845a6328dc191.nq.gz
│   ├── ef1fc4c9ce81c23f2a1b64aa3ec91c079eac8e80.nq.gz
│   ├── f51897b49460c5cc937b1bf7720dbfd7aa76cf45.nq.gz
│   ├── f7098a4ff43609bb7ca8dbd2d6ed3c2c113cb61f.nq.gz
│   ├── f8573cec6385b025f3bbea3cecad5f5b2f550089.nq.gz
│   ├── f8f51cad70327c95570229d3d946491b90f8507d.nq.gz
│   └── fa439043262864c812e0eff585be1d4456fed6d3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a399bc2f1e948c043b92db9d125aface091cbafa.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[psf/sboms-for-python-packages](https://github.com/psf/sboms-for-python-packages)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
