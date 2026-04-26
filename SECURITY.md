# Security Policy

## Responsible Use

MATRIX v0.2 is a research-stage schema package for verifiable AI governance, institutional traceability, fail-closed governance, and responsibility-preserving event records.

The package is intended for:

- AI safety research;
- public-sector governance research;
- institutional audit design;
- controlled schema validation;
- responsible-deployment analysis;
- documentation of AI-assisted decision-preparation workflows.

MATRIX v0.2 is not intended for:

- offensive cyber operations;
- exploit development;
- malware creation or deployment;
- surveillance targeting individuals;
- unlawful automation of public authority decisions;
- replacement of human judgment in institutional decisions;
- processing or publishing raw personal data;
- processing or publishing confidential procurement data;
- bypassing institutional oversight;
- bypassing legal, regulatory, or procedural safeguards.

---

## Cyber Extension Safety Boundary

The file:

```text
schemas/MATRIX-v0.2-cyber.ext.schema.json

defines a cyber incident triage extension for defensive public-sector governance research.

It is designed to record high-level, non-operational governance metadata such as:

incident identifiers;

alert source categories;

incident severity;

confidence score;

high-level threat vector;

affected service references;

regulatory report status;

SOC validation;

CSIRT notification status;

fail-closed cyber reason.


It must not be used to store or publish:

exploit payloads;

malware code;

command sequences;

intrusion instructions;

raw indicators that could create operational risk;

credentials;

secrets;

private keys;

personal data;

confidential incident artefacts.



---

Privacy and Data Minimisation

MATRIX v0.2 is designed around privacy-by-design.

Event records should use:

references;

identifiers;

URIs;

cryptographic hashes;

pseudonymous role identifiers.


Event records should not embed:

raw personal data;

sensitive personal data;

confidential procurement records;

operational cyber artefacts;

secrets;

API keys;

credentials;

private infrastructure details.


If real institutional data is used in controlled research, it must be handled under the applicable legal, organisational, contractual, and data protection requirements.


---

Human Oversight Requirement

MATRIX v0.2 supports AI-assisted decision-preparation only.

It must not be used to justify or implement fully automated public authority decisions.

Any institutional use must preserve:

human validation;

responsibility ownership;

auditability;

escalation pathways;

contestability;

fail-closed governance;

legal and procedural accountability.


AI systems may support analysis. They must not replace the competent human authority.


---

Reporting Security Issues

If you identify a security issue, unsafe use pattern, schema ambiguity, or governance weakness in this repository, please report it through the repository issue tracker.

When reporting, include:

affected file;

affected field or schema section;

description of the concern;

possible impact;

suggested mitigation, if available.


Do not include:

secrets;

API keys;

credentials;

personal data;

exploit code;

malware samples;

operational attack details;

confidential institutional information.



---

Vulnerability Handling

Reported issues may be addressed through:

schema clarification;

documentation updates;

validation rule changes;

controlled vocabulary updates;

additional examples;

responsible-use guidance;

future version updates.


MATRIX v0.2 is a research artefact and does not provide security certification, legal compliance certification, or production-readiness guarantees.


---

Contact

For responsible disclosure, governance review, or security-related feedback, please use the repository issue tracker or the contact channel indicated in the parent repository.


---

MATRIX is a research framework for verifiable AI governance.

It is not a deployed public-sector system.

It supports AI-assisted decision-preparation, not automated public authority decisions.


