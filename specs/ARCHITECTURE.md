# BOI Architecture Specification

## 1. High-level architecture

```text
User Intent
    |
    v
Claude Code / Codex
    |
    +--> Business Profile
    +--> Knowledge Base
    +--> Skills
    +--> Workflows
    +--> Connectors
    |
    v
Opportunity Intelligence
    |
    +--> Retrieve
    +--> Normalize
    +--> Filter
    +--> Match
    +--> Score
    +--> Rank
    +--> Explain
    |
    v
Human decision
```

## 2. Repository architecture

```text
BOI/
├── README.md
├── ARCHITECTURE.md
├── CHANGELOG.md
├── .gitignore
│
├── specs/
│   ├── BOI-PRD.md
│   ├── ARCHITECTURE.md
│   ├── KNOWLEDGE-MODEL.md
│   ├── SKILL-MODEL.md
│   ├── WORKFLOW-MODEL.md
│   └── SECURITY-MODEL.md
│
├── knowledge/
│   ├── shared/
│   │   ├── source/
│   │   ├── processed/
│   │   │   ├── markdown/
│   │   │   ├── images/
│   │   │   └── tables/
│   │   └── metadata/
│   └── business-lines/
│       └── electronics-automation/
│           ├── source/
│           ├── processed/
│           ├── projects/
│           ├── tenders/
│           ├── capabilities/
│           ├── products/
│           ├── customers/
│           └── commercial/
│
├── profiles/
│   └── electronics-automation/
│       ├── profile.md
│       ├── capability-profile.md
│       ├── opportunity-profile.md
│       └── config.yaml
│
├── skills/
│   ├── generic/
│   │   └── opportunity-scout/
│   └── business-lines/
│       └── electronics-automation/
│
├── workflows/
│   ├── ingestion/
│   ├── opportunity-discovery/
│   └── tender-evaluation/
│
├── agents/
│   ├── ingestion-agent/
│   └── opportunity-scout-agent/
│
├── connectors/
│   └── gem/
│
├── schemas/
├── scripts/
├── tests/
└── docs/
```

The exact implementation may simplify this structure during Phase 0 if a directory is not yet needed. Do not create empty architecture for appearance alone.

## 3. Thin core

The core should contain only reusable mechanisms:
- configuration loading
- profile loading
- knowledge discovery/retrieval
- evidence/provenance handling
- opportunity normalization
- filtering
- scoring/ranking primitives
- validation
- logging
- tests

Business-specific rules do not belong in the core.

## 4. Profiles

A profile defines how BOI should interpret opportunities for one business line.

A profile may specify capabilities, proven capabilities, adaptable capabilities, gaps, preferred sectors, excluded sectors, preferred opportunity types, commercial ranges, delivery constraints, geography, strategic priorities, eligibility constraints, scoring weights, no-go rules and terminology/synonyms.

## 5. Connectors

Connectors provide external data access.

The GeM connector should expose a clean normalized interface to the rest of BOI.

Do not couple the scoring engine directly to GeM-specific HTML/API structures.

Conceptually:

```text
GeM MCP -> GeM adapter -> normalized Opportunity objects -> BOI
```

If the existing GeM MCP proves unreliable or unavailable, stop and document the limitation before replacing it with custom access logic.

## 6. Skills

Skills are reusable task instructions plus supporting schemas/scripts/resources.

The generic `opportunity-scout` Skill should not contain Electronics-specific rules. It consumes a profile.

## 7. Agents

Agents are optional orchestration wrappers.

Use an agent only when autonomous multi-step execution is useful. Do not create agents merely to rename deterministic code.

## 8. Human-in-the-loop

Final bid/no-bid decisions remain human decisions in Phase 1. The system recommends and explains. It does not submit bids.
