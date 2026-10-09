---
name: ghrepos-survey
description: Research GitHub repositories for a product idea, technical problem, or OSS capability. Use when deciding whether to reuse, integrate, fork, contribute upstream, build a missing capability, or stop; produce evidence-backed repository comparisons and a practical build-vs-buy recommendation.
---

# GitHub Repository Survey

## Purpose

Turn a question or product idea into an evidence-backed survey of existing GitHub projects. This is a reusable research skill, not a standalone always-running agent or hosted SaaS.

Answer the decision: **reuse, integrate, contribute, fork, build, validate, or stop?**

## Inputs

Gather what is available; ask only for missing details that materially affect the search.

- **Question / decision:** what the user wants to accomplish
- **Keywords:** alternative names, domain terms, likely implementation terms
- **Language / ecosystem:** optional language, framework, or runtime
- **Constraints:** license, hosting, platform, maintenance, security, budget
- **Freshness:** optional last-updated window
- **Scope:** default to a manageable shortlist (about 10–30 candidates)

Do not block on optional inputs. Infer search terms from the problem and label assumptions.

## Workflow

1. **Frame the decision**
   - Restate the question as a concrete decision.
   - Generate synonyms, implementation terms, and adjacent categories.
   - Define inclusion/exclusion criteria before comparing candidates.

2. **Discover candidates**
   - Search GitHub by topic, README terms, language, and related projects.
   - Prefer primary repository pages, READMEs, releases, license files, issue/PR activity, and official docs.
   - Use multiple query formulations to reduce search-term bias.
   - Record the search date and queries where practical.

3. **Collect evidence**
   For each candidate, capture available facts:
   - full_name, URL, description, primary language, topics
   - stars/forks and last-updated / last-push dates, when available
   - license, release status, archived status
   - stated capabilities and evidence URLs
   - signs of maintenance: recent commits, releases, issue/PR response
   - limitations, dependencies, deployment model, and integration surface

   Missing data must be unknown, not guessed. Stars are a discovery signal, not proof of quality.

4. **Deduplicate and classify**
   Assign one or more categories:
   - direct alternative
   - adjacent solution
   - reusable library / component
   - reference implementation
   - infrastructure / dependency
   - inactive or archived project

5. **Compare against requirements**
   - Build a comparison matrix around the actual decision criteria.
   - Separate observed facts from interpretation and hypotheses.
   - Cite repository URLs or exact files for important claims.
   - Do not rank candidates using popularity alone.

6. **Find gaps and recommend a strategy**
   Evaluate:
   - reuse as-is
   - integrate multiple projects
   - fork or contribute upstream
   - build only the missing capability
   - run a small validation experiment first
   - stop if no defensible opportunity exists

   State the strongest evidence, trade-offs, uncertainties, and cheapest next experiment. Avoid claiming a market gap merely because search did not find a project.

7. **Deliver reusable artifacts**
   When working in a repository or file workspace, prefer:
   - repositories.jsonl — one normalized repository record per line
   - evidence.jsonl — one claim/evidence/source record per line
   - survey.json — structured summary and recommendation
   - report.md — readable findings, matrix, risks, and next steps
   - index.html — optional static dashboard when useful

   If the environment cannot create files, return the same structure in the response without pretending files were saved.

## Evidence and quality rules

- Label each statement as **Fact**, **Assessment**, or **Hypothesis** when the distinction is not obvious.
- Link important claims to primary sources.
- Include search scope and limitations; absence from search results is not proof of absence.
- Respect licenses and do not imply that public code is automatically safe or reusable.
- Never expose access tokens. Use authenticated GitHub access only through approved integrations.
- Do not execute untrusted repositories or install their dependencies during reconnaissance.
- Report uncertainty and stale/missing metadata explicitly.

## Output format

1. **Decision in one sentence**
2. **Shortlist** with links and why each matters
3. **Comparison matrix** against stated requirements
4. **Evidence-backed findings**
5. **Gaps / risks / unknowns**
6. **Recommendation**: reuse, integrate, contribute, fork, build, validate, or stop
7. **Next experiment** with a measurable success criterion
8. **Sources and search scope**

## Relationship to sibling projects

- paper-survey-agent: deep survey of academic papers and research evidence.
- ghrepos-survey (this skill): survey of GitHub repositories and implementation options.
- omni-survey: combine research, OSS, market, competitor, and user evidence into a broader decision report.

Use this skill as a component inside broader workflows rather than duplicating every survey pipeline in a separate autonomous service.

## Monetization hypothesis

Keep the reusable skill and basic workflow open. Potential paid deliverables include custom, cited build-vs-buy reports, technical landscape assessments, and ongoing repository/competitor monitoring. Treat these as hypotheses until a customer pays; validate with one narrowly scoped report before building subscription infrastructure.
