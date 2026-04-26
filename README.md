# MATRIX v0.2 — Verifiable AI Governance Schemas

## 1. Overview

MATRIX v0.2 is a research-stage schema package for producing verifiable, auditable, and contestable event records when AI systems are used to support institutional decision-preparation.

It defines a JSON Schema architecture intended to make AI-assisted institutional activity traceable across administrative, cybersecurity, and procurement contexts.

The package was derived from three controlled research tests:

- **Test 001** — administrative AI decision-preparation
- **Test 002** — regional cybersecurity incident triage
- **Test 003** — AI-assisted public procurement review

MATRIX v0.2 consists of one core schema and two domain extensions.

---

## 2. What MATRIX v0.2 Is

MATRIX v0.2 is:

- a research framework for verifiable AI governance;
- a set of JSON Schemas defining structured institutional event records;
- a traceability and auditability layer for AI-assisted decision-preparation;
- a schema architecture supporting fail-closed governance, human validation, and contestability;
- a foundation for institutional accountability and regulatory alignment research;
- a technical research package for testing traceability-by-construction in AI-assisted public-sector contexts.

---

## 3. What MATRIX v0.2 Is Not

MATRIX v0.2 is not:

- a deployed public-sector system;
- an automated decision-making engine;
- a substitute for human authority, legal review, or institutional responsibility;
- a certified compliance product;
- a security operations platform;
- a procurement platform;
- a data collection system;
- a tool for offensive cyber operations;
- a mechanism for replacing human judgment in public authority decisions.

MATRIX records references, identifiers, URIs, and cryptographic hashes. It does not require raw personal data, confidential procurement content, exploit material, or operational attack details.

---

## 4. Package Contents

```text
matrix-v0.2/
├── README.md
├── MATRIX-v0.2-core.schema.json
├── MATRIX-v0.2-cyber.ext.schema.json
├── MATRIX-v0.2-procurement.ext.schema.json
└── MATRIX-v0.2-Technical-Note.md

File	Description

README.md	Repository introduction and usage guide.
MATRIX-v0.2-core.schema.json	Core event record schema shared by all MATRIX event records.
MATRIX-v0.2-cyber.ext.schema.json	Cyber incident triage extension for public-sector cybersecurity workflows.
MATRIX-v0.2-procurement.ext.schema.json	Public procurement review extension for AI-assisted procurement analysis.
MATRIX-v0.2-Technical-Note.md	Technical note explaining the schema architecture and research context.



---

5. Architecture

MATRIX v0.2 follows a core-plus-extensions model.

The core schema defines the fields common to every governance event. Domain extensions add fields specific to a given institutional context.

An event record always validates against:

1. MATRIX-v0.2-core.schema.json


2. one domain extension, when applicable



┌─────────────────────────────────────┐
                  │      MATRIX v0.2 Core Schema        │
                  │                                     │
                  │  event identity                     │
                  │  timestamping                       │
                  │  hash chain                         │
                  │  AI system reference                │
                  │  input/output references            │
                  │  human validation                   │
                  │  fail-closed state                  │
                  │  audit status                       │
                  │  escalation status                  │
                  │  responsibility owner               │
                  └──────────────┬──────────────────────┘
                                 │
                domain_extension │
                                 │
              ┌──────────────────┴──────────────────┐
              │                                     │
   ┌──────────▼───────────┐             ┌───────────▼──────────┐
   │ Cyber Extension      │             │ Procurement Extension│
   │                      │             │                      │
   │ incident triage      │             │ tender review        │
   │ SOC validation       │             │ risk indicators      │
   │ CSIRT notification   │             │ compliance scoring   │
   │ regulatory reporting │             │ oversight body       │
   │ cyber fail-closed    │             │ contestation         │
   └──────────────────────┘             └──────────────────────┘

Event records are chained through previous_event_hash and trace_hash, producing a tamper-evident sequence suitable for institutional audit and event-chain reconstruction.


---

6. Core Schema

MATRIX-v0.2-core.schema.json defines the mandatory base structure for every MATRIX event record.

Field	Purpose

schema_version	Constant identifier of the MATRIX core schema version.
event_id	Unique identifier of the event record. UUIDv7 is recommended for time-ordered replay consistency.
event_timestamp	RFC 3339 / ISO 8601 UTC timestamp of the event.
domain_extension	Declares the applicable domain: generic, institutional, cyber_incident, or procurement.
canonicalization_method	Method used to canonicalize the record before hashing.
hash_algorithm	Cryptographic hash algorithm used for event-chain integrity.
previous_event_hash	Hash of the previous event in the chain.
trace_hash	Hash of the current canonicalized event payload.
AI_system_used	Object identifying the AI system, model, provider, version, and role.
input_reference	Privacy-preserving reference to the input artefact.
output_reference	Privacy-preserving reference to the output artefact.
human_validation	Object recording human validation of the event or output.
retention_requirement	Object defining retention period, legal basis, and disposal action.
drift_indicator	Object recording whether model, behavioural, or distributional drift was detected.
fail_closed	Object declaring whether fail-closed governance is enabled and whether it was triggered.
audit_status	Current audit lifecycle state of the event.
escalation_status	Current escalation state of the event.
responsibility_owner	Object identifying the accountable human or institutional role.



---

7. Cyber Incident Extension

MATRIX-v0.2-cyber.ext.schema.json extends the core schema for AI-assisted public-sector cybersecurity incident triage.

It is used when:

{
  "domain_extension": "cyber_incident"
}

The cyber extension is derived from Test 002: regional cybersecurity incident triage.

It contains no offensive cyber content, no exploit instructions, no malware guidance, and no raw technical artefacts that would enable cyber abuse.

Field	Purpose

incident_id	Non-personal institutional identifier of the cyber incident.
alert_source	High-level category of the detection or alerting source.
incident_severity	Institutional severity classification.
confidence_score	Confidence score for the AI-assisted or analyst-supported triage assessment.
threat_vector	High-level threat category only.
affected_services	References or identifiers of affected public-sector services.
regulatory_report_status	Status of mandatory regulatory reporting obligations.
containment_action_reference	Reference to a containment action record.
communication_status	Status of internal or external institutional communication.
SOC_validation	Human SOC analyst validation status.
CSIRT_notification_status	Status of CSIRT / CERT notification or coordination.
post_incident_review_reference	Reference to the post-incident review record.
fail_closed_cyber_reason	Controlled reason for triggering cyber-specific fail-closed governance.



---

8. Procurement Extension

MATRIX-v0.2-procurement.ext.schema.json extends the core schema for AI-assisted public procurement review.

It is used when:

{
  "domain_extension": "procurement"
}

The procurement extension is derived from Test 003: AI-assisted public procurement review.

It contains no confidential supplier data, no raw procurement documents, and no mechanism for opaque supplier exclusion without human review.

Field	Purpose

procurement_case_id	Non-personal identifier of the procurement review case.
tender_reference	Reference to the tender or call for proposals.
supplier_reference	Pseudonymous or institutional reference to the supplier or economic operator.
procurement_stage	Stage of the procurement lifecycle.
risk_indicator	Structured non-discriminatory procurement risk indicator.
compliance_score	Structured compliance assessment.
conflict_of_interest_flag	Potential or confirmed conflict-of-interest indicator.
procurement_integrity_status	Overall procurement integrity status.
human_procurement_validation	Human-in-the-loop procurement validation record.
oversight_body_status	Status of independent oversight body involvement.
appeal_or_contestation_status	Status of appeal or contestation mechanisms.
audit_trail_reference	Reference to the audit trail entry.
fail_closed_procurement_reason	Procurement-specific fail-closed governance rationale.
procurement_decision_effect	Effect of the AI-assisted output on the procurement process.



---

9. Governance Principles

MATRIX v0.2 is designed around the following principles.

Human Oversight

Every MATRIX event must preserve human oversight. AI systems may support institutional analysis, but they do not replace human judgment.

Legal Responsibility

Every event must identify a responsibility_owner. Responsibility remains attributable to a human or accountable institution.

Institutional Accountability

Records are bound to institutional roles, not autonomous AI authority.

Auditability

Records are structured to support post-hoc review, internal audit, external audit, and institutional oversight.

Traceability

Every event links input references, output references, AI system metadata, human validation, escalation state, audit state, and responsibility ownership.

Contestability

Procurement and institutional decision-preparation contexts require review, appeal, contestation, and oversight pathways.

Privacy-by-Design

MATRIX records references, identifiers, URIs, and hashes. They do not embed raw personal data or confidential content.

Fail-Closed Governance

If required governance conditions are missing, invalid, uncertain, or unsafe, the event must be treated as fail-closed and must not be used to support a decision.

Drift Control

The drift_indicator object supports lifecycle monitoring of AI behaviour and helps identify degraded model performance or changed operating conditions.


---

10. Privacy-by-Design

MATRIX v0.2 records references, not payloads.

The core schema uses:

input_reference

output_reference

retention_requirement


to preserve auditability without embedding raw personal data, confidential procurement content, incident artefacts, or sensitive operational details.

The authoritative data remains in the institution's existing systems, under the applicable legal, procedural, and retention regime.

MATRIX records only the minimum trace required to verify:

which event occurred;

when it occurred;

which AI system was involved;

which input and output artefacts were referenced;

whether human validation occurred;

whether fail-closed governance was triggered;

which role owned responsibility;

whether audit or escalation was required.



---

11. Human Oversight and Public Authority Constraints

MATRIX v0.2 supports AI-assisted decision-preparation only.

It does not represent, enable, or authorize automated public authority decisions.

The legal and institutional decision remains with the responsible human authority.

The schema enforces this through:

mandatory human_validation;

mandatory responsibility_owner;

escalation_status for oversight pathways;

fail_closed semantics that block AI-assisted continuation when governance conditions fail;

cyber-specific SOC_validation;

cyber-specific CSIRT_notification_status;

procurement-specific human_procurement_validation;

procurement-specific oversight_body_status;

procurement-specific appeal_or_contestation_status.


AI systems in MATRIX are assistive, advisory, or monitoring components. They are not public authority decision-makers.


---

12. Example Event Record

The following is an illustrative MATRIX core event record.

It contains no personal data, no confidential procurement data, and no offensive cyber content.

{
  "schema_version": "matrix-v0.2-core",
  "event_id": "550e8400-e29b-41d4-a716-446655440000",
  "event_timestamp": "2025-01-01T09:15:00Z",
  "domain_extension": "generic",
  "canonicalization_method": "JCS-RFC8785",
  "hash_algorithm": "SHA-256",
  "previous_event_hash": "0000000000000000000000000000000000000000000000000000000000000000",
  "trace_hash": "a3f1c4d2e5b6a7980c1d2e3f4a5b6c7d8e9f0a1b2c3d4e5f6a7b8c9d0e1f2a3b",
  "AI_system_used": {
    "system_id": "research-llm-ref-001",
    "version": "test-version",
    "provider": "research-provider",
    "role": "assistive"
  },
  "input_reference": "ref://institution/case/2025/0001/input",
  "output_reference": "ref://institution/case/2025/0001/output",
  "human_validation": {
    "validated": true,
    "validator_id": "role-case-officer-A",
    "validation_timestamp": "2025-01-01T09:20:00Z",
    "validation_notes_reference": "ref://institution/case/2025/0001/validation"
  },
  "retention_requirement": {
    "retention_period_days": 1825,
    "legal_basis": "institutional-research-retention-policy",
    "disposal_action": "review"
  },
  "drift_indicator": {
    "drift_detected": false,
    "drift_type": "none",
    "drift_score": 0,
    "detection_method_reference": "ref://institution/drift-monitoring/not-applicable"
  },
  "fail_closed": {
    "enabled": true,
    "triggered": false,
    "reason": "none"
  },
  "audit_status": "pending",
  "escalation_status": "none",
  "responsibility_owner": {
    "owner_id": "role-case-officer-A",
    "owner_role": "case_officer",
    "organisation": "research-institution-placeholder"
  }
}


---

13. Validation

Each MATRIX v0.2 schema is a standard JSON Schema Draft 2020-12 document and can be validated with any compatible validator.

A typical validation flow is:

1. Validate the event record against MATRIX-v0.2-core.schema.json.


2. Read domain_extension.


3. If domain_extension is cyber_incident, validate the domain payload against MATRIX-v0.2-cyber.ext.schema.json.


4. If domain_extension is procurement, validate the domain payload against MATRIX-v0.2-procurement.ext.schema.json.


5. Verify trace_hash by recomputing the hash over the canonicalized event record using canonicalization_method.


6. Verify previous_event_hash against the prior event in the event chain.


7. Verify human_validation.


8. Verify responsibility_owner.


9. Verify fail_closed.



Records that fail validation, hash verification, required human validation, or responsibility attribution must be treated as fail-closed and must not be used to support an institutional decision.

Example validation using ajv:

ajv validate \
  -s MATRIX-v0.2-core.schema.json \
  -d examples/event.generic.json \
  --spec=draft2020


---

14. Research Status

MATRIX v0.2 is a research artefact.

It has not been deployed in any public authority production environment.

The schemas are intended for:

academic review;

AI safety research;

governance research;

controlled institutional experimentation;

audit-design analysis;

responsible-deployment research.


The v0.2 package consolidates findings from Tests 001, 002, and 003 and remains subject to revision.

No certification, regulatory approval, legal compliance determination, or production readiness is claimed.


---

15. Roadmap

Planned work includes:

formal validation of the schemas against synthetic test corpora;

creation of worked examples for each domain;

a reference canonicalization and hashing implementation;

a reference validator;

a controlled vocabulary appendix;

EU legal-alignment notes;

additional domain extensions;

improved drift, escalation, and contestation modelling;

conformance tests for fail-closed behaviour;

structured research reporting for external review.


Candidate future extensions include:

administrative appeals;

social benefits review;

regulatory supervision;

infrastructure monitoring;

judicial preparation support;

emergency coordination.



---

16. License

To be defined in the repository LICENSE file.

Until a license is specified, the schemas and documentation are provided for research and review purposes only.


---

17. Contact

For research collaboration, governance review, or schema feedback, please use the repository issue tracker or the contact channel indicated in the parent repository.


---

MATRIX is a research framework for verifiable AI governance.

It is not a deployed public-sector system.

It supports AI-assisted decision-preparation, not automated public authority decisions.


