# Repolex Knowledge Graph of openai/tiktoken

RDF knowledge graph data for [openai/tiktoken](https://github.com/openai/tiktoken), parsed by [repolex](https://repolex.ai).

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
lexq download openai/tiktoken
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 97e49cbadd500b5cc9dbb51a486f0b42e6701bee
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 97e49cbadd500b5cc9dbb51a486f0b42e6701bee.nq.gz
│   └── repolex
│       └── 97e49cbadd500b5cc9dbb51a486f0b42e6701bee
│           └── chunk-001.nq.gz
├── blob
│   ├── 02c9ee20fa186223145da1de759bdf001f1f1e1c.nq.gz
│   ├── 0574e3545019523b44862d5ea7854feb8fa8e649.nq.gz
│   ├── 068c509330047ab0ecc06b2b0854a6999cebd5e4.nq.gz
│   ├── 0832c8ee534b036aa498be66ee32f29870724e92.nq.gz
│   ├── 17c4574f6063e922f83f9fb000c5e1784ac299fe.nq.gz
│   ├── 225fffb87d666004022ee61b577d0bc8ceeba5a8.nq.gz
│   ├── 2a3ebbf1ec63774576a8773ec039480bcc1b5e8d.nq.gz
│   ├── 2be95d262d0f4e3bfabdcfb7efe36aaf28b86f99.nq.gz
│   ├── 317e77560c2b95c2c8a7b3d0d170b2af6de239c9.nq.gz
│   ├── 31b7f8d48ede164f9e94e7619d308a6f56c62f00.nq.gz
│   ├── 49481ae1ac47184607b129274ba72a1d383cbfa0.nq.gz
│   ├── 4d679fac12958f242a2ed0d4459dc41d3a499619.nq.gz
│   ├── 4f36c53743fda5da28b593169dafb65e75cd669d.nq.gz
│   ├── 5bcc31e0d27cdb901b61f12066e268a33880184c.nq.gz
│   ├── 5c669af4293dd09f415d5b9386fe58ddb3e8a212.nq.gz
│   ├── 5e89bfd5790ee5a992cda004e4b3a89e1a4a6aa7.nq.gz
│   ├── 60b62452f6cf1c3f523a39c34d96967f0fc040ee.nq.gz
│   ├── 68cdf7ffa874d666fc05d0b0c9502b9a3df5f9ed.nq.gz
│   ├── 723036ca0bf40747a3b315fda7c54015ba9e1441.nq.gz
│   ├── 7f25b271273bc08dd4e745ad6007accda4cc9546.nq.gz
│   ├── 83ed1036f70d4f419307e8a044a35e163cc35201.nq.gz
│   ├── 8458c1266a18d9e2fd463c78e8d0cbeace55f689.nq.gz
│   ├── ab88a7792c922d707fbb02fdfce251c751799df9.nq.gz
│   ├── dc2eba6699d84489eb1e4aa1d1d13cc82910e801.nq.gz
│   ├── de637cd7b8cd09ecadfc942e682d26e64975632c.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f4bd29f66e68422245bb2a23d7c5912b6148d672.nq.gz
│   ├── f90afc7bec5ec240018a227adb45a053657808c3.nq.gz
│   └── fd1767c765cab1cd07d0f2dc0fe34dd8d24ae9fe.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 97e49cbadd500b5cc9dbb51a486f0b42e6701bee.nq.gz
├── filetree
│   └── 97e49cbadd500b5cc9dbb51a486f0b42e6701bee.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 39 files
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

[openai/tiktoken](https://github.com/openai/tiktoken)

---
*Parsed on 2026-04-10 by [repolex](https://repolex.ai)*
