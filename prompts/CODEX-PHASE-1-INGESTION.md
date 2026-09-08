# Codex Phase 1 Prompt - Knowledge Ingestion

Continue the BOI implementation from the existing repository.

Read:
- specs/BOI-PRD.md
- specs/ARCHITECTURE.md
- specs/KNOWLEDGE-MODEL.md
- specs/SECURITY-MODEL.md
- specs/PHASE-PLAN.md

## Objective

Implement the first production-quality version of the incremental local document ingestion pipeline.

## Inputs
Support, where practical:
- PDF
- DOC/DOCX
- XLS/XLSX
- PPT/PPTX
- PNG/JPG/JPEG
- TXT/MD

Design adapters so additional formats can be added later.

## Output

For each source document create a predictable derived structure such as:

```text
processed/
  markdown/
  images/
  tables/
metadata/
```

Do not modify the source.

Markdown should include source filename, source type, processing timestamp, source hash, page/section markers where possible, headings, tables, references to extracted images, and explicit markers for OCR/AI-derived content.

## Incremental behavior

Implement content hashing, a manifest/index, new-file and changed-file detection, safe re-run, failure status and clear logging.

If unchanged, do not reprocess unnecessarily.

## Extraction quality

For PDF preserve text order/page boundaries where feasible and extract embedded images/tables where feasible.

For Office files preserve headings/tables and extract embedded images where feasible.

For spreadsheets preserve sheet names and table structure. Do not flatten spreadsheets into meaningless prose.

For scanned documents detect lack of text where practical. Use locally available OCR only when appropriate and clearly mark OCR-derived text.

## Tests

Create synthetic fixtures and test each supported format, duplicate ingestion, changed-file ingestion, corrupt input, metadata, image extraction, table extraction and Markdown references.

Do not commit real confidential documents.

## Acceptance test

A clean checkout plus sample documents produces clear source files, Markdown files, image files and metadata/manifest. A second ingestion run does not duplicate or unnecessarily regenerate unchanged outputs.

## Stop condition

Do not proceed into GeM integration or advanced agent work until ingestion is tested and documented.

At completion report implementation summary, commands, tests, known extraction limitations and exactly one recommended next step.
