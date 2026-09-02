# Interoperability

## Current state

**CURRENT:** The four STC-DT components are independently maintained projects. This repository does not claim a shared API, schema, protocol, exchange format, identity mechanism, deployment environment, or automated end-to-end workflow across them.

The Urban Digital Twin component contains internal typed boundaries, data-processing workflows, and a visualization-portability experiment. Those component-level capabilities do not establish interoperability with the other STC-DT components.

The Knowledge Graph component currently uses and exposes semantic information and exchange artifacts, including IFC-related schema information, UCKS YAML, and buildingSMART IDS XML. These are component-level capabilities; no operational exchange with the Geometry, Urban Digital Twin, or CCDT components is currently claimed.

Current interoperability information for the AI-Enabled Geometry component is **Pending contributor confirmation**.

The CCDT component currently uses in-memory Python models for its internal six-twin reference system. Its CDE abstraction, data schemas, external adapters, and import/export or message interfaces remain planned; no operational exchange with the other STC-DT components is currently claimed.

## Planned direction

**PLANNED:** Subject to contributor agreement, technical validation, and documented ownership, future ecosystem work may investigate:

- shared terminology and concept definitions;
- metadata and provenance requirements;
- documented input and output expectations;
- schemas, exchange conventions, or interface contracts;
- identifiers and semantic mappings;
- geometry and model exchange;
- validation and conformance practices;
- versioning and compatibility policies; and
- security, privacy, and access-control expectations.

These are research and coordination goals, not current capabilities or commitments to a specific technical design.

## Adoption process

A shared interface or protocol should be described as adopted only after:

1. participating components and responsible contributors are identified;
2. the use case, inputs, outputs, and data boundaries are documented;
3. terminology and expected behavior are agreed upon;
4. security, privacy, provenance, and governance implications are reviewed;
5. implementation or conformance evidence is available; and
6. versioning and maintenance responsibilities are recorded.

## Information still required

Remaining ecosystem-level needs are:

- complete confirmed information for the AI-Enabled Geometry component;
- specific cross-component interoperability use cases;
- identification of candidate existing formats or interfaces for shared exchange;
- security, privacy, provenance, and data-governance requirements; and
- maintainers responsible for cross-component decisions.

Until these needs are documented and validated, ecosystem-level interoperability remains planned and conceptual.
