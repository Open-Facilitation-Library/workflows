# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A library of agent workflow definitions for AI facilitation platforms. Part of the [Open Facilitation Library](https://github.com/Open-Facilitation-Library).

Each YAML file documents how a platform's AI agents facilitate group processes — the agent roles, participant interaction model, stage pipeline, and data flow.

**Inclusion criteria:** Does an AI agent actively conduct, guide, or mediate a conversation or group process? This covers AI facilitation across domains: deliberation, market research, education, innovation workshops, dispute resolution, and more. Tools that only collect votes, structure arguments, or analyze data post-hoc without an AI agent in the facilitator role are out of scope.

## Structure

```
schema/workflow-schema.yaml    # Canonical schema definition
products/                      # Real platform implementations (17 workflows)
research/                      # Research notes on evaluated platforms
```

## Schema Conventions

Every product workflow YAML follows `schema/workflow-schema.yaml`. Key fields:

- **`source_type`** — Confidence level for the workflow documentation:
  - `verified` — from open-source code or detailed published methodology
  - `researched` — from academic papers or detailed technical write-ups
  - `inferred` — reconstructed from public marketing/website descriptions
- **`agents[].type`** — `llm` | `human` | `hybrid` | `system`
- **`participants`** — `input_mode` (text/voice/vote/mixed), `interaction` (one-to-one/small-group/large-group), `synchronicity` (sync/async/hybrid), `scale` (min/max/typical), `anonymity`
- **`stages[]`** — Ordered pipeline, each with: `input` → `processing` → `memory` → `output`, plus `duration` and `human_in_loop`
- **`patterns`** — References to OFL facilitation patterns from the [skills repo](https://github.com/Open-Facilitation-Library/skills) (e.g., `cross-pollination`, `delphi-method`)

## Adding a New Workflow

1. Research the platform — check for open-source repos, academic papers, technical blog posts, then marketing materials (in that order of preference)
2. Create `products/<platform-name>.yaml` following the schema
3. Set `source_type` honestly based on your best available source
4. Add a comment header with the platform URL
5. Update the product table in `README.md`
6. If a platform was evaluated but excluded, save rationale in `research/<platform>-<topic>.md`

## Relationship to OFL

Complements the `skills/` repo (abstract facilitation patterns like cross-pollination, Delphi method) by documenting concrete agent architectures. The `patterns` field in each workflow references patterns from `skills/patterns/`.
