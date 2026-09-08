# BOI Knowledge Model

## Source preservation
Every source document should retain original filename, source location, ingestion timestamp, content hash where practical, source type, processing status, extraction confidence and relationships to derived artifacts. Never overwrite originals with AI-generated content.

## Core entities

### Project
Represents work actually executed or substantially developed. Suggested fields:
- project_id
- name
- customer
- sector
- date/period
- status
- scope
- delivered systems
- technologies
- engineering disciplines
- quantities/capacity where relevant
- outcomes
- source evidence
- lessons learned

### Capability
Every capability should be classified as:
- `PROVEN`: evidence of actual delivery
- `ADAPTABLE`: strong evidence of adjacent capability but not identical delivery
- `NEW_OR_GAP`: material new capability, technology, certification or experience required

Suggested fields: capability_id, name, classification, maturity, evidence, related_projects, technologies, dependencies, limitations, confidence.

### Tender / Opportunity
Suggested fields:
- opportunity_id
- source
- reference
- title
- buyer
- category
- published_date
- closing_date
- value
- quantity
- location
- eligibility
- requirements
- technical_requirements
- commercial_requirements
- documents
- source_url/reference
- retrieval_timestamp
- status
- analysis
- decision
- evidence

### Tender outcome
Allowed outcomes:
- WON
- LOST
- PARTICIPATED_NO_OUTCOME
- WITHDRAWN
- NO_GO
- NOT_PARTICIPATED
- UNKNOWN

Optional lessons: technical, eligibility, price, delivery, documentation, competition, customer, strategic, other.

### Evidence
Evidence should identify:
- claim
- source document
- page/section if available
- extraction/processing method
- confidence

## Evidence hierarchy
Prefer:
1. Original tender/project documents
2. Official procurement source
3. Internal approved project records
4. Internal proposals/estimates
5. Derived summaries
6. AI inference

AI inference must not be represented as source fact.

## Commercial sensitivity
Commercial knowledge may include quotations, costs, margins, supplier prices, winning prices and internal thresholds. Keep sensitive commercial material under controlled paths and do not expose it in generic opportunity summaries unless relevant and authorized.

## Incremental ingestion
Each ingestion run should discover new/changed files, identify duplicates using stable identifiers/hash where practical, process only required files, preserve previous derived artifacts when useful for audit, update metadata/indexes, report failures, and avoid silently deleting knowledge.

## Images and drawings
Retain extracted images and reference them from Markdown. Where practical include figure caption, source page, relative image path and a brief machine-generated description clearly marked as derived. Image descriptions are not authoritative engineering specifications.
