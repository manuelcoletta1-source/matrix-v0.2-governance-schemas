# Changelog

All notable changes to the MATRIX v0.2 research schema package will be documented in this file.

This project follows a research-stage versioning model. Versions may change as the schema architecture, validation logic, examples, and documentation evolve.

---

## [0.2.0] - 2026-04-26

### Added

- Initial MATRIX v0.2 repository structure.
- Main repository `README.md`.
- MIT `LICENSE`.
- Core schema:
  - `schemas/MATRIX-v0.2-core.schema.json`
- Cyber incident extension:
  - `schemas/MATRIX-v0.2-cyber.ext.schema.json`
- Procurement extension:
  - `schemas/MATRIX-v0.2-procurement.ext.schema.json`
- Technical documentation:
  - `docs/MATRIX-v0.2-Technical-Note.md`
  - `docs/README.md`
- Schema documentation:
  - `schemas/README.md`
- Example records:
  - `examples/event.generic.example.json`
  - `examples/event.cyber.example.json`
  - `examples/event.procurement.example.json`
  - `examples/README.md`

### Research Basis

MATRIX v0.2 was derived from three controlled research tests:

- Test 001 — administrative AI decision-preparation.
- Test 002 — regional cybersecurity incident triage.
- Test 003 — AI-assisted public procurement review.

### Core Concepts Introduced

- Traceability-by-construction.
- Core-plus-extension schema architecture.
- Verifiable AI-assisted institutional event records.
- Human validation as a schema-level requirement.
- Responsibility ownership as a mandatory event field.
- Fail-closed governance semantics.
- Event-chain integrity using `previous_event_hash` and `trace_hash`.
- Privacy-by-design through `input_reference` and `output_reference`.
- Domain-specific extensions for cyber incident triage and procurement review.

### Status

MATRIX v0.2 is a research artefact.

It is not a deployed public-sector system.

It does not claim:

- production readiness;
- regulatory certification;
- legal compliance determination;
- security certification;
- procurement compliance approval.

MATRIX v0.2 supports AI-assisted decision-preparation, not automated public authority decisions.

---

## Planned

Future versions may include:

- reference validator;
- canonicalization and hashing implementation;
- controlled vocabulary appendix;
- EU legal-alignment note;
- additional domain extensions;
- conformance test suite;
- worked examples for each schema;
- synthetic test corpus;
- fail-closed state-machine specification;
- structured reporting template for external review.
