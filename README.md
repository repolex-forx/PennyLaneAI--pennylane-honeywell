# Repolex Knowledge Graph of PennyLaneAI/pennylane-honeywell

RDF knowledge graph data for [PennyLaneAI/pennylane-honeywell](https://github.com/PennyLaneAI/pennylane-honeywell), parsed by [repolex](https://repolex.ai).

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
rlex download PennyLaneAI/pennylane-honeywell
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── a1a6fb2b3edf20a812c4cb418191847cf1fd8eca
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── a1a6fb2b3edf20a812c4cb418191847cf1fd8eca
│           └── chunk-001.nq.gz
├── blob
│   ├── 00bb9552796d5cf6635e326bbb4124220d591e63.nq.gz
│   ├── 046532527ef439aa51b6b13b21fae845e8cee04b.nq.gz
│   ├── 1d1e91613923641d1cb5cd0dbb710095e347ed09.nq.gz
│   ├── 25f581e0fcbea4857c531747ee7037aef89ee423.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 29f81d812f3e768fa89638d1f72920dbfd1413a8.nq.gz
│   ├── 2ad508a2b3acb619d064608d6fee05eb9ff1ce18.nq.gz
│   ├── 2c42946a120a09dcfa99dbc4e6a19e810a4168db.nq.gz
│   ├── 3eec229ac78f2a27d2f5df72cf5585d3afe670ff.nq.gz
│   ├── 4b09ff14bc197c42f2b223b2707cfc4df8400b09.nq.gz
│   ├── 5419c889ae42d6c99cbadf0ad649436e56c6f0ee.nq.gz
│   ├── 62c5927449cef4a705940f2f4d43f860ba0e78f8.nq.gz
│   ├── 65f09236ae1e03177371c1faf2f2ddd3a8be6705.nq.gz
│   ├── 6c37355e34ed2da187b14d54dadecadbe3536fd8.nq.gz
│   ├── 734dc40efffbdeae9dd2e9f1856ec4d32812535f.nq.gz
│   ├── 76e4562457203b03c21aa3c382e9ff3041ef2d56.nq.gz
│   ├── 7751ec5198f96e1a4f29e44bc2bcc9088b31fa0d.nq.gz
│   ├── 819bea392fc20847aca227e62262132ffa8c851c.nq.gz
│   ├── 8385bcb9cbf36415848a4982a5b66bfbf795daec.nq.gz
│   ├── 8a47d1c5e56ab0b9e48bba979270193a528d9d4a.nq.gz
│   ├── a9eadd68ab52356a04a840622283b7741e8e01ff.nq.gz
│   ├── b0fbdf0e313d3fd3138974eabdc3c6f91a78ae25.nq.gz
│   ├── b69348d97da3e161718a410312935f4746b6cb54.nq.gz
│   ├── bde6df1f83c5b4b9a4cf65eaeaa0c9f4891102b8.nq.gz
│   ├── c1abf5ce880a2cf740a44abc033326098d8524f3.nq.gz
│   ├── c51b21f94ad40933b6a7ae315ac80dd9853b347d.nq.gz
│   ├── cf510d1b3ccda19d64692a87b998b1b0b134747a.nq.gz
│   ├── d9a259015802350bb2e9b9ea963b8b95cc1d61f8.nq.gz
│   ├── da55fc50ab854a236ac9c71a7bb395aa9db8f2c9.nq.gz
│   ├── dfa9e9fb010006b2b287dc7f88f5d012537e6b3a.nq.gz
│   ├── e290e049b4bdbc1c6bd59ce9206990bf8471b042.nq.gz
│   ├── e32fec120db97afbb688ad9959ecd287f5382a1c.nq.gz
│   ├── f67bec815653a41d9d6bb7cda75b00f728640fe0.nq.gz
│   ├── f7f33c39c611027b13ecf0b4bb8f5be7346135f9.nq.gz
│   ├── f98f8bbf27874cd4239a8a58924ac2fbca72bf02.nq.gz
│   ├── fd4fc49a32872f02a76b56fbfaa78c435170a001.nq.gz
│   └── ff1622a28d9c9ba7ec8bd373995b6db726f5eba8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── a1a6fb2b3edf20a812c4cb418191847cf1fd8eca.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 45 files
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

[PennyLaneAI/pennylane-honeywell](https://github.com/PennyLaneAI/pennylane-honeywell)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
