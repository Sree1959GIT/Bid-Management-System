# Codex Phase 4 Prompt - GeM Connector Validation

Continue from the stable BOI foundation.

## Objective

Connect BOI to India's Government e-Marketplace opportunity data through a legitimate, maintainable MCP/connector mechanism.

## First inspect

Before coding:
1. inspect any existing GeM MCP implementation available in the repo
2. inspect its documentation
3. identify whether it is public/open-source or an authorized interface
4. identify required configuration
5. determine what data it actually returns
6. test current open-bid retrieval if access is available

## Rules

Do not bypass CAPTCHA, authentication, access controls or rate limits. Do not store credentials in source control.

Prefer official API, authorized integration, existing MCP or thin local adapter.

## Normalize

Create a source-neutral opportunity representation containing at least:
- source
- reference
- title
- buyer
- category
- dates
- value
- quantity
- location
- eligibility
- requirements
- documents
- source reference
- retrieval timestamp
- raw-source identifier

Unknown fields remain unknown.

## Acceptance

Using real or clearly labelled mock data, demonstrate source retrieval, normalization, duplicate handling, error handling and freshness metadata.

Do not claim live GeM access is functional unless tested. Document limitations.
