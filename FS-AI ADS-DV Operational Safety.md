# FS-AI ADS-DV Operational Safety


## Document Control

| Version | Date       | Changes                                  |
| ------- | ---------- | ---------------------------------------- |
| 1.0     | 2026-03-XX | First issue of document.                 |

> The master copy of this document is stored at [FS-AI/FS-AI_ADS-DV_Documentation](https://github.com/FS-AI/FS-AI_ADS-DV_Documentation).<br>
> Always check you have the latest version, as printed copies, PDFs, downloads, or repository clones may be out of date.


## Table of Contents

1. [Introduction](#1-introduction)
2. [Scope and Current Limitations](#2-scope-and-current-limitations)
3. [Unattended Storage and Access](#3-unattended-storage-and-access)
4. [Handling and Lifting](#4-handling-and-lifting)
5. [ADS-DV Operations](#5-ads-dv-operations)
5.1. [Static Operation](#51-static-operation)
5.2. [Dynamic Operation](#52-dynamic-operation)
5.3. [Operational Limits](#53-operational-limits)
5.4. [Wet Weather Operation](#54-wet-weather-operation)
5.5. [Airports and RF Interference](#55-airports-and-rf-interference)
6. [Support Contacts](#6-support-contacts)


## 1. Introduction

This document provides operational safety guidance for handling, storing, and operating the FS-AI ADS-DV.


## 2. Scope and Current Limitations

This document does not duplicate the content of the [FS-AI ADS-DV User Manual](./FS-AI%20ADS-DV%20User%20Manual.md).

This document should be read and understood in conjunction with (Todo insert RAMS URL).

> Note: This document does not cover joystick operation, which is not yet supported by 2026 ADS-DVs.


## 3. Unattended Storage and Access

Access to the ADS-DV must be controlled to minimise risks to uninvolved or untrained people.

- The ADS-DV may only be accessed by authorised personnel who have been briefed on the ADS-DV and have read this document, the RAMS and the User Manual manual.
- The ADS-DV must be stored in a secure and locked area when unattended. CCTV is recommended.


## 4. Handling and Lifting

> Note: The ground clearance of the ADS-DV is low and plastic ramps have been provided to allow smooth transitions over steps, lips, kerbs, etc.

The ADS-DV must only be lifted using the Quick Lift jack on the underside of the chassis. The bodywork, including the nosecone, or the suspension, must not be used for lifting.

Except during an actual dynamic test run, the ADS-DV should be placed on and moved using the supplied "skateboard" trolleys. The Quick Lift jack is used only to lift the ADS-DV onto or off the trolleys.

**The ADS-DV weighs 300 kg, which means each wheel carries 75 kg. Thus, a single person at each wheel is insufficient to lift the ADS-DV safely and must not be attempted.**


## 5. ADS-DV Operations

To ensure safety during ADS-DV operations, the following rules must be followed.

### 5.1. Static Operation

When in a workshop, other enclosed space, or anywhere not specifically designated and approved as a Dynamic Operating Area, the ADS-DV may only be used in Static Operation mode.

Static Operations must be conducted as follows:

- There must be a clearly defined Hazardous Area extending at least 5m around the ADS-DV while it is active. General personnel must remain outside this area. Tensabarriers or similar portable barrier systems are recommended to mark out the boundary clearly.
- There must always be a qualified Autonomous Systems Responsible person (ASR) present to operate the ADS-DV with the Remote Emergency Stop (RES).
- The ADS-DV must be raised off the ground, with the wheels in the air, at all times. In practice, this means the ADS-DV should remain on suitable stands such as the supplied "skateboard" trolleys throughout Static Operation.
- The stands used must conform to the following requirements:
  - At least 90 mm clearance below the wheels.
  - At least 100 mm clearance to the front wheels when on full steering lock.
  - At least 800 mm x 400 mm spread of support under the chassis to avoid rocking or tipping.
  - The "skateboard" trolleys provided in the Inventory are considered suitable for Static Operation if used on a firm and level surface. Alternative stands (not provided) must be used if there is any risk of the "skateboard" trolleys rolling away.
- The ASR must only be responsible for mission selection and the RES. They must not perform any other duties while the ADS-DV is active.
- No person other than the ASR is allowed within the Hazardous Area while the ADS-DV is active. Test operations should be conducted remotely using a wired or wireless communications link to the ADS-DV.
- The ASR should not stand directly in front of or behind the ADS-DV.
- Any cables and wires must be kept clear of the rotating and/or steering wheels of the ADS-DV.

> Note: The Quick-Lift jack provided in the Inventory is not suitable for Static Operation and must only be used to lift the ADS-DV on and off the "skateboard" trolleys.
>
> Note: There is a risk of stones being flung off the tyres of the ADS-DV when performing a static test. It is recommended to clean off the tyres before a static test is conducted.

### 5.2. Dynamic Operation

Dynamic Operations of the ADS-DV are only permitted within a designated Dynamic Operating Area pre-approved by the IMechE.

> Note: Designated Dynamic Operating Areas require the marking out of a 10m "safe run off" area as a defined boundary. If the ADS-DV enters the "safe run off" area, the ASR **MUST** activate the RES **IMMEDIATELY**.

Dynamic Operations must be conducted according to the same safety principles as the Formula Student Dynamic Events:

- There must be a Safe Area for general personnel, separated from the Dynamic Operating Area by a structural barrier such as a tyre wall.
- There must always be an ASR present to operate the ADS-DV with the RES.
- Any work on the ADS-DV in the Safe Area must take place according to the same rules as the Static Operations listed above, with the wheels in the air at all times.
- Outside the actual dynamic test, the ADS-DV must remain on the supplied "skateboard" trolleys for handling and movement.
- The ADS-DV must enter and exit the designated Dynamic Operating Area on the supplied "skateboard" trolleys.
- The ADS-DV must only be lowered off the trolleys immediately before the actual dynamic test, and it must be returned to the trolleys immediately after the test.
- The ASR must only be responsible for mission selection and the RES. They must not perform any other duties while the ADS-DV is active.
- Only one other person in addition to the ASR is allowed "over the wall", i.e. outside the Safe Area, to assist with lifting the ADS-DV on or off the trolleys (using the Quick-Lift jack) immediately before or after the dynamic test.
- No tethered systems to the ADS-DV are allowed. Wireless connections only.
- Prior to selecting a Mission and activating the RES "Go" signal, the GEMS DA3 datalogger card must be inserted and confirmed to be logging, indicated by two "Green" lights. This will require downloading the data to a PC at regular intervals to ensure free storage space is always available.

> Note: A Dynamic Operations log must be filled in by the ASR. See [FS-AI ADS-DV Operations Logging and Record Keeping Protocol](./FS-AI%20ADS-DV%20Operations%20Logging%20and%20Record%20Keeping%20Protocol.md).

### 5.3. Operational Limits

If the designated dynamic area requires it, the IMechE will specify hard-coded Operational Limits to be placed on ADS-DV performance. For example, maximum speed, maximum torque (acceleration), or maximum steering angle for narrow areas.

> Note: If Operational Limits are required, the ASR will be responsible for loading and confirming these hard-coded limits are in effect.

### 5.4. Wet Weather Operation

The ADS-DV is not fully waterproof, especially the InCarPC. Therefore, operation in wet weather is only permissible according to the following conditions:

- No active rain must be falling.
- No standing water or puddles must be present.
- The ADS-DV must be dried down if it gets significantly wet, and WD40 applied by cloth to exposed metallic areas to prevent corrosion, except for the brake discs and brake pads.
- The InCarPC must be regularly inspected for water. If any water is present on or around the InCarPC, operation must be stopped until conditions dry out.

> Note: It is not permitted to operate the ADS-DV in ice or snow conditions.

### 5.5. Airports and RF Interference

The ADS-DV Remote Emergency Stop (RES) operates on a frequency range of 430 to 440 MHz. It has been observed previously that operation of the RES may be affected by RF systems present at airports.

If an airport is to be designated as a dynamic area, the airport should be informed that the RES radiates in this frequency band and must indicate approval.

If the ADS-DV fails to operate correctly near an airport, or spurious RES activation is observed when in the presence of RF systems, cease operations and inform IMechE Formula Student AI Technical Support.


## 6. Support Contacts

- IMechE Formula Student Office: [fs@imeche.org](mailto:fs@imeche.org)
- IMechE Formula Student AI Technical Support: [ian.murphy@member.imeche.org](mailto:ian.murphy@member.imeche.org)
