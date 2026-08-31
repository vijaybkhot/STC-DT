# Component Registry

The STC-DT ecosystem is organized around three independently maintained components. This registry separates verified current information from planned relationships and details awaiting contributor confirmation.

## 1. Knowledge Graph / Semantic Interoperability

### Purpose

The [AEC Knowledge Graph](https://github.com/halilyasavul/aec-knowledge-graph) is the Knowledge Graph / Semantic Interoperability component of STC-DT. Within its independently maintained repository, it provides semantic capabilities for built-environment entity definitions, properties, relationships, and exchange requirements.

### Current capabilities

**CURRENT:** The public prototype currently supports:

- IFC 4.3 knowledge-graph generation in Neo4j;
- natural-language querying grounded in graph data through GraphRAG;
- conversational capture of new AEC concepts in the UCKS knowledge schema;
- mapping from UCKS concepts to IFC; and
- export of buildingSMART Information Delivery Specification (IDS) files validated against an XSD schema.

### Status

The component is a public open-source prototype. Release [`v0.1.0`](https://github.com/halilyasavul/aec-knowledge-graph/releases/tag/v0.1.0) is available under the Apache License 2.0. The [live demo](https://aec-knowledge-engine-16881077631.us-central1.run.app) is publicly accessible without an account.

### Example input, process, and output

- **Inputs:** IFC 4.3 bSDD JSON and EXPRESS schema data; natural-language IFC questions; plain-language descriptions of new AEC concepts; and UCKS YAML entities.
- **Process:** schema ingestion into Neo4j, graph-grounded retrieval and querying, UCKS entity validation and mapping, and IDS generation with XSD validation.
- **Outputs:** graph-grounded answers with supporting graph data; validated UCKS YAML and graph representations; and downloadable buildingSMART IDS XML. The repository includes worked prompts and a generated, XSD-validated IDS example.

### Formats or interfaces

Confirmed formats and technologies include IFC 4.3, bSDD JSON, EXPRESS, Neo4j and Cypher, GraphRAG, UCKS YAML, buildingSMART IDS XML and XSD, Python, Flask, and a Gemini-backed language-model agent.

### Repository

- Repository: [github.com/halilyasavul/aec-knowledge-graph](https://github.com/halilyasavul/aec-knowledge-graph)
- Live demo: [aec-knowledge-engine-16881077631.us-central1.run.app](https://aec-knowledge-engine-16881077631.us-central1.run.app)

### Contributors

The component repository identifies **Halil Yasavul** as responsible for design and development. Its Git history preserves the development record, and contribution guidance is available in the repository.

### Release and license

- Current release: [`v0.1.0`](https://github.com/halilyasavul/aec-knowledge-graph/releases/tag/v0.1.0)
- License: [Apache License 2.0](https://github.com/halilyasavul/aec-knowledge-graph/blob/main/LICENSE)

### Testing and validation

The automated pytest suite covers the EXPRESS parser, IDS generation, XSD validation, and UCKS schema models. GitHub Actions runs continuous integration on pushes and pull requests. Generated IDS files are validated against the buildingSMART `ids.xsd` before being returned.

### Related documentation and publications

The repository includes a whitepaper, deployment guide, API reference, UCKS schema draft, and `CITATION.cff`. No related project publication is currently listed.

### Relationship to STC-DT

**CURRENT:** The component independently implements the semantic and knowledge-graph capabilities described above within its own repository and serves as the Knowledge Graph / Semantic Interoperability component of STC-DT.

**PLANNED:** Future work may allow the Geometry and Urban Digital Twin components to resolve definitions and exchange requirements through agreed formats or protocols. No technical integration with those components is currently claimed.

## 2. AI-Enabled Geometry Generation and Interoperability

### Purpose

Support the AI-enabled geometry-generation and geometry-interoperability dimension of the proposed STC-DT ecosystem.

### Current capabilities

**Pending contributor confirmation**

### Status

Public release in preparation

### Example input, process, and output

**Pending contributor confirmation**

### Formats or interfaces

**Pending contributor confirmation**

### Repository

**Pending contributor confirmation**

### Contributors

**Pending contributor confirmation**

### Related publications

**Pending contributor confirmation**

### Relationship to STC-DT

This is one of the three intended STC-DT components. Its future relationship to shared terminology, interfaces, or protocols must be defined and agreed upon by contributors. No implemented integration is currently claimed.

## 3. Urban Digital Twin Interoperability

### Purpose

The [Urban Digital Twin Interoperability Research Prototype](https://github.com/vijaybkhot/urban-digital-twin-interoperability) investigates config-driven geospatial digital-twin visualization and interoperability. It separates public-data acquisition and scientific processing from structured domain state and visualization clients.

### Current capabilities

The public repository documents:

- a React and TypeScript application with five isolated modes using a CesiumJS viewer boundary;
- typed, viewer-independent domain contracts and provider interfaces;
- browser-local image metadata and deterministic readiness checks without image upload;
- mock agent and reconstruction providers, including a simulated reconstruction lifecycle;
- visualization of configured GLB assets, annotations, and measurement links;
- manual Node.js workflows that acquire, process, and validate OpenStreetMap, FEMA National Flood Hazard Layer, and USGS 3DEP information into committed local GeoJSON artifacts;
- an implemented urban-resilience research scenario for Grand Isle, Port Fourchon, and selected Louisiana Highway 1 study areas; and
- an isolated experimental ArcGIS SceneView client that consumes selected processed urban GeoJSON without recomputing classifications.

### Status and limitations

The project is an implemented research prototype with explicitly identified mock, experimental, external, and planned elements. It is not a production digital-twin pipeline.

It currently has no real LLM agent, connected COLMAP reconstruction backend, backend API, authentication, database, persisted project state, live sensors, or operational emergency feeds. Its public-data scenarios report mapped relationships and coverage, not current hazards, road conditions, evacuation guidance, or official determinations.

### Example input, process, and output

- **Inputs:** local JSON project configuration; selected local-image metadata; committed GeoJSON derived from OSM, FEMA NFHL, and USGS 3DEP sources; and configured GLB model assets.
- **Process:** deterministic browser checks, local acquisition/build scripts, spatial processing, validators, typed domain logic, and viewer adapters.
- **Outputs:** browser-rendered Cesium scenes, an experimental ArcGIS view, selectable details, validation logs, and documented contract examples. The browser workflow does not produce a real photogrammetric reconstruction.

### Formats or interfaces

Documented formats include JSON, GeoJSON, and viewer-ready GLB. PLY is recognized in reconstruction handoff documentation but is not rendered directly. Current external boundaries are `AgentProvider`, `ProjectConfigRepository`, `ReconstructionProvider`, and `ViewerAdapter`; the first and third do not represent connected production services.

### Repository

[github.com/vijaybkhot/urban-digital-twin-interoperability](https://github.com/vijaybkhot/urban-digital-twin-interoperability)

### Contributors

The repository's verified [GitHub contribution record](https://github.com/vijaybkhot/urban-digital-twin-interoperability/graphs/contributors) lists [`vijaybkhot`](https://github.com/vijaybkhot) and [`zsradox`](https://github.com/zsradox) as contributors at the time of this review.

### Related publications

The repository states that no project-specific archival publication, `CITATION.cff`, or archived software release is currently claimed.

### Relationship to STC-DT

The repository identifies itself as the intended Urban Digital Twin Interoperability component. Its current contribution is an independent research testbed for geospatial-data integration, typed viewer boundaries, scientific provenance, visualization portability, and reproducible local datasets. It does not implement umbrella-level STC-DT integration.

### Verification basis

This summary was reviewed against the component's public `main` branch README, architecture documentation, accepted urban-resilience data guardrails, roadmap, and contribution record at commit [`1350dd2`](https://github.com/vijaybkhot/urban-digital-twin-interoperability/commit/1350dd25e9d05d48776dba1c87f46265c380833d).
