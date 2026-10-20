# Repolex Knowledge Graph of klen/marshmallow-peewee

RDF knowledge graph data for [klen/marshmallow-peewee](https://github.com/klen/marshmallow-peewee), parsed by [repolex](https://repolex.ai).

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
rlex download klen/marshmallow-peewee
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 010c7d6c6945a8a18aa13f8244727079ee83ccf3
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 010c7d6c6945a8a18aa13f8244727079ee83ccf3
│           └── chunk-001.nq.gz
├── blob
│   ├── 04a0caf0083929ab66637582e2107bff67b81da2.nq.gz
│   ├── 17c7be657d493d5b89a33662d333048d6c0fd951.nq.gz
│   ├── 26aa047e53427f8c81bdebb08929998066029cdf.nq.gz
│   ├── 2f899abd23c109c3937ecdd66ebd49c783190f45.nq.gz
│   ├── 3762e4182d51d550390af8e0923f07ea5ef7ba0e.nq.gz
│   ├── 41d4cb1a1da6059b06e833521ea16646bcd75f57.nq.gz
│   ├── 4257bdd5e2b6be5aaac5372ba6e9a6a54b81456c.nq.gz
│   ├── 460e258d9db9fc868683524476698e3740a1c019.nq.gz
│   ├── 5788e730d46b0c4341df78c9ceb5b58822aca0c2.nq.gz
│   ├── 6b2e6a8470edc1ea6fef9b74c44592b1ca929d47.nq.gz
│   ├── 8efd9e77f63f9b2e47ebf90ba22c595dc890b091.nq.gz
│   ├── a854dd94a785f134f19c3e252dcfb8d48e1c2188.nq.gz
│   ├── ab98a33b1b7b768dca9c21e644118e4fb27ece2d.nq.gz
│   ├── b21b563e9f6975d27ef19ece049ac6e66903c53f.nq.gz
│   ├── ba10c226d67fa393182fabad7d240ea1e730d59d.nq.gz
│   ├── d063574d7f82f53b73cccb989fc0dc1b523251e9.nq.gz
│   ├── d59a211e6a03ffcb5defe7bbcca956e31cdbaaba.nq.gz
│   ├── d857711bde4eaaff2d0c7222a6de587f6b763a24.nq.gz
│   ├── dd3eed1767d8d38fca0756d05d95c7f217d2e4c2.nq.gz
│   ├── e36328d6047f50240b8a5427b3414099769b75f5.nq.gz
│   ├── e49e804710bfd37b6823bf4702c32b7dde3a6cb2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f7e22616a79304f4aab9ec0442d13e5ba9607313.nq.gz
│   └── fe2abd7c199b001839adb9c6cddbc6d9109988ea.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 010c7d6c6945a8a18aa13f8244727079ee83ccf3.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 32 files
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

[klen/marshmallow-peewee](https://github.com/klen/marshmallow-peewee)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
