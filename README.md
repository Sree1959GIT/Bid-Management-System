# BOI - Business Opportunity Intelligence

This repository is the controlled starting point for building BOI with Codex, while keeping the resulting framework usable by both Codex and Claude Code.

## Goal

Build a thin, AI-native framework that combines:
- evolving company/project knowledge
- business-line profiles
- reusable Skills
- optional Agents
- reusable Workflows
- procurement/source connectors such as GeM MCP
- intent-driven opportunity discovery, matching, ranking and bid/no-bid recommendations

## Phase 1 scope

Start deliberately narrow:
1. Build the repository foundation.
2. Build incremental document ingestion.
3. Create the Electronics & Automation business profile.
4. Integrate/test GeM MCP without building a custom scraper unless explicitly justified.
5. Build the generic `opportunity-scout` Skill.
6. Validate against real company knowledge and real open GeM opportunities.

## Design principle

Precision over volume. BOI should surface a small number of opportunities that the business can realistically execute, supported by evidence.

## Operating rule

Codex implements. The user owns decisions and source material. Claude/Codex can operate the resulting framework. Changes should be incremental, tested and documented.
