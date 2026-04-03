# FS-AI ADS-DV Glossary


## Document Control

| Version | Date       | Changes                                                      |
| ------- | ---------- | ------------------------------------------------------------ |
| 1.0     | 2026-04-03 | Added canonical GEMS DA3 Datalogger terminology.             |

> The master copy of this document is stored at [FS-AI/FS-AI_ADS-DV_Documentation](https://github.com/FS-AI/FS-AI_ADS-DV_Documentation).<br>
> Always check you have the latest version, as printed copies, PDFs, downloads, or repository clones may be out of date.


## Table of Contents

1. [Introduction](#1-introduction)
2. [Scope and Use](#2-scope-and-use)
3. [Glossary](#3-glossary)


## 1. Introduction

This document defines common terms and abbreviations used across the FS-AI ADS-DV documentation set.

It is intended to be used alongside the current User Manual, Operational Safety, Transportation Procedures, Inspection Schedule, RAMS, and other related ADS-DV documents.


## 2. Scope and Use

This glossary provides the preferred definitions and terminology for shared operational, safety, transport, and project terms.

Where a document contains interface-specific, competition-specific, or software-specific terminology, that document may still define additional local terms. In particular, the [FS-AI ADS-DV Software Interface Specification](./FS-AI%20ADS-DV%20Software%20Interface%20Specification.md) remains the authoritative source for fixed CAN identifiers, message names, and interface-specific abbreviations.


## 3. Glossary

| Term | Definition / Use in Current Docs | Notes |
| ---- | -------------------------------- | ----- |
| ADS-DV | Autonomous Driving System - Dedicated Vehicle. | Core project term used across the document set. |
| ADS-DV Operator | The responsible person or organisation using the ADS-DV and accountable for planning, documentation, preparation, and overall control outside specific delegated roles. | Use this as the generic responsibility term. Use narrower role names where a more specific duty is intended. |
| ASR | Autonomous Systems Responsible person. The responsible operator who supervises the ADS-DV and operates the RES. | Operational role defined in the User Manual and Operational Safety. |
| RES | Remote Emergency Stop. The hand-carried emergency stop device operated by the ASR. | While the ADS-DV is active, the RES must be strapped around the ASR's waist and kept on their person. |
| EBS | Emergency Braking System. | Used in the User Manual, RAMS, and Software Interface Specification. |
| E-Stop Loop | The condition in which the emergency stop chain is complete and the Touch Screen indicator shows "Green". | Completed through the correct state of the RES, Side Emergency Stop Switches, MPP Dongle, and Inertia Switch. |
| MPP | Multi-Purpose Port. | Shared interface and operational term. |
| MPP Dongle | The dongle fitted to the MPP as part of the required operating, charging, and storage state. | Required for operation and Brake Discharge. |
| GEMS DA3 Datalogger | The GEMS DA3 data-logging unit used to record ADS-DV run data. | Use this as the full term for the datalogger across the operational document set. |
| GEMS DA3 Datalogger Memory Card | The removable memory card used by the GEMS DA3 Datalogger. | Preferred term where insertion, removal, storage, or download of the card is being described. |
| Compute Platform | Generic term for any hardware used to send CAN signals to the ADS-DV. | Preferred generic term across the operational document set. |
| InCarPC | A specific type of Compute Platform provided with some ADS-DV configurations. | A defined subtype of Compute Platform, not a replacement for the generic term. |
| AI Power Switch | The switch used to supply power to the Compute Platform. | Operational term from the User Manual. |
| Autonomous System Master Switch (ASMS) | The switch controlling the Autonomous System. | Preferred term across the operational document set. |
| Tractive System Master Switch (TSMS) | The switch controlling the tractive system. | Preferred term across the operational document set. |
| TSAL | Tractive System Active Light. The indicator LEDs used to show tractive-system and autonomous-state conditions. | Expanded here for cross-document use. |
| LV Battery | Low Voltage Battery. The low-voltage battery supporting the ADS-DV auxiliary electrical systems. | Used in the User Manual and Inspection Schedule. |
| DC/DC Converter | Direct Current / Direct Current converter used to recharge the LV Battery from the Traction Battery. | The User Manual also refers to this as the `DCDC converter`; `DC/DC Converter` is the expanded form. |
| Mission | The selected autonomous run or task chosen through the Touch Screen interface before activating the RES "Go" signal. | The Software Interface Specification also defines mission-related signals via `AMI`. |
| RAMS | Risk Assessment & Method Statement. | Used for the controlled safety document covering method, hazards, and controls. |
| IMechE | Institution of Mechanical Engineers. | Used in references to Formula Student and technical support. |
| CAN | Controller Area Network. | Shared term used for the ADS-DV interface and communications references. |
| VCU | Vehicle Control Unit. | Interface term used in the Software Interface Specification. |
| Dynamic Operating Area | The designated area, pre-approved by the IMechE, within which Dynamic Operation is permitted. | Defined operationally in Operational Safety. |
| Safe Area | The area for general personnel during Dynamic Operation, separated from the Dynamic Operating Area by a structural barrier. | Defined in Operational Safety. |
| Run Off Zone | The defined 10m boundary around the internal operating area of the Dynamic Operating Area. | Entry into this zone requires immediate RES activation by the ASR. |
| Static Operation | Use of the ADS-DV in a workshop, enclosed space, or non-approved dynamic venue with the wheels raised off the ground. | Defined in Operational Safety and referenced by the User Manual. |
| Dynamic Operation | Use of the ADS-DV within an approved Dynamic Operating Area under the defined ASR and area-control rules. | Defined in Operational Safety and referenced by the User Manual. |
| Skateboard Trolleys | The supplied wheeled supports used to carry or support the ADS-DV. | Used as suitable stands for Static Operation on firm, level ground and as the default movement method outside specific exceptions. |
| Quick Lift Jack | The approved jack used to lift the ADS-DV on the underside of the chassis. | Preferred capitalisation across the operational document set. |
