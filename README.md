# OFL Workflows

A library of agent workflow definitions for deliberation and facilitation platforms.

Part of the [Open Facilitation Library](https://github.com/Open-Facilitation-Library).

## What are workflows?

Workflows describe how AI agents orchestrate deliberation — how they get input from participants, process it, draw from memory/context, and produce outputs. Each workflow maps the concrete agent architecture of a platform or reusable pattern.

This complements OFL's [facilitation patterns](https://github.com/Open-Facilitation-Library/skills) (abstract methods like cross-pollination or Delphi) by documenting how real products implement these patterns as agent systems.

## Structure

```
schema/
  workflow-schema.yaml    # Schema definition
products/                 # How real platforms implement deliberation
  anthropic-interviewer.yaml
  harmonica.yaml
  remesh.yaml
  thinkscape.yaml
  complexchaos.yaml
  listen.yaml
```

## Workflow Schema

Each workflow is a YAML file describing:

- **Agents** — what agent roles exist (facilitator, synthesizer, clustering engine, etc.)
- **Participants** — how people interact (text/voice/vote, sync/async, scale)
- **Stages** — the ordered pipeline: input → processing → memory → output
- **Data flow** — what goes in, what comes out, where data lives
- **Pattern mapping** — which OFL facilitation patterns it implements

See [`schema/workflow-schema.yaml`](schema/workflow-schema.yaml) for the full definition.

## Product Workflows

| Platform | Type | Agents | Scale | Key Pattern |
|----------|------|--------|-------|-------------|
| [Anthropic Interviewer](products/anthropic-interviewer.yaml) | Async 1-on-1 interviews | Interviewer + Analyst | 1,000+ | Adaptive interviews → thematic synthesis |
| [Harmonica](products/harmonica.yaml) | Async structured deliberation | Facilitator + Cross-Pollinator + Synthesizer | 3-500 | Cross-pollination between participants |
| [Remesh](products/remesh.yaml) | Real-time collective dialogue | Clustering Engine + Consensus Predictor + Human Moderator | 20-5,000 | Voting + semantic clustering |
| [Thinkscape](products/thinkscape.yaml) | Swarm intelligence | Conversational Surrogates + Orchestrator | 14-400 | Small-group → cross-tank propagation |
| [ComplexChaos](products/complexchaos.yaml) | Async organizational alignment | Dialogue Agent + Pattern Synthesizer | 5-200 | Cross-silo common ground discovery |
| [Listen](products/listen.yaml) | AI research pipeline | Recruiter + Interviewer + Analyst | 10-1,000 | Recruit → interview → synthesize |

## Contributing

Add a new workflow by creating a YAML file following the schema. Product workflows go in `products/`, reusable abstract workflows in `abstract/` (coming soon).

## License

MIT
