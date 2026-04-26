# MATRIX v0.2 Validation

This directory is reserved for validation documentation, validation scripts, and future reference tooling for the MATRIX v0.2 research schema package.

MATRIX v0.2 defines JSON Schemas for traceability-by-construction in AI-assisted institutional environments.

Validation is intended to ensure that MATRIX event records preserve:

- schema conformance;
- event-chain integrity;
- human validation;
- responsibility ownership;
- privacy-by-design;
- fail-closed governance;
- auditability;
- traceability.

---

## Current Status

At v0.2, this directory contains the validation roadmap only.

Reference validation scripts are planned for a future version.

No production validator is currently provided.

---

## Validation Objectives

A MATRIX validation workflow should verify:

1. Core schema conformance.
2. Domain extension conformance.
3. Hash-chain integrity.
4. Canonicalization consistency.
5. Human validation presence.
6. Responsibility owner presence.
7. Fail-closed state.
8. Audit and escalation status.
9. Privacy-preserving reference structure.
10. Retention requirement presence.

---

## Core Validation

Every MATRIX event must validate against:

```text
schemas/MATRIX-v0.2-core.schema.json

The core schema checks the mandatory structure of a MATRIX event record, including:

schema_version;

event_id;

event_timestamp;

domain_extension;

canonicalization_method;

hash_algorithm;

previous_event_hash;

trace_hash;

AI_system_used;

input_reference;

output_reference;

human_validation;

retention_requirement;

drift_indicator;

fail_closed;

audit_status;

escalation_status;

responsibility_owner.



---

Domain Extension Validation

After core validation, the validator should read:

domain_extension

Then it should apply the corresponding extension schema.

Cyber Incident

If:

{
  "domain_extension": "cyber_incident"
}

validate the cyber payload against:

schemas/MATRIX-v0.2-cyber.ext.schema.json

Procurement

If:

{
  "domain_extension": "procurement"
}

validate the procurement payload against:

schemas/MATRIX-v0.2-procurement.ext.schema.json

Generic

If:

{
  "domain_extension": "generic"
}

no domain extension is required.


---

Hash-Chain Verification

A MATRIX validator should verify:

previous_event_hash;

trace_hash;

canonicalization_method;

hash_algorithm.


The expected process is:

1. remove or ignore trace_hash before hashing the current event payload;


2. canonicalize the remaining event record using canonicalization_method;


3. compute the digest using hash_algorithm;


4. compare the computed digest with trace_hash;


5. compare previous_event_hash with the prior event in the event chain.



At v0.2, the canonical method is:

JCS-RFC8785

Supported hash algorithms are:

SHA-256
SHA-512
BLAKE3


---

Human Validation Check

A valid MATRIX event must include:

human_validation

The validator should verify that:

the field exists;

the field is an object;

validated is present;

when validation is required, the event does not proceed without human validation;

validation references do not embed raw personal data.


For public-sector or high-impact institutional workflows, missing human validation should trigger fail-closed treatment.


---

Responsibility Owner Check

A valid MATRIX event must include:

responsibility_owner

The validator should verify that:

owner_id is present;

organisation is present;

responsibility is assigned to a human-attributable role or accountable institution;

AI systems are not treated as responsibility owners.



---

Fail-Closed Check

A valid MATRIX event must include:

fail_closed

The validator should verify:

enabled;

triggered;

reason, where applicable.


Records should be treated as fail-closed if:

schema validation fails;

hash verification fails;

human validation is missing where required;

responsibility owner is missing;

privacy constraints are violated;

domain extension validation fails;

audit or escalation requirements are inconsistent;

the event attempts to support automated public authority decision-making.



---

Privacy-by-Design Check

MATRIX validation should reject or flag records that embed:

raw personal data;

confidential procurement data;

offensive cyber content;

exploit payloads;

malware instructions;

credentials;

API keys;

secrets;

raw incident artefacts;

unnecessary institutional content.


MATRIX records should use:

references;

identifiers;

URIs;

hashes;

pseudonymous role identifiers.



---

Example Validation Flow

1. Load event record.
2. Validate core_event or event record against MATRIX-v0.2-core.schema.json.
3. Read domain_extension.
4. Validate cyber_extension or procurement_extension when applicable.
5. Recompute trace_hash.
6. Verify previous_event_hash.
7. Verify human_validation.
8. Verify responsibility_owner.
9. Verify fail_closed.
10. Return VALID or FAIL_CLOSED.


---

Planned Tooling

Future versions may include:

JSON Schema validation script;

canonicalization and hashing script;

example event validator;

fail-closed conformance checker;

privacy reference checker;

domain extension validator;

validation report generator;

CI workflow for schema validation.



---

Research Status

Validation tooling is planned but not yet implemented in v0.2.

This directory currently documents the intended validation model.

MATRIX v0.2 remains a research-stage package and is not certified for production use.


---

MATRIX supports AI-assisted decision-preparation, not automated public authority decisions.

