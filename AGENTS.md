# Repository Context

This repository is a documentation-only workspace for the FS-AI ADS-DV project. It currently contains user guidance, safety and transport procedures, inspection material, scrutineering process notes, dimensions/specification data, and the CAN/software interface documentation for the vehicle.

## Current Inventory

- There is no application code, build system, or test suite in this repository.
- `README.md` currently contains a migration notice and a documentation index for the Markdown set.
- `FS-AI ADS-DV User Manual.md` is the main draft user-facing operating document and has received the most active Markdown clean-up in this editing pass.
- `FS-AI ADS-DV Software Interface Specification.md` is the main technical interface document.
- `FS-AI ADS-DV Operational Safety.md` is a substantial draft safety document covering storage/access, handling/lifting, static operation, dynamic operating area requirements, and dynamic operating controls.
- `FS-AI ADS-DV Specifications & Dimensions.md` is a draft hardware summary document.
- `FS-AI ADS-DV Inspection Schedule.md` is an early draft inspection/checks document with Document Control front matter and migrated storage/maintenance content.
- `FS-AI ADS-DV Transportation Procedures.md` is a populated transport draft covering inventory, preparation for movement, movement procedure, and transport protection/securing.
- `FS-AI ADS-DV Risk Assessment & Method Statement.md` currently contains Document Control front matter and an explicit placeholder note, but no substantive risk/method content yet.
- `FS-AI ADS-DV Operations Logging and Record Keeping Protocol.md` currently contains Document Control front matter and an explicit placeholder note, but no substantive protocol content yet.
- `FS-AI DDT Scrutineering Process.md` contains Document Control front matter and an early outline/checklist.
- `FS-AI APC Scrutineering Process.md` currently contains Document Control front matter and an explicit placeholder note, but no substantive APC process content yet.
- `images/FS-AI_ADS-DV_Handshake.png` and `images/FS-AI_ADS-DV_State_Machine.png` are interface/state documentation assets.
- `images/FS-AI_ADS-DV_Key_Switches.png`, `images/FS-AI_ADS-DV_Side_Switches.png`, `images/FS-AI_ADS-DV_RES.png`, `images/FS-AI_ADS-DV_RES_Battery_Charger.png`, `images/FS-AI_ADS-DV_RES_Closeup.jpg`, and `images/FS-AI_ADS-DV_Ramps.jpg` are hardware and procedure reference assets.

## Document Status

- `FS-AI ADS-DV Software Interface Specification.md` remains one of the most developed files. It covers CAN_B messages, handshake/comms-loss behaviour, autonomous state transitions, and fault conditions, but still references an external `.dbc` file.
- `FS-AI ADS-DV User Manual.md` is a populated draft with Document Control front matter and reformatted Markdown structure. It now distinguishes between the traction battery threshold for operation (`47.5V`) and the higher threshold used when preparing for storage (`50.0V`), and it treats the RES battery as part of the RES except where battery charging is described explicitly. It still contains publication placeholders, image placeholders, and incomplete procedural detail in some sections.
- `FS-AI ADS-DV Operational Safety.md` is materially populated, with numbered top-level sections for Static Operation and Dynamic Operation. It now includes Dynamic Operating Area controls, Safe Run Off Zone terminology, and welfare/emergency-planning guidance, but it still includes placeholder publication metadata and should be kept aligned with Transportation Procedures where transport-related handling rules overlap.
- `FS-AI ADS-DV Specifications & Dimensions.md` contains starter technical content and Document Control front matter, but still includes unresolved placeholders such as `2026-03-XX` and `XXX Lead Acid`.
- `FS-AI ADS-DV Inspection Schedule.md` is still an early draft, but it now includes Document Control front matter plus migrated storage, 12V battery, and mechanical-check guidance; its structure and at least one internal cross-reference should be reviewed before release.
- `FS-AI ADS-DV Transportation Procedures.md` is now a substantially rewritten numbered draft aligned to the current user manual. It requires completion of User Manual Section 7 before transport movement, uses trolley movement as the default handling method, allows on-wheel movement only where necessary, requires Brake Discharge before powered-down handling on the ADS-DV's own wheels, and states that the ADS-DV is transported on its own wheels rather than on the trolleys. It still contains photo placeholders and publication metadata placeholders.
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
- Where a document includes a `## Document Control` section, keep the title, aligned table formatting, and master-copy note consistent. Format the `Changes` column to 60 characters wide.
- Maintain consistency in terminology across documents, especially for subsystem names, safety states, operational steps, inspection names, and scrutineering terminology.
- Where a term is being used as a defined area, zone, role, or supplied equipment item, prefer capitalisation rather than quotation marks. Examples include `Safe Run Off Zone`, `Safe Area`, `Skateboard Trolleys`, and `Quick Lift Jack`.
- In operator-facing procedure text, use double quotation marks for literal states, indicator colours, displayed status labels, switch positions, control values, and other UI labels shown to the user. Examples include `"On"`, `"Off"`, `"Green"`, `"AS Ready"`, `"Service"`, `"Set"`, `"Go"`, `"0"`, and `"1"`.
- Do not use single quotation marks for names, states, or UI values. Reserve them only for limited emphasis or literal sounds such as `'click'` where needed.
- In operator-facing text, treat the RES battery as part of the RES unless the battery itself is being charged or otherwise handled explicitly.
- In transport text, trolley movement is the default handling method; on-wheel movement is only for necessary manoeuvres such as plastic ramps or positioning inside the transport vehicle/trailer, and the ADS-DV is transported on its own wheels rather than on the trolleys.
- Do not separate units from numbers with a space; use forms such as `75kg`, not `75 kg`.
- For consistency, note callouts should use a Markdown blockquote and begin with `**Note:**`.
- Exception: the Safe Run Off Zone instruction requiring immediate RES activation may use stronger formatting than a standard note callout, because it is a primary dynamic-operation risk mitigation and needs additional emphasis.
- Tables of contents should refer only to top-level sections, not sub-sections.
- Avoid inventing technical values, procedures, or safety requirements; leave gaps explicit until they are confirmed.
- Replace placeholder dates, URLs, TODO markers, and migration notes before treating a document as publishable.
- When editing an existing document, follow its current style unless there is an intentional clean-up pass. Some files use plain-text titles and section lists rather than strict Markdown headings.
- For readability in plain-text editors, use double line spacing between top-level section headings and the preceding section content.
- If a file is intentionally still a stub or blank placeholder, keep that status explicit rather than implying completion.

## Editing Session Notes

- Check that the `README.md` documentation index stays aligned with the actual repository file set.
- Normalise repeated publication boilerplate across the Markdown documents where appropriate.
- Resolve or clearly retain placeholders such as `2026-03-XX`, `TBD`, `XXX Lead Acid`, image placeholders, and references to external legacy PDFs.
- After section renumbering or restructuring, re-check the table of contents and heading links so they still match the body structure.
- Where procedures are repeated across sections, compare them explicitly for drift before committing changes.
- Review migrated text for stale year references, copied-source notes, and formatting/encoding artefacts before reusing it elsewhere.
- Keep Transportation Procedures and Operational Safety aligned where both mention trolley use, ramps, or transport handling exceptions.
- Confirm whether placeholder-only files should be expanded in the session or remain explicitly incomplete.
- Before committing documentation changes, check for stale cross-references, missing assets, and unresolved placeholders.

## Maintenance Notes

- Update this file whenever documents are added, removed, renamed, or materially change in scope.
- If a working copy or duplicate draft is created temporarily during editing, either remove it before commit or document its purpose here if it is meant to remain in the repository.
