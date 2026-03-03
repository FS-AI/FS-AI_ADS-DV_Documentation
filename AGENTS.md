# Repository Context

This repository is a documentation-only workspace for the FS-AI ADS-DV project. It currently focuses on operator guidance, safety, inspection, dimensions, and the CAN/software interface for the vehicle.

## Current Inventory

- There is no application code, build system, or test suite in this repository.
- `README.md` exists and currently contains only the repository title.
- `FS-AI ADS-DV User Manual.md` is a draft user-facing operating document.
- `FS-AI ADS-DV Software Interface Specification.md` is the main technical interface document.
- `FS-AI ADS-DV Specifications & Dimensions.md` is a draft hardware summary document.
- `FS-AI ADS-DV Operational Safety.md` is a draft safety and handling document.
- `FS-AI ADS-DV Inspection Schedule.md` is a draft inspection and checks document.
- `images/FS-AI_ADS-DV_Handshake.png` and `images/FS-AI_ADS-DV_State_Machine.png` are repository image assets for interface/state documentation.

## Document Status

- `FS-AI ADS-DV Software Interface Specification.md` is the most developed file. It covers CAN_B messages, handshake/comms-loss behavior, autonomous state transitions, and fault conditions.
- `FS-AI ADS-DV User Manual.md` has a populated outline and draft content, with at least one explicit placeholder (`ToDo: Inertia Switch`).
- `FS-AI ADS-DV Specifications & Dimensions.md`, `FS-AI ADS-DV Operational Safety.md`, and `FS-AI ADS-DV Inspection Schedule.md` are early-stage drafts with starter content and placeholder publication metadata.
- Several documents still contain placeholders such as `[URL]` and `2026-03-XX`; these should be treated as incomplete, not release-ready values.

## External References

- `FS-AI ADS-DV Software Interface Specification.md` references `ADSDV_2021_VCU_AI_interface_v2.dbc`.
- That `.dbc` file is not currently present in this repository, so any CAN-level review should treat it as an external dependency.

## Working Conventions

- Preserve the current file names and top-level layout unless there is a clear reason to change them.
- Keep documentation in Markdown.
- Maintain consistency in terminology across documents, especially for subsystem names, safety states, and operational steps.
- Avoid inventing technical values, procedures, or safety requirements; leave gaps explicit until they are confirmed.
- Replace placeholder dates, URLs, and TODO markers before treating a document as publishable.
- When editing an existing document, follow its current style unless there is an intentional clean-up pass. Some files use plain-text titles and section lists rather than strict Markdown headings.

## Maintenance Notes

- Update this file whenever documents are added, removed, renamed, or materially change in scope.
- Before committing documentation changes, check for stale cross-references, missing assets, and unresolved placeholders.
