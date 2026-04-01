# Repository Context

This repository is a documentation-only workspace for the FS-AI ADS-DV project. It currently contains user guidance, safety and transport procedures, inspection material, scrutineering process notes, dimensions/specification data, and the CAN/software interface documentation for the vehicle.

## Current Inventory

- There is no application code, build system, or test suite in this repository.
- `README.md` is no longer title-only; it now contains a migration notice and a documentation index for the Markdown set.
- `FS-AI ADS-DV User Manual.md` is a draft user-facing operating document.
- `FS-AI ADS-DV Software Interface Specification.md` is the main technical interface document.
- `FS-AI ADS-DV Operational Safety.md` is a substantial draft safety document with a mix of new front matter and older migrated loan/safety content.
- `FS-AI ADS-DV Specifications & Dimensions.md` is a draft hardware summary document.
- `FS-AI ADS-DV Inspection Schedule.md` is a very early draft inspection/checks document.
- `FS-AI ADS-DV Transportation Procedures.md` exists but is currently empty.
- `FS-AI ADS-DV Risk Assessment & Method Statement.md` exists but is currently empty.
- `FS-AI ADS-DV Operations Logging and Record Keeping Protocol.md` exists but is currently empty.
- `FS-AI DDT Scrutineering Process.md` contains an early outline/checklist.
- `FS-AI APC Scrutineering Process.md` exists but is currently empty.
- `images/FS-AI_ADS-DV_Handshake.png` and `images/FS-AI_ADS-DV_State_Machine.png` are interface/state documentation assets.
- `images/FS-AI_ADS-DV_Key_Switches.png`, `images/FS-AI_ADS-DV_Side_Switches.png`, `images/FS-AI_ADS-DV_RES.png`, `images/FS-AI_ADS-DV_RES_Battery_Charger.png`, `images/FS-AI_ADS-DV_RES_Closeup.jpg`, and `images/FS-AI_ADS-DV_Ramps.jpg` are hardware and procedure reference assets.

## Document Status

- `FS-AI ADS-DV Software Interface Specification.md` remains one of the most developed files. It covers CAN_B messages, handshake/comms-loss behaviour, autonomous state transitions, and fault conditions, but still references an external `.dbc` file.
- `FS-AI ADS-DV User Manual.md` is a populated draft and still contains explicit placeholders such as `ToDo: Inertia Switch`, `[URL]`, and `2026-03-XX`.
- `FS-AI ADS-DV Operational Safety.md` is materially populated, but it includes placeholder publication metadata, migration notes, and legacy copied text that should be normalised during editing.
- `FS-AI ADS-DV Specifications & Dimensions.md` contains starter technical content, but still includes unresolved placeholders such as `[URL]`, `2026-03-XX`, and `XXX Lead Acid`.
- `FS-AI ADS-DV Inspection Schedule.md` is currently a stub with placeholder publication metadata and minimal content.
- `FS-AI ADS-DV Transportation Procedures.md`, `FS-AI ADS-DV Risk Assessment & Method Statement.md`, `FS-AI ADS-DV Operations Logging and Record Keeping Protocol.md`, and `FS-AI APC Scrutineering Process.md` are currently blank files and should be treated as placeholders rather than completed drafts.
- `FS-AI DDT Scrutineering Process.md` is currently a short checklist outline rather than a finished procedure document.
- Several documents still contain placeholders such as `[URL]`, `2026-03-XX`, `ToDo`, and draft notes; these should be treated as incomplete, not release-ready values.
- Some files contain encoding artefacts from prior migration or copy/paste operations; preserve meaning, but clean these up deliberately when editing.

## External References

- `FS-AI ADS-DV Software Interface Specification.md` references `ADSDV_2021_VCU_AI_interface_v2.dbc`.
- That `.dbc` file is not currently present in this repository, so any CAN-level review should treat it as an external dependency.

## Working Conventions

- Preserve the current file names and top-level layout unless there is a clear reason to change them.
- Keep documentation in Markdown.
- Maintain consistency in terminology across documents, especially for subsystem names, safety states, operational steps, inspection names, and scrutineering terminology.
- Avoid inventing technical values, procedures, or safety requirements; leave gaps explicit until they are confirmed.
- Replace placeholder dates, URLs, TODO markers, and migration notes before treating a document as publishable.
- When editing an existing document, follow its current style unless there is an intentional clean-up pass. Some files use plain-text titles and section lists rather than strict Markdown headings.
- If a file is intentionally still a stub or blank placeholder, keep that status explicit rather than implying completion.

## Editing Session Notes

- Check that the `README.md` documentation index stays aligned with the actual repository file set.
- Normalise repeated publication boilerplate across the Markdown documents where appropriate.
- Resolve or clearly retain placeholders such as `[URL]`, `2026-03-XX`, `ToDo: Inertia Switch`, and `XXX Lead Acid`.
- Review migrated text for stale year references, copied-source notes, and formatting/encoding artefacts before reusing it elsewhere.
- Confirm whether blank files should be populated in this session or remain as declared placeholders.
- Before committing documentation changes, check for stale cross-references, missing assets, and unresolved placeholders.

## Maintenance Notes

- Update this file whenever documents are added, removed, renamed, or materially change in scope.
- If a working copy or duplicate draft is created temporarily during editing, either remove it before commit or document its purpose here if it is meant to remain in the repository.
