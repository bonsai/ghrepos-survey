# ghrepos-survey

A reusable skill for evidence-backed GitHub repository surveys and build-vs-buy decisions.

It helps answer whether to **reuse, integrate, contribute, fork, build, validate, or stop**—without treating GitHub stars as a proxy for quality.

## Use

Read [SKILL.md](SKILL.md) and apply it when researching existing implementations for a product idea, technical problem, or OSS capability.

## Outputs

- Repository shortlist and comparison matrix
- Evidence-linked findings with facts separated from hypotheses
- Build-vs-buy / reuse-vs-build recommendation
- Optional repositories.jsonl, evidence.jsonl, survey.json, report.md, and static index.html

## Design principle

This repository defines a **skill/workflow**, not a standalone service. It can be invoked by an AI agent and reused by broader research workflows.

## Related projects

- [paper-survey-agent](https://github.com/bonsai/paper-survey-agent) — academic-paper surveys
- [omni-survey](https://github.com/bonsai/omni-survey) — broader integrated surveys and decision support

## Status

Initial skill definition. Validate it against a real research question before adding a collector, database, web app, or subscription system.
