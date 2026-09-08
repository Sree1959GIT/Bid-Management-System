# BOI Product Requirements Document

## Vision
BOI (Business Opportunity Intelligence) is a reusable AI-native framework for discovering and evaluating business opportunities using company knowledge, user intent and external procurement data.

The initial use case is India's Government e-Marketplace (GeM) and the Electronics & Industrial Automation business line.

BOI is not a generic tender database. Its purpose is to answer: Which currently available opportunities are genuinely worth our attention, given what we have proven, what we can realistically deliver, our commercial preferences, and the user's current intent?

## Principles
1. Precision over recall.
2. Evidence before inference.
3. Proven capability is different from adaptable capability.
4. Do not recommend an opportunity merely because keywords match.
5. Separate source retrieval from business reasoning.
6. Keep the BOI core thin.
7. Put business-line differences in profiles, Skills, Workflows and configuration.
8. Preserve original source documents.
9. Knowledge grows incrementally.
10. Every important recommendation should be explainable and traceable.
11. Never silently invent missing commercial, technical or eligibility information.
12. External access must use legitimate, authorized mechanisms. Do not bypass CAPTCHA, authentication controls, rate limits or access restrictions.

## Phase 1 user stories

### Opportunity discovery
- Ask for the best currently open opportunities for a business line.
- Provide natural-language intent instead of fixed keywords.
- Constrain value, geography, closing date, customer/sector, capability or other criteria.
- Receive a small ranked shortlist rather than a large result dump.

### Capability matching
- Understand documented company capabilities.
- Distinguish Proven, Adaptable and New/Gap capabilities.
- Cite evidence supporting capability claims.
- Identify critical gaps and risks.

### Knowledge ingestion
- Add PDFs, Word, Excel, PowerPoint, CAD/drawings/images, scans and other supported project material incrementally.
- Keep originals untouched.
- Store processed Markdown, extracted images/tables and metadata separately.
- Re-run ingestion safely without unnecessary duplicate processing.
- Report failed or uncertain extraction.

### Tender history
- Represent participated, won, lost, withdrawn and no-go tenders.
- Let outcome and lessons learned influence future recommendations.
- Never treat historical data as current tender data.

## Phase 1 non-goals
Do not build a dashboard, full CRM, full bid management system, autonomous bid submission, CAPTCHA solving, payment/procurement transactions, vector DB by default, multiple procurement portals, multiple business lines, large agent swarm, or complex orchestration infrastructure.

## Initial business line
Electronics & Industrial Automation.
Seed themes:
- automated test benches
- electronic test systems
- ATE
- functional test systems
- test fixtures
- jigs and fixtures
- control panels
- PLC/HMI/SCADA
- DAQ and instrumentation
- industrial automation
- electronics integration
- cable/harness testing
- custom engineering systems

These are seed themes, not fixed search keywords.

## Scout output
For each shortlisted opportunity provide:
- rank
- bid/tender reference
- title
- buyer/organisation
- closing date
- value/quantity when available
- source link/reference
- opportunity category
- overall fit score
- capability fit
- delivery fit
- eligibility fit
- commercial fit where evidence exists
- strategic fit
- why it matches
- evidence
- capability gaps
- risks/unknowns
- recommendation: PURSUE / REVIEW / WATCH / NO-GO
- confidence
- information freshness

Default shortlist: normally 3-10 opportunities. Fewer is correct when only a few genuinely qualify.

## Decision philosophy
A high score must not override a fatal disqualifier, such as mandatory eligibility failure, unavailable certification, impossible delivery timeline, unauthorized access requirement, or clearly out-of-scope work.

## Evolution
Future phases may add tender document analysis, compliance matrices, bid/no-bid workflows, costing, proposal generation, win/loss learning, monitoring, notifications and additional business lines/sources. Do not implement these merely because they are listed here.
