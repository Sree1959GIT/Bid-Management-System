# Codex Operating Protocol for BOI

Use this protocol for every future BOI development session.

## Before changes
1. Read relevant specs.
2. Inspect current repository state.
3. Inspect recent CHANGELOG entries.
4. Identify the smallest coherent change.
5. State the plan briefly.

## During changes
- preserve existing working functionality
- avoid unnecessary refactors
- keep modules small
- add/update tests
- update documentation
- do not introduce dependencies without justification
- do not invent company facts
- do not commit secrets
- do not make unauthorized external requests

## After changes
Run relevant tests, then report:

### Changed
Files/modules changed.

### Tested
Exact commands and result.

### Decisions
Architectural decisions made.

### Limitations
Known limitations or assumptions.

### User input needed
Only decisions that genuinely require the business owner.

### Next step
Recommend exactly one next step.

## Change control
If implementation reveals that the specs are wrong or incomplete:
- do not silently rewrite architecture
- document the issue
- propose the change
- ask before materially changing architecture

## Quality rule
Prefer a smaller working implementation over a broad unfinished framework.
BOI should become more capable through incremental validated additions, not speculative complexity.
