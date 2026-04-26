# MATRIX v0.2 Schemas

This directory contains the JSON Schema files for the MATRIX v0.2 research package.

MATRIX v0.2 is a research-stage schema architecture for traceability-by-construction in AI-assisted institutional environments.

The schemas define structured, auditable, and responsibility-preserving event records for AI-assisted decision-preparation.

---

## Schema Files

| File | Purpose |
|---|---|
| `MATRIX-v0.2-core.schema.json` | Core event record schema shared by all MATRIX events. |
| `MATRIX-v0.2-cyber.ext.schema.json` | Cyber incident triage domain extension. |
| `MATRIX-v0.2-procurement.ext.schema.json` | Public procurement review domain extension. |

---

## Core Schema

The core schema defines the minimum governance structure required for every MATRIX event record.

It includes:

- event identity;
- timestamping;
- domain extension selection;
- canonicalization method;
- hash algorithm;
- previous event hash;
- current trace hash;
- AI system reference;
- input reference;
- output reference;
- human validation;
- retention requirement;
- drift indicator;
- fail-closed state;
- audit status;
- escalation status;
- responsibility owner.

The core schema is located at:

```text
MATRIX-v0.2-core.schema.json


---

Cyber Extension

The cyber extension supports AI-assisted public-sector cybersecurity incident triage.

It includes:

incident identifier;

alert source;

incident severity;

confidence score;

high-level threat vector;

affected services;

regulatory report status;

containment action reference;

communication status;

SOC validation;

CSIRT notification status;

post-incident review reference;

cyber-specific fail-closed reason.


The cyber extension is located at:

MATRIX-v0.2-cyber.ext.schema.json

It is used when the core event contains:

{
  "domain_extension": "cyber_incident"
}


---

Procurement Extension

The procurement extension supports AI-assisted public procurement review.

It includes:

procurement case identifier;

tender reference;

supplier reference;

procurement stage;

risk indicator;

compliance score;

conflict-of-interest flag;

procurement integrity status;

human procurement validation;

oversight body status;

appeal or contestation status;

audit trail reference;

procurement-specific fail-closed reason;

procurement decision effect.


The procurement extension is located at:

MATRIX-v0.2-procurement.ext.schema.json

It is used when the core event contains:

{
  "domain_extension": "procurement"
}


---

Validation Model

A MATRIX event should be validated in this order:

1. Validate the core event against MATRIX-v0.2-core.schema.json.


2. Read domain_extension.


3. If domain_extension is cyber_incident, validate the cyber extension payload against MATRIX-v0.2-cyber.ext.schema.json.


4. If domain_extension is procurement, validate the procurement extension payload against MATRIX-v0.2-procurement.ext.schema.json.


5. Verify hash-chain integrity through previous_event_hash and trace_hash.


6. Verify human validation and responsibility ownership.


7. Treat invalid records as fail-closed.




---

Research Status

These schemas are research artefacts.

They are not certified for production use and do not represent a deployed public-sector system.

MATRIX supports AI-assisted decision-preparation, not automated public authority decisions.

