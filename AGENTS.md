# Repository Context

This repository is a documentation-only workspace for the FS-AI ADS-DV project. It currently contains user guidance, safety and transport procedures, inspection material, scrutineering process notes, dimensions/specification data, and the CAN/software interface documentation for the vehicle.

## Current Inventory

- There is no application code, build system, or test suite in this repository.
- `README.md` currently contains a migration notice and a documentation index for the Markdown set.
- `FS-AI ADS-DV User Manual.md` is the main draft user-facing operating document and has received the most active Markdown clean-up in this editing pass.
- `FS-AI ADS-DV Software Interface Specification.md` is the main technical interface document and currently retains the original interface terminology used in the CAN specification.
- `FS-AI ADS-DV Operational Safety.md` is a substantial draft safety document covering storage/access, handling/lifting, static operation, dynamic operating area requirements, and dynamic operating controls.
- `FS-AI ADS-DV Glossary.md` is the central glossary document for shared terms and abbreviations used across the operational document set.
- `FS-AI ADS-DV Specifications & Dimensions.md` is a structured draft hardware summary document with Document Control front matter, references, and numbered specification sections.
- `FS-AI ADS-DV Inspection Schedule.md` is an early draft inspection/checks document with Document Control front matter, a reduced scope focused on recurring inspection and mechanical checks, and a short preventative-maintenance section.
- `FS-AI ADS-DV Transportation Procedures.md` is a populated transport draft covering inventory, preparation for movement, movement procedure, and transport protection/securing.
- `FS-AI ADS-DV Risk Assessment & Method Statement.md` now contains a developed RAMS draft with a top-level TOC, related documents, a populated method statement, a risk scoring method, and populated general, static, dynamic, and transport risk assessment entries.
- `FS-AI ADS-DV Operations Logging and Record Keeping Protocol.md` is now a structured draft covering run logging, run logging record sheets, and GEMS datalogger data management.
- `FS-AI DDT Scrutineering Process.md` is now a structured stub with Document Control front matter, a TOC, references, a `coming soon` status note, and a retained planned-content outline.
- `FS-AI APC Scrutineering Process.md` is now a structured stub with Document Control front matter, a TOC, references, and a `coming soon` status note.
- `images/FS-AI_ADS-DV_Handshake.png` and `images/FS-AI_ADS-DV_State_Machine.png` are interface/state documentation assets.
- `images/FS-AI_ADS-DV_Key_Switches.png`, `images/FS-AI_ADS-DV_Side_Switches.png`, `images/FS-AI_ADS-DV_RES.png`, `images/FS-AI_ADS-DV_RES_Battery_Charger.png`, `images/FS-AI_ADS-DV_RES_Closeup.jpg`, and `images/FS-AI_ADS-DV_Ramps.jpg` are hardware and procedure reference assets.

## Document Status

- `FS-AI ADS-DV Software Interface Specification.md` remains one of the most developed files. It covers CAN_B messages, handshake/comms-loss behaviour, autonomous state transitions, and fault conditions, but still references an external `.dbc` file. It also intentionally retains established interface terminology such as `AI Computer`, which should not be normalised casually when editing other documents.
- `FS-AI ADS-DV User Manual.md` is a populated draft with Document Control front matter and reformatted Markdown structure. It now distinguishes between the traction battery threshold for operation (`47.5V`) and the higher threshold used when preparing for storage (`50.0V`), treats the RES battery as part of the RES except where battery charging is described explicitly, states that the ASR must keep the RES strapped around their waist and on their person while the ADS-DV is active, and now uses `Autonomous System Master Switch (ASMS)`, `Tractive System Master Switch (TSMS)`, and `Tractive System Active Light (TSAL)` terminology consistently. It still contains publication placeholders, image placeholders, and incomplete procedural detail in some sections.
- `FS-AI ADS-DV Operational Safety.md` is materially populated, with numbered top-level sections for Static Operation and Dynamic Operation. It now includes Dynamic Operating Area controls, Run Off Zone terminology, welfare/emergency-planning guidance, and the rule that the ASR must keep the RES strapped around their waist and on their person while the ADS-DV is active. It still includes placeholder publication metadata and should be kept aligned with Transportation Procedures where transport-related handling rules overlap.
- `FS-AI ADS-DV Glossary.md` now centralises shared terms and abbreviations used across the operational documents. It is the preferred source for cross-document terminology such as `ADS-DV Operator`, `ASR`, `RES`, `MPP`, `TSAL`, `ASMS`, and `TSMS`, while interface-specific definitions remain local to the Software Interface Specification where required.
- `FS-AI ADS-DV Specifications & Dimensions.md` is now a structured dimensions/specification draft with a top-level TOC, references, grouped drive/steering/battery/dimensions sections, confirmed `Lead Acid` battery chemistry, and a live CAD repository reference. It still remains a summary document rather than a full detailed design specification.
- `FS-AI ADS-DV Inspection Schedule.md` is still an early draft, but it now focuses on recurring inspection and mechanical-check guidance plus basic preventative-maintenance advice rather than repeating storage, transport, or operating procedures. It still needs further development before release.
- `FS-AI ADS-DV Transportation Procedures.md` is now a substantially rewritten numbered draft aligned to the current user manual. It requires completion of User Manual Section 7 before transport movement, uses trolley movement as the default handling method, allows on-wheel movement only where necessary, requires Brake Discharge before powered-down handling on the ADS-DV's own wheels, states that the ADS-DV is transported on its own wheels rather than on the trolleys, and now uses `Quick Lift Jack` casing consistently. It still contains photo placeholders and publication metadata placeholders.
- `FS-AI ADS-DV Risk Assessment & Method Statement.md` now has substantive RAMS content, including a populated method statement, risk scoring, populated general, static, dynamic, and transport assessment tables, document-linked controls, consolidated activity labels, and a closing residual-risk summary. It now references the standalone glossary document for shared terminology, reflects the consolidated `ASMS`, `TSMS`, `TSAL`, and `Compute Platform` terminology used in the operational documents, and the RES-interference dynamic-operation entry has been rescored to reflect fail-safe behaviour. It still needs technical review, scoring review, and formal approval before it can be treated as final.
- `FS-AI ADS-DV Operations Logging and Record Keeping Protocol.md` is now a structured logging draft aligned to the operational documents. It includes references, a run logging record-sheet requirement, and GEMS datalogger download guidance using a Windows PC and GEMS GDA software. It may still need further detail before release.
- `FS-AI APC Scrutineering Process.md` now has the same structured front section style as the other controlled documents, but remains an explicit stub pending APC-specific scrutineering content.
- `FS-AI DDT Scrutineering Process.md` now has the same structured front section style as the other controlled documents, but remains an explicit stub pending full DDT scrutineering content.
- `README.md` remains a repository landing page rather than a fully standardized controlled document and should be treated accordingly.
- Several documents still contain placeholders such as `2026-03-XX`, `TBD`, image placeholders, and references to external legacy PDFs; these should be treated as incomplete, not release-ready values.
- Some files contain encoding artefacts from prior migration or copy/paste operations; preserve meaning, but clean these up deliberately when editing.

## External References

- `FS-AI ADS-DV Software Interface Specification.md` references `ADSDV_2021_VCU_AI_interface_v2.dbc`.
- That `.dbc` file is not currently present in this repository, so any CAN-level review should treat it as an external dependency.

## Working Conventions

- Preserve the current file names and top-level layout unless there is a clear reason to change them.
- Keep documentation in Markdown.
- Where a document includes a `## Document Control` section, keep the title, aligned table formatting, and master-copy note consistent. Format the `Changes` column to 60 characters wide.
- Always check `Document Control` tables in plain text after editing to ensure the spacing and alignment read cleanly, not just in rendered Markdown.
- Exception: for the RAMS, the `## Document Control` table should also include `Proposed By`, `Approved By`, and `Approved Date` columns. The `Proposed By` and `Approved By` cells should allow both a name and a role in a readable plain-text format, for example `Name / Role`.
- Maintain consistency in terminology across documents, especially for subsystem names, safety states, operational steps, inspection names, and scrutineering terminology.
- Use `Autonomous System Master Switch (ASMS)` / `Autonomous System Master Switch` rather than `AS Master Switch`.
- Use `Tractive System Master Switch (TSMS)` / `Tractive System Master Switch` rather than `TS Master Switch` or `Traction System Master Switch`.
- Use `Compute Platform` as the generic term for the autonomous driving computer. `InCarPC` is a specific type of Compute Platform. Avoid `AI Computer` except where it is part of a fixed interface identifier or required external terminology.
- Use `ADS-DV Operator` as the generic term for the responsible person or organisation using the ADS-DV. Use specific role names such as `ASR`, `Safety Supervisor`, or `Vehicle Handler` where those narrower responsibilities are intended.
- Use `GEMS DA3 Datalogger` as the full term for the datalogger, and `GEMS DA3 Datalogger Memory Card` where the removable card is being described.
- Use `FS-AI ADS-DV Glossary.md` as the central source for shared cross-document terms and abbreviations, and keep document introductions aligned with it where appropriate.
- Exception: in `FS-AI ADS-DV Software Interface Specification.md`, preserve the established interface terminology, including `AI Computer`, unless there is an explicit request for a dedicated terminology rewrite of that document. Never rename fixed interface identifiers such as `AI2VCU`.
- Where a term is being used as a defined area, zone, role, or supplied equipment item, prefer capitalisation rather than quotation marks. Examples include `Run Off Zone`, `Safe Area`, `Skateboard Trolleys`, and `Quick Lift Jack`.
- In operator-facing procedure text, use double quotation marks for literal states, indicator colours, displayed status labels, switch positions, control values, and other UI labels shown to the user. Examples include `"On"`, `"Off"`, `"Green"`, `"AS Ready"`, `"Service"`, `"Set"`, `"Go"`, `"0"`, and `"1"`.
- Do not use single quotation marks for names, states, or UI values. Reserve them only for limited emphasis or literal sounds such as `'click'` where needed.
- In operator-facing text, treat the RES battery as part of the RES unless the battery itself is being charged or otherwise handled explicitly.
- Where the ADS-DV is active under ASR supervision, describe the RES as strapped securely around the ASR's waist and kept on their person at all times. It is not to be held in one hand, put down, or moved out of immediate reach.
- In transport text, trolley movement is the default handling method; on-wheel movement is only for necessary manoeuvres such as plastic ramps or positioning inside the transport vehicle/trailer, and the ADS-DV is transported on its own wheels rather than on the trolleys.
- Do not separate units from numbers with a space; use forms such as `75kg`, not `75 kg`.
- For consistency, note callouts should use a Markdown blockquote and begin with `**Note:**`.
- Exception: the Run Off Zone instruction requiring immediate RES activation may use stronger formatting than a standard note callout, because it is a primary dynamic-operation risk mitigation and needs additional emphasis.
- Tables of contents should refer only to top-level sections, not sub-sections.
- Avoid inventing technical values, procedures, or safety requirements; leave gaps explicit until they are confirmed.
- Replace placeholder dates, URLs, TODO markers, and migration notes before treating a document as publishable.
- When editing an existing document, follow its current style unless there is an intentional clean-up pass. Some files use plain-text titles and section lists rather than strict Markdown headings.
- For readability in plain-text editors, use double line spacing between top-level section headings and the preceding section content.
- If a file is intentionally still a stub or blank placeholder, keep that status explicit rather than implying completion.

## Editing Session Notes

- Check that the `README.md` documentation index stays aligned with the actual repository file set.
- Normalise repeated publication boilerplate across the Markdown documents where appropriate.
- Resolve or clearly retain placeholders such as `2026-03-XX`, `TBD`, image placeholders, and references to external legacy PDFs.
- After section renumbering or restructuring, re-check the table of contents and heading links so they still match the body structure.
- Where procedures are repeated across sections, compare them explicitly for drift before committing changes.
- Review migrated text for stale year references, copied-source notes, and formatting/encoding artefacts before reusing it elsewhere.
- Keep Transportation Procedures and Operational Safety aligned where both mention trolley use, ramps, or transport handling exceptions.
- Keep the User Manual, Operational Safety, and RAMS aligned where they describe ASR duties and the on-person RES carrying requirement.
- Keep the standalone glossary aligned with the User Manual, Operational Safety, Transportation Procedures, Inspection Schedule, and RAMS whenever shared terminology changes.
- Keep operational-document terminology clean-up separate from the Software Interface Specification unless the session explicitly includes an interface-spec terminology pass.
- Confirm whether placeholder-only files should be expanded in the session or remain explicitly incomplete.
- Before committing documentation changes, check for stale cross-references, missing assets, and unresolved placeholders.

## Maintenance Notes

- Update this file whenever documents are added, removed, renamed, or materially change in scope.
- If a working copy or duplicate draft is created temporarily during editing, either remove it before commit or document its purpose here if it is meant to remain in the repository.
