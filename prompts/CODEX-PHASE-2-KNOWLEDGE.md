# Codex Phase 2 Prompt - Knowledge and Evidence

Continue from the stable BOI ingestion implementation.

Read all BOI specs before coding.

## Objective

Turn the processed document collection into a structured, evidence-aware local knowledge layer.

Implement the minimum required mechanisms for Projects, Capabilities, Tenders, Tender Outcomes, Evidence and Source Documents.

## Proven vs adaptable vs gap

Represent capability maturity explicitly:
- `PROVEN`: evidence of actual delivery
- `ADAPTABLE`: strong evidence of adjacent capability but not identical delivery
- `NEW_OR_GAP`: material new capability, technology, certification or experience required

Do not infer PROVEN solely from keyword similarity.

## Evidence

Create a consistent evidence object containing:
- claim
- source
- location/page/section when known
- evidence type
- confidence
- derived/inferred flag

## Retrieval

Implement simple local retrieval first. Prefer deterministic metadata filtering, text search, structured lookup and lightweight ranking. Do not introduce a vector database unless tests show simple retrieval is insufficient.

## Knowledge updates

Adding a new document should enrich the knowledge base without destroying existing information.
Provide mechanisms for linking a project to documents, capabilities to projects/evidence, historical tenders to outcomes, and lessons learned.

## Tests

Test evidence linkage, capability classifications, project relationships, tender outcomes, retrieval, provenance and incremental updates.

## Acceptance

Given a small sample knowledge base, the system can answer:
- What capabilities are proven?
- What capabilities are adaptable?
- What evidence supports a capability?
- Which projects demonstrate it?
- What happened on a historical tender?

Every answer must distinguish facts from inference.

Do not implement autonomous tender scouting yet.
