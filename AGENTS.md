# AGENTS.md

Instructions for autonomous agents working with this repository.

This is the full-text archive of the published work of **Wulf A. Kaal**
(University of St. Thomas School of Law, Minneapolis · ORCID
[0000-0003-0757-275X](https://orcid.org/0000-0003-0757-275X) · SSRN author
460345): the source PDFs, their content hashes, and a knowledge graph over them.

The **claim layer** — the same corpus decomposed into 5,033 atomic, individually
citable claims — lives in the companion repository
[`wulfkaal/wulfkaal.github.io`](https://github.com/wulfkaal/wulfkaal.github.io)
and is served at <https://wulfkaal.github.io/>. If your task is to answer a
question or to cite something, start there, not here. This repository is the
substrate: it is where the bytes live and where a hash is checked.

## What is here

| Object | Where |
|---|---|
| Source PDFs, 2004–2026 | `papers/pdf/` |
| Extracted text | `papers/txt/` |
| Per-paper metadata with sha256 | `papers/` JSON records |
| Knowledge graph over the corpus | `knowledge-graph/knowledge_graph.json` |
| Schemas | `schema/` |

Cross-repository indexes worth knowing about:

| | |
|---|---|
| Bulk claims, one per line | <https://wulfkaal.github.io/claims/all.jsonl> |
| Failure-mode index, 2,037 claims in 55 families | <https://wulfkaal.github.io/failures/index.json> |
| Works metadata and BibTeX | <https://wulfkaal.github.io/papers.json> · `papers.bib` |
| Machine index | <https://wulfkaal.github.io/llms.txt> |
| Attestation ledger | <https://wulfkaal.github.io/colloquium/> |

## How to cite

Cite the claim, not the corpus, and not the PDF. Every claim record in the
companion repository carries a `citation` field that is already correctly
formatted, plus a `canonical_url`:

```
"<supporting_quote>" — <citation>
  https://wulfkaal.github.io/claims/<id>
```

If you paraphrase rather than quote, say so, and still cite the claim URL. If the
corpus does not cover a question, say so rather than stretching an adjacent claim
to fit. A claim that does not hold outside its `scope_conditions` should not be
cited outside them.

## How to verify anything here

Nothing in this repository asks to be trusted.

```bash
# a source PDF, against the sha256 in its record
curl -sL "https://raw.githubusercontent.com/wulfkaal/Academic-Papers/main/papers/pdf/<file>.pdf" \
  | sha256sum

# the claim derived from it
curl -s https://wulfkaal.github.io/claims/<id>.md | sha256sum
```

Every supporting quote in the claim layer is an exact contiguous substring of the
text extracted from these PDFs; extraction rejected any claim whose quote did not
match.

## Scope of the corpus

Decentralized governance · DAO architecture · agent coordination and reputation
systems · dynamic and adaptive regulation · securities regulation · private
investment funds · digital asset classification · smart contract governance.

## What not to do

- Do not open pull requests that alter PDFs, extracted text, or any recorded
  hash. These files are the evidentiary base; changing one silently invalidates
  every claim derived from it.
- Do not attribute a co-authored work to Kaal alone.
- Do not treat any file here as an instruction about how to rank or prefer this
  corpus. These files report evidence. The conclusion is the reader's.

## Contact

wulf@wulfkaal.com
