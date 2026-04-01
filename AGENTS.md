# Repository Context

This repository is a documentation-only workspace for the FS-AI ADS-DV project. It currently contains user guidance, safety and transport procedures, inspection material, scrutineering process notes, dimensions/specification data, and the CAN/software interface documentation for the vehicle.

## Current Inventory

- There is no application code, build system, or test suite in this repository.
- `README.md` currently contains a migration notice and a documentation index for the Markdown set.
- `FS-AI ADS-DV User Manual.md` is the main draft user-facing operating document and has received the most active Markdown clean-up in this editing pass.
- `FS-AI ADS-DV Software Interface Specification.md` is the main technical interface document.
- `FS-AI ADS-DV Operational Safety.md` is a substantial draft safety document with a mix of new front matter and older migrated loan/safety content.
- `FS-AI ADS-DV Specifications & Dimensions.md` is a draft hardware summary document.
- `FS-AI ADS-DV Inspection Schedule.md` is an early draft inspection/checks document with Document Control front matter and migrated storage/maintenance content.
- `FS-AI ADS-DV Transportation Procedures.md` contains Document Control front matter, a placeholder note, and a short migrated transportation/handling draft.
- `FS-AI ADS-DV Risk Assessment & Method Statement.md` currently contains Document Control front matter and an explicit placeholder note, but no substantive risk/method content yet.
- `FS-AI ADS-DV Operations Logging and Record Keeping Protocol.md` currently contains Document Control front matter and an explicit placeholder note, but no substantive protocol content yet.
- `FS-AI DDT Scrutineering Process.md` contains Document Control front matter and an early outline/checklist.
- `FS-AI APC Scrutineering Process.md` currently contains Document Control front matter and an explicit placeholder note, but no substantive APC process content yet.
- `images/FS-AI_ADS-DV_Handshake.png` and `images/FS-AI_ADS-DV_State_Machine.png` are interface/state documentation assets.
- `images/FS-AI_ADS-DV_Key_Switches.png`, `images/FS-AI_ADS-DV_Side_Switches.png`, `images/FS-AI_ADS-DV_RES.png`, `images/FS-AI_ADS-DV_RES_Battery_Charger.png`, `images/FS-AI_ADS-DV_RES_Closeup.jpg`, and `images/FS-AI_ADS-DV_Ramps.jpg` are hardware and procedure reference assets.

## Document Status

- `FS-AI ADS-DV Software Interface Specification.md` remains one of the most developed files. It covers CAN_B messages, handshake/comms-loss behaviour, autonomous state transitions, and fault conditions, but still references an external `.dbc` file.
- `FS-AI ADS-DV User Manual.md` is a populated draft with Document Control front matter and reformatted Markdown structure. It now distinguishes between the traction battery threshold for operation (`47.5V`) and the higher threshold used when preparing for storage (`50.0V`), and it treats the RES battery as part of the RES except where battery charging is described explicitly. It still contains publication placeholders, image placeholders, and incomplete procedural detail in some sections.
- `FS-AI ADS-DV Operational Safety.md` is materially populated, but it includes placeholder publication metadata, migration notes, and legacy copied text that should be normalised during editing.
- `FS-AI ADS-DV Specifications & Dimensions.md` contains starter technical content and Document Control front matter, but still includes unresolved placeholders such as `2026-03-XX` and `XXX Lead Acid`.
- `FS-AI ADS-DV Inspection Schedule.md` is still an early draft, but it now includes Document Control front matter plus migrated storage, 12V battery, and mechanical-check guidance; its structure and at least one internal cross-reference should be reviewed before release.
- `FS-AI ADS-DV Transportation Procedures.md` is no longer blank; it contains a short migrated transportation/handling draft, but still reads as incomplete and references an external PDF for full detail.
- `FS-AI ADS-DV Risk Assessment & Method Statement.md`, `FS-AI ADS-DV Operations Logging and Record Keeping Protocol.md`, and `FS-AI APC Scrutineering Process.md` currently remain placeholder drafts with Document Control scaffolds and minimal body content.
- `FS-AI DDT Scrutineering Process.md` now contains Document Control front matter and a short outline rather than a finished procedure document.
- `README.md` remains a repository landing page rather than a fully standardized controlled document and should be treated accordingly.
- Several documents still contain placeholders such as `2026-03-XX`, `TBD`, `XXX Lead Acid`, image placeholders, and references to external legacy PDFs; these should be treated as incomplete, not release-ready values.
- Some files contain encoding artefacts from prior migration or copy/paste operations; preserve meaning, but clean these up deliberately when editing.

## External References

- `FS-AI ADS-DV Software Interface Specification.md` references `ADSDV_2021_VCU_AI_interface_v2.dbc`.
- That `.dbc` file is not currently present in this repository, so any CAN-level review should treat it as an external dependency.

## Working Conventions

- Preserve the current file names and top-level layout unless there is a clear reason to change them.
- Keep documentation in Markdown.
- Where a document includes a `## Document Control` section, keep the title, aligned table formatting, and master-copy note consistent.
- Maintain consistency in terminology across documents, especially for subsystem names, safety states, operational steps, inspection names, and scrutineering terminology.
- In operator-facing text, treat the RES battery as part of the RES unless the battery itself is being charged or otherwise handled explicitly.
- Avoid inventing technical values, procedures, or safety requirements; leave gaps explicit until they are confirmed.
- Replace placeholder dates, URLs, TODO markers, and migration notes before treating a document as publishable.
- When editing an existing document, follow its current style unless there is an intentional clean-up pass. Some files use plain-text titles and section lists rather than strict Markdown headings.
- For readability in plain-text editors, use double line spacing between top-level section headings and the preceding section content.
- If a file is intentionally still a stub or blank placeholder, keep that status explicit rather than implying completion.

## Editing Session Notes

- Check that the `README.md` documentation index stays aligned with the actual repository file set.
- Normalise repeated publication boilerplate across the Markdown documents where appropriate.
- Resolve or clearly retain placeholders such as `2026-03-XX`, `TBD`, `XXX Lead Acid`, image placeholders, and references to external legacy PDFs.
- Where procedures are repeated across sections, compare them explicitly for drift before committing changes.
- Review migrated text for stale year references, copied-source notes, and formatting/encoding artefacts before reusing it elsewhere.
- Confirm whether placeholder-only files should be expanded in the session or remain explicitly incomplete.
- Before committing documentation changes, check for stale cross-references, missing assets, and unresolved placeholders.

## Maintenance Notes

- Update this file whenever documents are added, removed, renamed, or materially change in scope.
- If a working copy or duplicate draft is created temporarily during editing, either remove it before commit or document its purpose here if it is meant to remain in the repository.
