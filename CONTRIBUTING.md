# Contributing to MATRIX v0.2

Thank you for your interest in reviewing or contributing to the MATRIX v0.2 research schema package.

MATRIX v0.2 is a research-stage schema architecture for verifiable AI governance, institutional traceability, fail-closed governance, and responsibility-preserving event records.

This repository is intended for:

- AI safety research;
- public-sector AI governance research;
- institutional audit design;
- schema validation;
- responsible-deployment analysis;
- technical review of traceability-by-construction models.

---

## Contribution Scope

Contributions may include:

- schema corrections;
- documentation improvements;
- validation examples;
- controlled vocabulary suggestions;
- privacy-by-design improvements;
- fail-closed governance refinements;
- auditability and traceability improvements;
- domain extension proposals;
- responsible-use clarifications;
- issue reports about ambiguity, inconsistency, or unsafe interpretation.

---

## Out of Scope

Please do not submit contributions that include:

- offensive cyber content;
- exploit instructions;
- malware code;
- raw personal data;
- confidential procurement data;
- secrets;
- credentials;
- API keys;
- private infrastructure details;
- unlawful automation patterns;
- recommendations to replace legally required human judgment;
- proposals for fully automated public authority decisions.

MATRIX supports AI-assisted decision-preparation only.

It does not support automated public authority decisions.

---

## Repository Structure

```text
README.md
LICENSE
CHANGELOG.md
CITATION.cff
SECURITY.md
CONTRIBUTING.md
schemas/
  README.md
  MATRIX-v0.2-core.schema.json
  MATRIX-v0.2-cyber.ext.schema.json
  MATRIX-v0.2-procurement.ext.schema.json
docs/
  README.md
  MATRIX-v0.2-Technical-Note.md
examples/
  README.md
  event.generic.example.json
  event.cyber.example.json
  event.procurement.example.json


---

How to Contribute

Use GitHub Issues for:

questions;

schema review;

documentation feedback;

bug reports;

validation concerns;

responsible-use concerns;

proposed domain extensions.


Use Pull Requests for:

direct schema changes;

documentation edits;

example records;

validation tooling;

controlled vocabulary additions.



---

Schema Contribution Guidelines

When proposing changes to schema files, please describe:

1. the affected file;


2. the affected field or section;


3. the governance problem addressed;


4. the proposed change;


5. the expected impact on validation;


6. compatibility with privacy-by-design;


7. compatibility with human oversight;


8. compatibility with fail-closed governance.



Schema changes should preserve:

traceability;

auditability;

human validation;

responsibility ownership;

event-chain integrity;

privacy-by-design;

contestability;

fail-closed behaviour.



---

Domain Extension Proposals

New domain extensions should follow the MATRIX core-plus-extension architecture.

A domain extension proposal should include:

domain name;

institutional context;

risk model;

required fields;

controlled vocabularies;

human validation points;

escalation pathways;

audit requirements;

fail-closed conditions;

privacy and data minimisation posture;

examples using synthetic or anonymized data only.


Candidate future extensions include:

administrative appeals;

social benefits review;

regulatory supervision;

infrastructure monitoring;

judicial preparation support;

emergency coordination.



---

Examples

Example records must be:

synthetic;

non-operational;

privacy-preserving;

free of personal data;

free of confidential procurement content;

free of offensive cyber content;

aligned with the relevant schema.


Example records should help reviewers understand validation, traceability, auditability, and responsibility assignment.


---

Responsible Review

When reviewing MATRIX v0.2, please keep the following principles in view:

AI systems may support institutional analysis.

AI systems must not replace human judgment.

Public authority decisions must remain human-accountable.

Event records must remain verifiable.

Invalid or incomplete records must fail closed.

Privacy-by-design must be preserved.

Domain-specific oversight must be encoded where relevant.



---

Versioning

MATRIX v0.2 is a research-stage package.

Changes may be introduced as the schema architecture, controlled vocabularies, validation tooling, examples, and documentation evolve.

Suggested versioning:

0.2.x — corrections, clarifications, examples, documentation updates;

0.3.0 — structural schema changes or new validation model;

1.0.0 — stabilized research release after external review.



---

License

By contributing, you agree that your contributions will be made available under the repository license.

See:

LICENSE


---

Contact

For research collaboration, governance review, or contribution discussion, please use the repository issue tracker.


---

MATRIX is a research framework for verifiable AI governance.

It is not a deployed public-sector system.

It supports AI-assisted decision-preparation, not automated public authority decisions.

