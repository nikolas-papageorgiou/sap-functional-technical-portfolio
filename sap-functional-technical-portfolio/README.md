# SAP Functional & Technical Portfolio

A learning portfolio that walks through four SAP areas of a utilities company, one at a time.
For every solution it shows three things: the business problem, the functional solution and the technical solution.

Author: [nikolas-papageorgiou](https://github.com/nikolas-papageorgiou)

## Scope

- Target release: SAP S/4HANA 2023 on-premise with SAP for Utilities (IS-U).
- All solutions belong to one fictional company, [Meltemi Grid S.A.](docs/company-profile.md), so the repository reads as a single story.

## Roadmap

| # | Area | Folder | Status |
|---|------|--------|--------|
| 1 | AWM – Notifications | [01-awm-notifications](01-awm-notifications/) | In progress |
| 2 | Plant Maintenance | 02-plant-maintenance | Not started |
| 3 | FI-CA and Billing | 03-fica-billing | Not started |
| 4 | Document Management | 04-document-management | Not started |
| – | Cross-area final scenario | – | Not started |

## How to read a solution

Each solution lives in `<area>/solutions/<nn>-<slug>/` and contains:

| File | Content |
|------|---------|
| `README.md` | The problem in five lines and how to read the solution |
| `functional-solution.md` | Business context, process, fit-gap, customizing, business rules, test scenarios |
| `technical-solution.md` | Architecture, data model, design decisions, objects, error handling, tests |
| `test-evidence.md` | What was executed, where, and with what result |
| `src/` | ABAP and CDS sources |

Supporting documents:

- [Company profile](docs/company-profile.md)
- [Glossary](docs/glossary.md)
- [Integration map](docs/integration-map.md)
- [Templates](docs/templates/)

## Execution status

Every solution states its status explicitly:

- **Tested on** `<system and release>`: the code was executed there and the evidence is in `test-evidence.md`.
- **Designed, not executed**: the design and the code were written without access to a suitable system.

No S/4HANA system with IS-U is available for this portfolio. Parts that are pure ABAP (for example business logic classes with ABAP Unit tests) are executed on the SAP BTP ABAP environment. Parts that depend on S/4HANA application objects are marked as designed, not executed.

## Naming conventions

All custom objects use the prefix `ZMG` (Meltemi Grid).

| Object | Convention | Example |
|--------|------------|---------|
| Package | `ZMG_<area>` | `ZMG_AWM` |
| Class / interface | `ZCL_MG_<area>_...` / `ZIF_MG_<area>_...` | `ZCL_MG_AWM_TASK_SEQUENCER` |
| Database table | `ZMG_<area>_...` | `ZMG_AWM_STEP` |
| CDS view entity | `ZR_MG_...`, `ZI_MG_...`, `ZC_MG_...` | `ZI_MG_NotifTaskStep` |
| Local test class | `LTCL_...` | `LTCL_SEQUENCER` |

Commit messages follow `type(area): summary`, for example `docs(awm): add lesson 1.1 notes`.

## Disclaimer

- Meltemi Grid S.A. is fictional. All master data, names, addresses and numbers are invented.
- Nothing in this repository comes from an employer or a customer: no code, object names, specifications, screenshots or data.
- All code is written from scratch for this portfolio. SAP standard code and SAP Note texts are referenced by name or number only, never copied.
- This repository is a personal project and is not affiliated with or endorsed by SAP SE. SAP and other SAP product names are trademarks of SAP SE.

## License

[MIT](LICENSE)
