# BOI Skill Model

A Skill is a reusable capability package that tells an AI tool when to use it, what inputs it expects, what knowledge it may use, what procedure to follow, what output contract to produce, and what quality checks apply.

## Suggested structure

```text
skill-name/
├── SKILL.md
├── schemas/
├── examples/
├── resources/
└── scripts/
```

Create supporting directories only when needed.

## Generic opportunity-scout Skill

Purpose: find a small number of high-fit business opportunities using user intent, company knowledge, an active business profile and one or more opportunity sources.

Procedure:
1. Parse user intent.
2. Load the selected business profile.
3. Identify opportunity hypotheses, not just keywords.
4. Query available source connector(s).
5. Normalize candidates.
6. Remove obvious duplicates/irrelevant results.
7. Retrieve additional detail only for promising candidates.
8. Compare requirements with company capabilities.
9. Identify Proven/Adaptable/New-or-Gap capabilities.
10. Check eligibility and fatal disqualifiers.
11. Score and rank.
12. Produce concise evidence-backed shortlist.
13. State uncertainty.
14. Ask for human decision/next action.

## Output contract
Every shortlisted item should contain opportunity identity, fit score, recommendation, rationale, evidence, gaps, risks, confidence and freshness.

Missing data must be marked unknown. Do not invent values.

## Specialization
Business-line-specific Skills may extend the generic Skill, but should reuse its output contract where practical. Engineering, software-services and workforce workflows should differ mainly in evaluation logic and process stages rather than repository conventions.
