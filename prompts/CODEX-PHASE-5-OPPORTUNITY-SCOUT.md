# Codex Phase 5 Prompt - Opportunity Scout

Continue from the stable BOI foundation, knowledge layer, Electronics & Automation profile and GeM connector.

## Objective

Implement the first genuinely useful BOI Skill: `opportunity-scout`.

## User interaction

Support natural-language intent, for example:
> Find the best currently open GeM opportunities we can realistically execute.

or:
> Find a few high-value automation test bench and electronic test system opportunities that match our proven capabilities.

Translate intent into search hypotheses.

## Procedure

1. parse intent
2. identify business profile
3. inspect relevant knowledge
4. generate search hypotheses
5. query GeM
6. normalize candidates
7. remove obvious irrelevant/duplicate candidates
8. retrieve details for promising candidates
9. compare requirements against company capabilities
10. identify Proven/Adaptable/New-or-Gap capabilities
11. identify fatal disqualifiers
12. calculate configurable score
13. rank candidates
14. return a small shortlist
15. provide evidence and uncertainty

## Precision rules

Default to 3-10 recommendations. If only 2 are genuinely strong, return 2. Do not pad the list. High score cannot override a fatal disqualifier. Keyword matches alone are insufficient.

## Output

Each opportunity should include:
- source/reference
- title
- buyer
- closing date
- value/quantity
- category
- fit score
- recommendation
- why it matches
- evidence
- proven capabilities
- adaptable capabilities
- gaps
- risks
- unknowns
- confidence
- freshness

Recommendation values: `PURSUE`, `REVIEW`, `WATCH`, `NO-GO`.

## Explainability

For every high-ranked opportunity answer:
1. Why did this match?
2. What evidence supports that?
3. What do we already know how to deliver?
4. What would we need to adapt?
5. What could prevent us from bidding?
6. What information is still missing?

## Testing

Use mock opportunities plus sample company knowledge. Include adversarial tests for high keyword match but poor capability, excellent technical match but fatal eligibility issue, incomplete data, duplicates, stale opportunities, major capability gap and high technical fit but low strategic fit.

## Acceptance

A test prompt produces a small, ranked and explainable shortlist rather than a raw search result dump.

Do not implement autonomous bid submission or automated final bid/no-bid approval.
