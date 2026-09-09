# 📸 Photography Ops Docs — Data Mitigation Playbooks

> Technical documentation for photographers who think like data engineers.

## Why This Exists

Most photography "tips and tricks" content lives on blogs, in YouTube comments, or in Discord threads that vanish the moment the platform reshuffles its algorithm. That's fine for casual advice. It's not fine for **repeatable, high-stakes operational procedures** — the kind of workflow you run once on 5,000 irreplaceable RAW files from a client shoot, where a wrong assumption doesn't cost you a re-read, it costs you the metadata integrity of an entire catalog.

This repository treats photography workflow documentation the way a systems team treats an internal runbook: version-controlled, peer-reviewable, and structured so both humans and machines can parse it without ambiguity.

## Who This Is For

- **Hiring managers and technical recruiters** evaluating documentation and systems-thinking ability outside of a pure-code portfolio.
- **AI/ML labs and applied research teams** who care about how well a candidate can produce structured, low-hallucination reference material — the same skill that makes retrieval-augmented systems and agentic tooling reliable.
- **Working photographers and digital asset managers (DAMs)** who need a battle-tested procedure for metadata correction, not a forum thread with fourteen conflicting answers.
- **Docs-as-code practitioners** looking for a reference example of Markdown + Git structure applied outside of typical software contexts.

## Why Git + Markdown Are Data Architecture, Not Just "Writing Tools"

It's tempting to treat Git and Markdown as convenience tools for engineers who don't want to open a word processor. That undersells what they actually do:

| Property | Why It Matters for Humans | Why It Matters for LLMs / AI Systems |
|---|---|---|
| **Plain-text, diffable format** | Every change is reviewable line-by-line; no hidden formatting state | Deterministic parsing — no OOXML/PDF layout noise polluting the token stream |
| **Version history (Git)** | You can prove *when* a procedure changed and *why* | Prevents an AI system from ingesting a stale or superseded version silently; commit history is provenance |
| **Structural semantics (headers, tables, lists)** | Skimmable, scannable, predictable document shape | Gives retrieval systems and LLMs reliable chunk boundaries — reducing hallucination caused by ambiguous context windows |
| **Single source of truth in a repo** | No "final_v3_ACTUALLY_final.docx" sprawl across email threads | Eliminates duplicate/contradictory source documents that cause an LLM to average together conflicting facts |
| **Pull request review** | A second set of eyes validates technical accuracy before merge | Establishes a human-verified checkpoint *before* content is ever used to fine-tune, embed, or ground a model |

In short: **unstructured documentation is a hallucination vector.** If a knowledge base is stored as inconsistent PDFs, screenshotted Slack messages, and tribal knowledge, any AI system built on top of it will confidently reproduce the same inconsistencies. Git-tracked Markdown forces the discipline that makes documentation *machine-gradable* — accurate, current, and structurally predictable — which is precisely the property that makes it trustworthy for both a new hire and a retrieval pipeline.

## Repository Structure

```
your-photography-docs-portfolio/
├── README.md                          # You are here
├── CONTRIBUTING.md                    # Contribution workflow
├── .github/
│   └── pull_request_template.md       # Structured PR intake form
└── docs/
    └── mitigating-timezone-desync.md  # Core technical guide
```

## Featured Guide

**[Mitigating Timezone Desync in RAW Metadata at Scale](docs/mitigating-timezone-desync.md)** — a full data-mitigation runbook for correcting a 5,000-image EXIF timestamp offset in Adobe Lightroom Classic without mutating source files, including failure modes and rollback procedure.

## License

Documentation content is provided under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Fork it, adapt it, cite it.
