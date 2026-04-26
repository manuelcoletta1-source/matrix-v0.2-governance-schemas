# MATRIX v0.2 Examples

This directory contains example event records for the MATRIX v0.2 research package.

The examples are synthetic and provided for documentation, validation, and research review purposes only.

They do not contain:

- personal data;
- confidential procurement data;
- operational cyber artefacts;
- exploit details;
- malware instructions;
- real public-sector records.

---

## Example Files

| File | Purpose |
|---|---|
| `event.generic.example.json` | Minimal generic MATRIX core event record. |
| `event.cyber.example.json` | Example combining a core event with the cyber incident extension. |
| `event.procurement.example.json` | Example combining a core event with the procurement extension. |

---

## Generic Example

The generic example demonstrates the minimum structure of a MATRIX core event record.

It includes:

- `schema_version`;
- `event_id`;
- `event_timestamp`;
- `domain_extension`;
- `canonicalization_method`;
- `hash_algorithm`;
- `previous_event_hash`;
- `trace_hash`;
- `AI_system_used`;
- `input_reference`;
- `output_reference`;
- `human_validation`;
- `retention_requirement`;
- `drift_indicator`;
- `fail_closed`;
- `audit_status`;
- `escalation_status`;
- `responsibility_owner`.

File:

```text
event.generic.example.json


---

Cyber Example

The cyber example demonstrates how a MATRIX core event can be combined with a cyber incident extension.

It includes a core_event object and a cyber_extension object.

The example represents a synthetic AI-assisted public-sector cybersecurity triage record.

File:

event.cyber.example.json


---

Procurement Example

The procurement example demonstrates how a MATRIX core event can be combined with a procurement extension.

It includes a core_event object and a procurement_extension object.

The example represents a synthetic AI-assisted public procurement review record.

File:

event.procurement.example.json


---

Validation Notes

The example files are intended to support future validation tooling.

A full validation workflow should:

1. validate the core event against schemas/MATRIX-v0.2-core.schema.json;


2. validate the domain extension against the corresponding extension schema;


3. verify previous_event_hash;


4. recompute and verify trace_hash;


5. verify human_validation;


6. verify responsibility_owner;


7. treat invalid or incomplete records as fail-closed.




---

Research Status

These examples are synthetic research artefacts.

They are not operational records.

They are not evidence of deployment in any public authority system.

MATRIX supports AI-assisted decision-preparation, not automated public authority decisions.

