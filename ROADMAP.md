# MATRIX Roadmap

This roadmap describes planned development directions for the MATRIX research schema package.

MATRIX is a research-stage framework for verifiable AI governance, institutional traceability, fail-closed governance, and responsibility-preserving event records.

The roadmap is indicative and may change as external review, validation work, schema testing, and research priorities evolve.

---

## Current Release

### MATRIX v0.2.0

Status: initial research schema package.

Included:

- core event schema;
- cyber incident extension;
- procurement extension;
- synthetic example records;
- technical note;
- repository documentation;
- security and responsible-use policy;
- contribution guidelines;
- citation metadata;
- validation roadmap;
- CI workflow placeholder.

Primary focus:

- traceability-by-construction;
- human validation;
- responsibility ownership;
- fail-closed governance;
- privacy-by-design;
- auditability;
- domain extension architecture.

---

## Planned v0.2.x Updates

The v0.2.x line will focus on corrections, clarifications, examples, and validation preparation.

Planned work:

- refine schema descriptions;
- add controlled vocabulary documentation;
- add more synthetic example records;
- improve example consistency across core and extensions;
- add validation notes for combined core + extension records;
- document hash-chain verification assumptions;
- clarify canonicalization requirements;
- improve fail-closed semantics;
- add issue templates;
- add pull request template;
- add GitHub release notes.

Expected outputs:

- `vocabularies/README.md`
- `vocabularies/MATRIX-v0.2-controlled-vocabularies.json`
- additional example records
- refined validation documentation
- release tag `v0.2.0`

---

## Planned v0.3.0

The v0.3.0 line will focus on validation tooling and schema testability.

Planned work:

- reference JSON Schema validator;
- canonicalization and hash verification script;
- example validation workflow;
- conformance test suite;
- fail-closed conformance checks;
- privacy-by-design checks;
- responsibility-owner checks;
- human-validation checks;
- domain extension validation logic;
- machine-readable validation report format.

Expected outputs:

- `validation/validate.py`
- `validation/hash_trace.py`
- `validation/report.schema.json`
- `tests/`
- executable validation examples
- CI validation workflow replacing the current placeholder.

---

## Planned v0.4.0

The v0.4.0 line will focus on legal and institutional alignment.

Planned work:

- EU AI Act alignment note;
- GDPR data minimisation and retention note;
- NIS2 / cyber resilience alignment note;
- public procurement governance note;
- public-sector auditability note;
- institutional responsibility mapping;
- risk-classification guidance.

Expected outputs:

- `docs/MATRIX-v0.4-EU-AI-Act-Alignment.md`
- `docs/MATRIX-v0.4-GDPR-Privacy-Note.md`
- `docs/MATRIX-v0.4-NIS2-Cyber-Alignment.md`
- `docs/MATRIX-v0.4-Procurement-Governance-Note.md`

---

## Planned v0.5.0

The v0.5.0 line will focus on new domain extensions.

Candidate extensions:

- administrative appeals;
- social benefits review;
- regulatory supervision;
- infrastructure monitoring;
- emergency coordination;
- judicial preparation support;
- public health administrative triage;
- energy infrastructure resilience;
- education administration review.

Expected outputs:

- additional extension schemas;
- additional synthetic examples;
- domain-specific technical notes;
- extension design guidelines.

---

## Planned v1.0.0

The v1.0.0 line will be considered only after:

- external review;
- stable schema architecture;
- working validation tooling;
- documented controlled vocabularies;
- multiple validated examples;
- legal and institutional alignment notes;
- clear versioning policy;
- sufficient review of safety, privacy, and governance boundaries.

Potential v1.0.0 criteria:

- stable core schema;
- stable extension mechanism;
- validated examples;
- reference validator;
- reproducible trace hashing;
- documented fail-closed state model;
- clear responsible-use boundary;
- research publication or technical report.

---

## Research Principles

All future work must preserve the following MATRIX principles:

- AI supports decision-preparation, not automated public authority decisions.
- Human validation remains mandatory where institutional decisions are involved.
- Responsibility remains assigned to human or institutional roles.
- Records remain traceable, auditable, and contestable.
- Invalid or incomplete records fail closed.
- Privacy-by-design is preserved.
- Domain extensions must not introduce offensive cyber content, raw personal data, confidential procurement content, or unsafe automation patterns.
- MATRIX remains a research framework unless explicitly reviewed and authorized for controlled institutional experimentation.

---

## Open Research Questions

Key questions for future work:

1. How should canonicalization and hashing be implemented to ensure reproducible event-chain verification?
2. How should human validation be represented when multiple reviewers are involved?
3. How should contested or appealed records be linked to subsequent events?
4. How should fail-closed states propagate through a multi-event institutional workflow?
5. How should domain extensions remain interoperable while preserving domain-specific obligations?
6. How should privacy-preserving references be resolved during audit without exposing unnecessary data?
7. How should responsibility ownership be mapped across human, organizational, vendor, and infrastructure layers?
8. How should MATRIX event records interact with existing institutional logging systems?
9. How should validation reports be structured for supervisory bodies or external reviewers?
10. What minimum evidence is required for an AI-assisted institutional event to be considered reconstructible?

---

## Community Review

External review is welcome in the following areas:

- AI safety;
- responsible AI deployment;
- public-sector governance;
- cybersecurity governance;
- procurement integrity;
- digital resilience;
- institutional audit;
- legal informatics;
- data protection;
- JSON Schema design;
- validation tooling.

Please use GitHub Issues for comments, questions, corrections, or domain-extension proposals.

---

MATRIX is a research framework for verifiable AI governance.

It is not a deployed public-sector system.

It supports AI-assisted decision-preparation, not automated public authority decisions.
