# Repolex Knowledge Graph of isaacs/github-flavored-markdown

RDF knowledge graph data for [isaacs/github-flavored-markdown](https://github.com/isaacs/github-flavored-markdown), parsed by [repolex](https://repolex.ai).

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
lexq download isaacs/github-flavored-markdown
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d57dd7dc82906e067dfe6bbcf3874300f86f96a5
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── d57dd7dc82906e067dfe6bbcf3874300f86f96a5.nq.gz
│   └── repolex
│       └── d57dd7dc82906e067dfe6bbcf3874300f86f96a5
│           └── chunk-001.nq.gz
├── blob
│   ├── 056fdf280296a30158416469474620681d137106.nq.gz
│   ├── 5d701daba056135235f623a8ddf6a96e1c1e4eea.nq.gz
│   ├── 65954427a2e5dc643ac77d7f4d6c155d7c73529b.nq.gz
│   ├── 6857503c03a367908dc1c50b3f1d151736c26560.nq.gz
│   ├── 6ab83e825a40ea2cdb1881d4972f4459dd1ac217.nq.gz
│   ├── 86c71a3f84c18720a6d3ceb7f2596914be632d11.nq.gz
│   ├── 9263a1ed651779c665bc3b3287cf4b56d5b6c7f5.nq.gz
│   ├── bc5fb07b718e587f11d223d3bd67bf9d9a2f505c.nq.gz
│   ├── c10ad67da114ecdb24e9acd24ccac826715988e9.nq.gz
│   ├── e477c07eb626e991dd09c61d99b2f6c791382a60.nq.gz
│   └── e6e8d7cd6d9a6ab871765f24eed2bb7e6638c175.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── d57dd7dc82906e067dfe6bbcf3874300f86f96a5.nq.gz
├── filetree
│   └── d57dd7dc82906e067dfe6bbcf3874300f86f96a5.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 20 files
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

[isaacs/github-flavored-markdown](https://github.com/isaacs/github-flavored-markdown)

---
*Parsed on 2026-04-14 by [repolex](https://repolex.ai)*
