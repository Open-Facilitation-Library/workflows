# OFL Workflows

A library of agent workflow definitions for deliberation and facilitation platforms.

Part of the [Open Facilitation Library](https://github.com/Open-Facilitation-Library).

## What are workflows?

Workflows describe how AI agents facilitate group processes — how they get input from participants, process it, draw from memory/context, and produce outputs. Each workflow maps the concrete agent architecture of a platform or reusable pattern.

The key filter for inclusion: **does an AI agent actively conduct, guide, or mediate a conversation or group process?** This covers AI facilitation across domains: deliberation, market research, education, innovation workshops, dispute resolution, and more.

This complements OFL's [facilitation patterns](https://github.com/Open-Facilitation-Library/skills) (abstract methods like cross-pollination or Delphi) by documenting how real products implement AI facilitation as agent systems.

## Structure

```
schema/
  workflow-schema.yaml    # Schema definition
products/                 # How real platforms implement AI facilitation
  anthropic-interviewer.yaml
  bot-mediation.yaml
  complexchaos.yaml
  cortico.yaml
  crowdsmart.yaml
  habermas-machine.yaml
  harmonica.yaml
  jigsaw-sensemaking.yaml
  juno.yaml
  listen.yaml
  orchidea.yaml
  outset.yaml
  parlay.yaml
  remesh.yaml
  talk-to-the-city.yaml
  thinkscape.yaml
```

## Workflow Schema

Each workflow is a YAML file describing:

- **Agents** — what agent roles exist (facilitator, synthesizer, clustering engine, etc.)
- **Participants** — how people interact (text/voice/vote, sync/async, scale)
- **Stages** — the ordered pipeline: input → processing → memory → output
- **Data flow** — what goes in, what comes out, where data lives
- **Pattern mapping** — which OFL facilitation patterns it implements
- **Source type** — how the workflow was documented:
  - `verified` — from open-source code or detailed published methodology
  - `researched` — from academic papers or detailed technical write-ups
  - `inferred` — reconstructed from public marketing/website descriptions

See [`schema/workflow-schema.yaml`](schema/workflow-schema.yaml) for the full definition.

## Product Workflows

| Platform | Source | Type | Agents | Scale |
|----------|--------|------|--------|-------|
| [Anthropic Interviewer](products/anthropic-interviewer.yaml) | researched | Async 1-on-1 interviews | Interviewer + Analyst | 1,000+ |
| [Bot Mediation](products/bot-mediation.yaml) | researched | AI dispute mediation | AI Bot Mediator | 2 (bilateral) |
| [ComplexChaos](products/complexchaos.yaml) | inferred | Async organizational alignment | Dialogue Agent + Pattern Synthesizer | 5-200 |
| [Cortico](products/cortico.yaml) | researched | Community audio conversations | Recorder + AI Sensemaker + Human Facilitator | 6-500 |
| [CrowdSmart](products/crowdsmart.yaml) | researched | Generative Collective Intelligence | Collective Reasoning Agent + Pairwise Engine + Private LM | 10-10,000 |
| [Habermas Machine](products/habermas-machine.yaml) | verified | Iterative consensus | Statement Generator + Critique Processor | 5-1,000 |
| [Harmonica](products/harmonica.yaml) | verified | Async structured deliberation | Facilitator + Cross-Pollinator + Synthesizer | 3-500 |
| [Jigsaw Sensemaking](products/jigsaw-sensemaking.yaml) | verified | Comment analysis | Topic Modeler + Categorizer + Summarizer | 50-100,000 |
| [Juno](products/juno.yaml) | inferred | Unscripted AI interviews | Interviewer + Thematic Analyst | 5-1,000 |
| [Listen](products/listen.yaml) | inferred | AI research pipeline | Recruiter + Interviewer + Analyst | 10-1,000 |
| [Orchidea](products/orchidea.yaml) | researched | AI workshop facilitation | AI Ideator + Proposal Drafter | 3-500 |
| [Outset](products/outset.yaml) | researched | Multimodal AI interviews | AI Moderator + Fraud Detector + Analyst | 10-5,000 |
| [Parlay Ideas](products/parlay.yaml) | researched | Classroom discussion facilitation | Parlay Genie + Participation Tracker | 5-40 |
| [Remesh](products/remesh.yaml) | inferred | Real-time collective dialogue | Clustering Engine + Consensus Predictor + Human Moderator | 20-5,000 |
| [Talk to the City](products/talk-to-the-city.yaml) | verified | Elicitation + clustering | WhatsApp Bot + Topic Clusterer + Visualizer | 10-10,000 |
| [Thinkscape](products/thinkscape.yaml) | researched | Swarm intelligence | Conversational Surrogates + Orchestrator | 14-400 |

## Planned Features

- **Abstract workflows** — reusable, product-agnostic workflow definitions extracted from the product layer (in `abstract/`)
- **Schema.org JSON-LD** — generate web pages with [schema.org](https://schema.org/) structured data from each YAML workflow, mapping to `HowTo`/`HowToStep` (stages), `SoftwareApplication` (products), `Role` (agents), and `Dataset` (outputs). This would make workflows discoverable by search engines and consumable by AI assistants (Claude, Perplexity, ChatGPT). Deliberation-specific concepts (cross-pollination, pairwise comparison, consensus) have no schema.org equivalent and would remain in the YAML schema.
- **OpenClaw integration** — generate agent configurations for [OpenClaw](https://github.com/openclaw) or similar orchestration frameworks from the abstract workflow layer

## Contributing

Add a new workflow by creating a YAML file following the schema. Product workflows go in `products/`, reusable abstract workflows in `abstract/` (coming soon).

## License

MIT
