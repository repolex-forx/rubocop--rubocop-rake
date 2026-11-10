# Repolex Knowledge Graph of rubocop/rubocop-rake

RDF knowledge graph data for [rubocop/rubocop-rake](https://github.com/rubocop/rubocop-rake), parsed by [repolex](https://repolex.ai).

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
rlex download rubocop/rubocop-rake
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 890aabc9708da938d54f954cc8393732e86b8891
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 890aabc9708da938d54f954cc8393732e86b8891
│           └── chunk-001.nq.gz
├── blob
│   ├── 094a49d28738f696770c6c7bb3d53c62b3bbfb45.nq.gz
│   ├── 1346917bdb82cc06172d4d4c7efa3d29e069097c.nq.gz
│   ├── 13a221ec2b6f27e0ffa9f4f71a36b02cb02f8e9d.nq.gz
│   ├── 34c5164d9b56c7d528f061c97f2d2fe02c834bdd.nq.gz
│   ├── 3820450d9602927ed678dc312ac346a36041d60a.nq.gz
│   ├── 425572cca1bacef7672a505a4b2e3861d9c9fd5a.nq.gz
│   ├── 48944ea5f0e0ad71ba93487319e7624953a5c4e3.nq.gz
│   ├── 4f0b460cc3636f47feec86a42fbf3c6edb486b37.nq.gz
│   ├── 519bad97e0902dc764d0e1d38fc5ebf742b1550b.nq.gz
│   ├── 5f4f053dcfc0eea233cd564374fe90e24f2c4bdf.nq.gz
│   ├── 60d75f50310f9072deff73858ed89141fa7d05b5.nq.gz
│   ├── 670c81ccc5e9a87786f86fe0174c83953215801a.nq.gz
│   ├── 67cebe91ecab7e70f4c4d4c95a8488dac6e5909b.nq.gz
│   ├── 7123cb3954330222ff55a0afa369da6256c1f63b.nq.gz
│   ├── 739e79fe6edb47c2328bdebf8f38edca701cd0b6.nq.gz
│   ├── 744df14f5e70ef7b096d3437dd7f980a7f51b240.nq.gz
│   ├── 75a224ad8a77987f90fed0e804a8c25f8fbca60e.nq.gz
│   ├── 7bc9253390894fe885c9fbda5b0d4efd6a74a327.nq.gz
│   ├── 812b1cfab670e8fdce19d2d4e26c7a950bb015b3.nq.gz
│   ├── 857faa991f1c57ed368b6361bbab2342888db6b8.nq.gz
│   ├── 88b84c4d18f9da25befea3639a2a7dc0c227684a.nq.gz
│   ├── 90cbd4884cf585d620ef853e79776426e5df3d4b.nq.gz
│   ├── 9653cf9432e9046bba5165e0e7d50633e6a47c03.nq.gz
│   ├── 9d6589e39cae15512147f795b4e0640e51897a75.nq.gz
│   ├── a25cb9c441e8b5ba0695049fff2d308a85986a82.nq.gz
│   ├── ac4b277d418c8ecf4e4bec5be10d3cf50c89b393.nq.gz
│   ├── acce65806197fc107a5fbf66bd47c51718a71196.nq.gz
│   ├── ae1ec23ddc7ec8e1c6822418d921d60b29769159.nq.gz
│   ├── af806293efe1db7682aecf265bd9747dc681ee55.nq.gz
│   ├── b5bf16f2de069d0fda096b101d3a79c08d42b912.nq.gz
│   ├── c8b1737495094dbaf3d3eb594d259b1f910b40bc.nq.gz
│   ├── cf38c474e844f3315019237489e55e4aea966ec6.nq.gz
│   ├── d719116ad092d2ad3108f8724d83c0050639cf66.nq.gz
│   ├── dce67d860af47a4eb630117ce03624bae45dcf26.nq.gz
│   ├── e13ee1fb4fa5c174bb25899b844308ebac7b895c.nq.gz
│   ├── f193878afb2cb19577783381f296aa7324c8858b.nq.gz
│   ├── f1c28dec8ac089043a8f4a293d9d9d52b91d0a00.nq.gz
│   ├── f213c31d1cd9bf2af40375f6880dbecb271c5081.nq.gz
│   └── ffbd08e426a3b37287146f661b747f1dac7e9f2d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 890aabc9708da938d54f954cc8393732e86b8891.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 47 files
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

[rubocop/rubocop-rake](https://github.com/rubocop/rubocop-rake)

---
*Parsed on 2026-11-10 by [repolex](https://repolex.ai)*
