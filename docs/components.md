# Component Registry

The STC-DT ecosystem is organized around four independently maintained components. This registry separates verified current information from planned relationships and details awaiting contributor confirmation.

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

**PLANNED:** Future work may allow the Geometry, Urban Digital Twin, and CCDT components to resolve definitions and exchange requirements through agreed formats or protocols. No technical integration with those components is currently claimed.

## 2. AI-Enabled Geometry Generation and Interoperability

### Purpose

Support drone-to-BIM semantic segmentation and semantic processing for the AI-Enabled Geometry Generation and Interoperability dimension of STC-DT. The work builds on and is forked from the upstream [GARField codebase](https://github.com/chungmin99/garfield); not all source code in the component repository was newly authored by the component contributor.

### Current capabilities

**CURRENT:** The public research prototype documents:

- COLMAP structure-from-motion processing of drone imagery;
- GARField neural-radiance-field grouping features;
- GARField-Gauss / 3D Gaussian Splatting rendering;
- orthographic projection of grouping features to point clouds;
- Optuna-optimized HDBSCAN clustering;
- semantic labeling with a fine-tuned SAM 3 model;
- cluster-to-mask matching using intersection-over-union and majority voting;
- semantic point-cloud generation; and
- Snakemake orchestration of the documented pipeline stages.

### Status

Public research prototype; repository documentation and licensing are being finalized by the contributor. The repository is not presented as production-ready.

### Example input, process, and output

- **Inputs:** drone images placed under a project image directory and dataset paths and parameters supplied through `pipeline/config.yaml`.
- **Process:** COLMAP produces camera poses and a sparse point cloud; GARField and GARField-Gauss provide parallel grouping-feature and rendering branches; orthographic projection, Optuna/HDBSCAN clustering, fine-tuned SAM 3 labeling, and cluster-to-mask matching are orchestrated through Snakemake.
- **Outputs:** documented final outputs include `semantic_pointcloud.ply`, `semantic_labels.json`, and per-class PLY files. Intermediate outputs include grouping features, cluster labels, clustered point clouds, optimization results, rendered labeling views, and segmentation masks.

### Formats or interfaces

Documented formats and technologies include drone images, YAML configuration, NumPy arrays, PLY point clouds, JSON semantic labels, COLMAP, GARField, neural radiance fields, 3D Gaussian Splatting, Optuna, HDBSCAN, SAM 3, and Snakemake.

### Repository

[github.com/Ehs9449/garfield](https://github.com/Ehs9449/garfield)

### Contributors

**Ehsan Agha Ebrahimi** provided and is finalizing this component repository. The repository is a fork of [`chungmin99/garfield`](https://github.com/chungmin99/garfield) and retains upstream GARField code and attribution.

### License

**Pending contributor confirmation**

The repository's current `LICENSE` contains inherited MIT license text and a UC Berkeley copyright notice from the upstream GARField codebase. This is not represented here as the finalized licensing structure for the component.

### Related publications

The repository README currently provides a 2026 `@misc` citation entry for *Unsupervised Building Component Discovery via Orthographic Feature Projection from Neural Radiance Fields* and acknowledges the upstream GARField project. This entry is not represented as a confirmed archival publication; no archival publication is claimed unless contributor-confirmed.

### Relationship to STC-DT

This independently maintained research prototype is the proposed AI-Enabled Geometry Generation and Interoperability component of STC-DT. Its future relationship to shared terminology, interfaces, or protocols must be defined, documented, and validated with the other component contributors. No implemented technical integration or verified interoperability with the Knowledge Graph, Urban Digital Twin, or CCDT components is currently claimed.

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

The project is a public open-source research prototype with explicitly identified mock, experimental, external, and planned elements. Release [`v0.1.0`](https://github.com/vijaybkhot/urban-digital-twin-interoperability/releases/tag/v0.1.0) is published under the Apache License 2.0, and the repository provides `CITATION.cff`.

The [hosted Vercel demo](https://urban-digital-twin-interoperability.vercel.app/) remains a research demonstration; it is not an operational emergency-management or production system.

It currently has no real LLM agent, connected COLMAP reconstruction backend, backend API, authentication, database, persisted project state, live sensors, or operational emergency feeds. Its public-data scenarios report mapped relationships and coverage, not current hazards, road conditions, evacuation guidance, or official determinations.

### Example input, process, and output

- **Inputs:** local JSON project configuration; selected local-image metadata; committed GeoJSON derived from OSM, FEMA NFHL, and USGS 3DEP sources; and configured GLB model assets.
- **Process:** deterministic browser checks, local acquisition/build scripts, spatial processing, validators, typed domain logic, and viewer adapters.
- **Outputs:** browser-rendered Cesium scenes, an experimental ArcGIS view, selectable details, validation logs, and documented contract examples. The browser workflow does not produce a real photogrammetric reconstruction.

### Formats or interfaces

Documented formats include JSON, GeoJSON, and viewer-ready GLB. PLY is recognized in reconstruction handoff documentation but is not rendered directly. Current external boundaries are `AgentProvider`, `ProjectConfigRepository`, `ReconstructionProvider`, and `ViewerAdapter`; the first and third do not represent connected production services.

### Repository

- Repository: [github.com/vijaybkhot/urban-digital-twin-interoperability](https://github.com/vijaybkhot/urban-digital-twin-interoperability)
- Release: [`v0.1.0`](https://github.com/vijaybkhot/urban-digital-twin-interoperability/releases/tag/v0.1.0)
- Live research demo: [urban-digital-twin-interoperability.vercel.app](https://urban-digital-twin-interoperability.vercel.app/)
- License: [Apache License 2.0](https://github.com/vijaybkhot/urban-digital-twin-interoperability/blob/main/LICENSE)
- Citation metadata: [`CITATION.cff`](https://github.com/vijaybkhot/urban-digital-twin-interoperability/blob/main/CITATION.cff)

### Contributors

The repository's verified [GitHub contribution record](https://github.com/vijaybkhot/urban-digital-twin-interoperability/graphs/contributors) lists [`vijaybkhot`](https://github.com/vijaybkhot) and [`zsradox`](https://github.com/zsradox) as contributors at the time of this review.

### Related publications

The repository provides `CITATION.cff`. No project-specific archival publication is currently claimed.

### Relationship to STC-DT

The repository identifies itself as the intended Urban Digital Twin Interoperability component. Its current contribution is an independent research testbed for geospatial-data integration, typed viewer boundaries, scientific provenance, visualization portability, and reproducible local datasets. It does not implement umbrella-level STC-DT integration.

### Verification basis

This summary was reviewed against the component's public `main` branch, published [`v0.1.0`](https://github.com/vijaybkhot/urban-digital-twin-interoperability/releases/tag/v0.1.0) release at commit [`9b068f6`](https://github.com/vijaybkhot/urban-digital-twin-interoperability/commit/9b068f67faee8b3b4bf67eec97695848a1e8d889), relevant architecture and urban-resilience documentation, and public contribution record.

## 4. Coupled–Composable Digital Twin / Off-Site Construction

### Purpose

The [Coupled–Composable Digital Twin (CCDT) Framework for Off-Site Construction](https://github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction) investigates coordination among multiple semi-independent digital twins in off-site construction, with emphasis on cross-twin interactions, probabilistic reasoning, and system-of-systems decision support. Its initial reference use case is modular/manufactured housing.

### Current capabilities and documented current state

**CURRENT:** The public early research prototype currently provides:

- an in-memory Python registry and coordination layer for six reference twins: Planning, Procurement, Components Fabrication, Modules Manufacturing, Logistics, and Assembly;
- a generalized twin state tuple with digital, physical, sensor, action, reward, and event fields, plus timestamped state updates, event logging, snapshots, and timestep advancement;
- representations for PT–PT, DT–DT, PT–DT, and DT–PT interactions, including designed-versus-hidden flags and interaction filtering;
- initial research algorithms for Planning/Assembly schedule divergence, discrete Bayesian filtering of logistics state, probability-weighted assembly forecasts, mutual-information dependency detection, physical-coupling prediction, and rework/capacity/delivery-risk calculations; and
- a runnable 50-home / 200-module manufactured-housing demonstration using reference assumptions and synthetic demonstration parameters.

The documented research framework additionally frames temporal and cross-twin reasoning through Probabilistic Graphical Model and Dynamic Bayesian Network concepts and identifies six KPI domains: Cost, Time, Quality, Sustainability, Risk, and Safety. A fully integrated temporal PGM/DBN and KPI evaluation layer are not current implementations.

### Status

The README describes the repository as an **early research prototype / open-source foundation (v0.1)** and explicitly states that it is not a production control system. The repository has package and citation metadata at version `0.1.0`, but no tag or formal GitHub Release is currently published.

### Example input, process, and output

- **Inputs:** in-memory Python dictionaries for twin states, events, prior and transition probabilities, sensor likelihoods, schedule values, and demonstration coefficients.
- **Process:** build the six-twin reference system, register the four interaction classes, evaluate schedule synchronization, update a logistics posterior from sensor evidence, propagate expected delay to an assembly forecast, and estimate rework-related capacity and delivery risk.
- **Outputs:** Python objects and dictionaries for twin state, interaction and event records, posterior probabilities, schedule-sync results, forecast values, and risk estimates; the included example prints a concise demonstration summary.

The repository states that its demonstration probabilities, coefficients, thresholds, and scenario parameters are not empirically calibrated unless supporting validation data are added.

### Formats or interfaces

The current package targets Python 3.10 or newer and uses Python dataclasses, dictionaries, and enums as in-memory interfaces. JSON schemas, external platform import/export, message/event interfaces, BIM/IFC, GIS, GPS/RFID/IoT adapters, and a Common Data Environment abstraction remain planned.

### Repository

- Repository: [github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction](https://github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction)
- License file: [Apache License 2.0](https://github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction/blob/main/LICENSE)
- Citation metadata: [`CITATION.cff`](https://github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction/blob/main/CITATION.cff)
- Architecture documentation: [`docs/architecture.md`](https://github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction/blob/main/docs/architecture.md)
- Roadmap: [`ROADMAP.md`](https://github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction/blob/main/ROADMAP.md)

### Contributors and maintainers

The repository README identifies **Mohannad Daqdouq** and **Yongcheol Lee**, both affiliated there with Louisiana State University. Its package and citation metadata list both as authors.

### License and release

An Apache License 2.0 `LICENSE` file is present, and the package and citation metadata identify `Apache-2.0`. The README describes Apache-2.0 as planned for the initial public release, while the roadmap records the licensing foundation as implemented. No tag or formal GitHub Release is currently published, so the repository's v0.1/`0.1.0` metadata is not represented here as a published release.

### Testing and validation

Seven pytest tests cover the six-twin reference system, all four interaction types, state updates and event logging, schedule divergence and reconciliation, Bayesian sensor updates and assembly cross-updates, mutual-information dependency detection, and PT–PT / DT–PT ripple models. GitHub Actions is configured to run the suite on Python 3.10, 3.11, and 3.12.

These tests verify the initial implementation mechanics and numerical examples; they do not establish empirical calibration, production readiness, or cross-project validation.

### Related documentation and publications

The repository includes architecture documentation, `ROADMAP.md`, and `CITATION.cff`. The README says the implementation aligns with a CCDT Rev10 study manuscript and that citation metadata will be updated when the associated manuscript/repository release is finalized; no finalized archival publication is claimed here.

### Relationship to STC-DT

**CURRENT:** CCDT adds a multi-digital-twin / system-of-systems research perspective to the STC-DT umbrella as an independently maintained component. No implemented technical integration with the Knowledge Graph, Geometry, or Urban Digital Twin components is currently claimed.

**PLANNED:** The CCDT roadmap identifies further composable-twin lifecycle work, inferred interaction graphs and alerts, integrated temporal PGM/DBN cross-updates, CDE and data-exchange abstractions, external adapters, calibration, validation, optimization, and production hardening. These remain component-level research plans and do not imply an adopted STC-DT interface or working cross-component integration.

### Verification basis

This summary was reviewed against the component's public `main` branch at commit [`1c25c07`](https://github.com/m-daqdouq/Coupled-Composable-Digital-Twin-Framework-for-Off-Site-Construction/commit/1c25c07510727075779be935166bb888a298c1a0), including its README, license and notice files, repository structure, source package, example, tests, CI workflow, architecture documentation, roadmap, package metadata, and citation metadata. GitHub repository metadata and the tags and releases endpoints were also checked for release status.
