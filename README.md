# CDP User Demo

Demo project for Customer Data Platform (CDP) use cases, organized by delivery phase.

## Overview

This repository holds materials, assets, and working examples for CDP user scenarios. Work is split into phases so each use case can be developed, reviewed, and demoed independently.

### Phase 1

CSV on HDFS → Spark → SQL warehouse → reporting, with governance across the stack.

![Reference Architecture — User Demo Phase 1](./use-case-phase-1/images/UseCasePhase1.png)

### Phase 2

Oracle → NiFi ingestion (HDFS/CSV) → Spark → SQL warehouse → reporting, with governance across the stack.

![Reference Architecture — User Demo Phase 2](./use-case-phase-2/images/UseCasePhase2.png)

## Repository structure

```
CDPUserDemo/
├── README.md
├── use-case-phase-1/
│   ├── README.md       # Phase 1 use case (with setup screenshots)
│   ├── images/         # Architecture diagram + CAI / CDW / Hue screenshots
│   └── notebooks/      # Phase 1 notebooks
└── use-case-phase-2/
    ├── README.md       # Phase 2 use case
    └── images/         # Architecture diagram
```

| Directory | Purpose |
|-----------|---------|
| [`use-case-phase-1/`](./use-case-phase-1/) | Phase 1 use case materials and demos |
| [`use-case-phase-1/images/`](./use-case-phase-1/images/) | Phase 1 architecture + session / Hue screenshots |
| [`use-case-phase-1/notebooks/`](./use-case-phase-1/notebooks/) | Phase 1 Jupyter / analysis notebooks |
| [`use-case-phase-2/`](./use-case-phase-2/) | Phase 2 use case materials and demos |
| [`use-case-phase-2/images/`](./use-case-phase-2/images/) | Phase 2 architecture diagram |

## Getting started

1. Clone this repository.
2. Open [`use-case-phase-1/`](./use-case-phase-1/) for the Phase 1 lab (screenshots in the README walk through CAI session setup).
3. Follow the notes and assets inside that phase folder.

## Contributing

- Keep phase-specific work inside its phase directory.
- Prefer clear, descriptive file names for demos, scripts, and docs.
- Update this README when you add new top-level areas or change the phase layout.

## License

Licensed under the [Apache License, Version 2.0](./LICENSE).
