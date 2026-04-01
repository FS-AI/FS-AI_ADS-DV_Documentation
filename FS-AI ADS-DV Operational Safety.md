# FS-AI ADS-DV Operational Safety


## Document Control

| Version | Date       | Changes                  |
| ------- | ---------- | ------------------------ |
| 1.0     | 2026-03-XX | First issue of document. |

> The master copy of this document is stored at [FS-AI/FS-AI_ADS-DV_Documentation](https://github.com/FS-AI/FS-AI_ADS-DV_Documentation).<br>
> Always check you have the latest version, as printed copies, PDFs, downloads, or repository clones may be out of date.


## Table of Contents

- Manual Handling
- Transportation
- Static Testing
- Dynamic Testing


NOTE: This doc refers to Joystick operation which is not yet supported by 2026 ADS-DVs

Todo: Copy-paste Joystick procesures out of e.g. 'IMechE FS-AI ADS-DV Movement, Loading and Transport Procedures (2026 V1)'





**IMechE FS-AI ADS-DV Vehicle Loan Requirements and Info**

**Event Year 2024**

This document outlines the responsibilities of a Team or Organisation operating an IMechE FS-AI ADS-DV for development and testing associated with the Formula Student AI competition.

| **Version** | **Date** | **Changes** |
| --- | --- | --- |
| 1.0 | 2024-02-20 | Information copied into new document for Event Year 2024. |
|     |     |     |
|     |     |     |


**This document does not duplicate the content of the ADS-DV Operating Manual.**


**Unattended Storage and Access**

Access to the ADS-DV must be controlled by the Organising Entity to minimise any risks to uninvolved personnel.

- The ADS-DV may only be accessed by authorised personnel who have been briefed on the ADS-DV and read the Operation Manual.
- The ADS-DV must be stored in a secure and locked area when unattended. CCTV is recommended, please advise the IMechE Formula Student Office whether or not CCTV is in place.


**Handling & Lifting**

Note that the ground clearance of the ADS-DV is low and plastic ramps have been provided to allow smooth transitions over steps, lips, kerbs etc.

The ADS-DV must only be lifted using the Quick Lift jack on the underside of the chassis, or the wheels. The bodywork, including the nosecone, or the suspension, must not be used for lifting. If lifted using the wheels, safe handling & lifting practices must be employed under the supervision of competent and trained personnel.

**The ADS-DV weighs 300kg which means each wheel carries 75kg. Thus, a single person at each wheel is considered insufficient to lift the ADS-DV safely.**



**ADS-DV Operations**

To ensure safety during ADS-DV operations the following rules must be followed:

**Static Operation**

When in a workshop, other enclosed space or anywhere not specifically designated a dynamic area, the ADS-DV may only be used in the Static Operation mode.

Static Operations must be conducted as follows:

- There must be a Safe Area for general personnel (at least 5m away from the ADS-DV). This area must not be directly in front or behind the ADS-DV, but should be to the side.
- There must always be an ASR present to operate the vehicle with the RES.
- The ADS-DV must be lifted onto stands (wheels in the air) at all times.
- The stands used must conform to the following requirements:

- At least 90mm clearance below the wheels.
- At least 100mm clearance to the front wheels when on full steering lock.
- At least 800mm x 400mm spread of support under the chassis to avoid rocking / tipping.
- The 'skateboard' trolleys provided in the Inventory are considered suitable for Static Operation if used on a firm and level surface.
- **The Quick-Lift jack provided in the Inventory is NOT suitable for Static Operation and must only be used to lift the ADS-DV on and off the 'skateboard' trolleys.**

- The ASR must only be responsible for the mission selection and the RES - they must not perform any other duties when the ADS-DV is active.
- No other person than the ASR is allowed closer than 5m (outside the Safe Area) to the ADS-DV while it is active. Test operations should be conducted remotely using a wired or wireless communications link to the ADS-DV.
- The ASR should not stand directly in front or behind the ADS-DV.

**There is a risk of stones being flung off the tyres of the ADS-DV when performing a static test. It is recommended to clean off the tyres before a static test is conducted.**

- Any cables and wires must be kept clear of the rotating and / or steering wheels of the ADS-DV.

**Dynamic Operation**

Dynamic Operations of the ADS-DV are only permitted within a designated dynamic area.

Dynamic Operations must be conducted according to the same safety principles as the Formula Student Dynamic Events:

- There must be a Safe Area for general personnel (e.g. behind a wall).
- There must always be an ASR present to operate the vehicle with the RES.
- Any work on the ADS-DV in the Safe Area must take place according to the same rules as the Static Operations listed above (wheels in the air).
- The ADS-DV must enter and exit the designated dynamic area on the supplied 'skateboard' trolleys.
- The ASR must only be responsible for the mission selection and the RES - they must not perform any other duties when the ADS-DV is active.
- Only one other person in addition to the ASR is allowed 'over the wall' (outside the Safe Area) to perform any other duties relating to the ADS-DV.
- No tethered systems to the vehicle are allowed - wireless connections only (excepting the push-bar joystick).
- Prior to selecting a Mission and Activating the RES 'Go' signal the GEMS DA3 datalogger card must be inserted and confirmed to be logging (two Green lights) - this will require downloading the data to a PC between runs to ensure free storage space is always available.

To approve a designated dynamic area(s), please indicate the size, shape and location (a marked up Google map image is good) and submit to the IMechE Formula Student Office AND the IMechE Formula Student AI Technical Support.

**Designated dynamic areas will require the marking out of a 'safe run off' area which if the vehicle enters the ASR MUST activate the RES immediately.**

Designated dynamic areas may be approved for 'damp track operation' if requested, which may be subject to different 'safe run off' areas than dry track operation.

**A Dynamic Operations log sheet will be provided which must be kept with the ADS-DV and filled in by the ASR.**

**Operational Limits**

If the designated dynamic area requires it, the IMechE will specify hard-coded Operational Limits to be placed on the vehicle performance. For example, maximum speed, maximum torque (acceleration) or maximum steering angle (for narrow areas).

**If Operational Limits are required, the ASR will be responsible for loading and confirming these hard-coded limits.**

Some designated dynamic areas will require operational limits for 'damp track operation' only.

**Wet Weather Operation**

The ADS-DV is not 100% waterproof especially the InCarPC. Also, slick tyres are fitted. Therefore, operation in wet weather is only permissible according to the following conditions:

- Dynamic area must be approved for 'damp track operation' and if necessary, the appropriate Operational Limits must be applied (the ASR is responsible for this).
- No active rain must be falling.
- No standing water or puddles must be present.
- The ADS-DV must be dried down if it gets significantly wet and WD40 applied by cloth to exposed metallic areas to prevent corrosion. EXCEPT the brake discs and pads.
- The InCarPC must be regularly inspected for water. If any water is present on or around the InCarPC the operation must be stopped until conditions dry out.

Plastic sheeting may be applied to keep the InCarPC dry. This must be transparent so that any water that does reach the InCarPC can be observed, and corrective action taken.

**It is not permitted to operate the ADS-DV in ice or snow conditions.**

**Airports & RF Interference**

The ADS-DV Remote Emergency Stop (RES) operates on a frequency range of 430 to 440MHz. It has been observed previously that operation of the RES may be affected by RF systems present at airports.

If an airport is to be designated as a dynamic area, the airport should be informed that the RES radiates in this frequency band and must indicate approval.

If the ADS-DV fails to operate correctly, or spurious RES activation is observed, when in the presence of RF systems, please inform IMechE Formula Student AI Technical Support.

**Support Contacts**

**IMechE Formula Student Office**

Naomi Rolfe &lt;<Naomi.Rolfe@imeche.org>&gt;

**IMechE Formula Student AI Technical Support**

Ian Murphy &lt;<ian.murphy@member.imeche.org>&gt;















**FS-AI ADS-DV Movement, Loading and Transport Procedures**

This document outlines the procedure for moving loading / unloading and transporting the FS-AI ADS-DV.

| **Version** | **Date** | **Changes** |
| --- | --- | --- |
| 1.0 | 2023-09-26 | First issue. |
|     |     |     |
|     |     |     |

**Introduction**

The Institution of Mechanical Engineers (IMechE) Formula Student Artificial Intelligence (FS-AI) Autonomous Driving Systems - Dedicated Vehicle (ADS-DV) - (hereafter simply described as 'the ADS-DV') is a driverless vehicle used at the annual Formula Student competition.

This document is intended to accompany the ADS-DV at all times and be referred to by personnel responsible for moving, loading / unloading and transporting a vehicle, and preparing it for storage.

Pages 6 to 10 are formatted in large type suitable for laminating into a reference card.

**NOTE: This document does not fully duplicate the content of the ADS-DV Operating Manual, just those aspects related to moving, loading / unloading and transport.**

**Refer to the full ADS-DV Operating Manual for other aspects of vehicle operation.**

**Support Contacts**

**IMechE Formula Student Office**

Naomi Rolfe &lt;<Naomi.Rolfe@imeche.org>&gt;

**IMechE Formula Student AI Technical Support**

Ian Murphy &lt;<ian.murphy@member.imeche.org>&gt;

**Inventory**

The following is an Inventory of the equipment & accessories which must always accompany the ADS-DV during transportation. Without the use of Inventory items the ADS-DV brakes cannot be released and the wheels will not turn.

- Grossfunk Remote Emergency Stop (RES) with battery:

Confirm you have the correct RES for the car [refer to colour coded stickers]

(photo)

- Grossfunk RES spare battery, battery charger & wall plug:

(photo)

- Joystick & Joystick cable:

TBD

- Set of 4x black plastic ramps.

(photo)

- Red Keys (x3 + 1 spare)

(photo)

- Quick-Lift jack.

(photo)

- Pair of 'skateboard' trolleys.

(photo)

- Pushbar

(photo)


In the event of loss or damage to any of the Inventory, immediately inform the IMechE Formula Student Office and IMechE Formula Student AI Technical Support, as contingency procedures may be required.

**NOTE: the Full Inventory of the ADS-DV includes additional items not required for transport.**

**If these are to accompany the ADS-DV they will be itemised separately.**


**Handling, Protecting and Securing the ADS-DV**

**Handling & Lifting**

Note that the ground clearance of the ADS-DV is low and the plastic ramps have been provided to allow smooth transitions over steps, lips, kerbs etc.

The ADS-DV must only be lifted using the Quick Lift jack on the underside of the chassis, or by the wheels. The bodywork, including the nosecone, or the suspension, must not be used for lifting. If lifted using the wheels, safe handling & lifting practices must be employed under the supervision of competent and trained personnel.

**NOTE: The ADS-DV weighs 300kg which means each wheel carries 75kg.  
Thus, a single person at each wheel is insufficient to lift the ADS-DV safely.**


**Protection during Transport**

The ADS-DV and Inventory must be only transported inside a covered car carrier or by covered trailer.

**NOTE: The ADS-DV is not fully waterproof and must not be transported uncovered, or in any way which risks water ingress.**


**Securing during Transport**

At all times during transport the ADS-DV must be securely tied down using at least 4 straps preventing longitudinal, lateral and twisting motion of the vehicle. The straps must attach to the ADS-DV wheels and not the suspension or bodywork.

At all times during transport the Inventory must be secured such that it cannot slide around and sustain damage, or impact the ADS-DV in any way.

The ADS-DV does not have any specific access security provision and is not tamper proof. It should not be left unattended in an insecure environment. The covered car carrier / trailer used for transport should be locked.


**Airports & Radio Frequency Interference**

The ADS-DV Remote Emergency Stop (RES) operates on a Radio Frequency (RF) range of 430 to 440MHz. It has been observed previously that operation of the RES may be affected by RF systems present at airports.

If the ADS-DV fails to operate correctly, or spurious RES activation is observed, when in the presence of RF systems, please inform IMechE Formula Student AI Technical Support.


**ADS-DV Movement Procedure**

**Personnel Required**

Moving / manoeuvring the ADS-DV requires a minimum of two personnel. Three is recommended. The following roles are defined:


**Safety Supervisor**

They must not perform any other task. They must observe all movement of the ADS-DV and be ready to press the RES Emergency Stop button if required.

**Vehicle Handler(s)**

Vehicle Handlers can push the vehicle as required, whether on the ground with the brakes released, or with the vehicle on the trolleys.

It is recommended one vehicle handler operate the Joystick and one push the vehicle.

- PPE in the form of Gloves and Safety Shoes is recommended for Vehicle Handlers pushing the vehicle.


**Risk Assessment**

The primary risk associated with moving the ADS-DV is 'roll-away' on a slope. To mitigate this risk the following actions are recommended:

- Avoid moving the ADS-DV on a surface with a slope greater than 10% / 10 in 1.

- This includes any ramps used when loading the ADS-DV onto a car carrier or trailer, or a 'tilt bed' car carrier or trailer.
- Steeper loading ramps will require the use of a winch:
  - The ADS-DV does not have a 'towing eye'. A winch cable may be attached to a suspension wishbone as close to the bodywork as possible. Protect the ADS-DV from damage from the cable using padding.

- Brief the Vehicle Handler(s) to always push the vehicle up a slope, not pull, and to be aware of the risk of 'roll-away'.
- Ensure the Safety Supervisor is watching the ADS-DV at all times.


**NOTE: Only push using the ADS-DV using the pushbar or the tyres, never the bodywork or suspension.**


**Preparing the ADS-DV for Storage**

Once movement is complete, the ADS-DV must be fully powered down to avoid draining the batteries.

- Press the Emergency Stop Button on the RES and leave it pressed.
  - The Red Status LED will go out. This is the powered-down state of the RES. Leaving the RES on, with the Status LED illuminated, will drain the RES battery and must be avoided.
  - Store the RES safely.
- Turn off the three side switches by rotating the 'Red Keys' anti-clockwise. Start with the AS, then the TS and finally the LV.
- Remove the three 'Red Keys' and store safely along with the spare.
- Disconnect the Joystick from the MPP and store safely.
- Re-confirm the AI Master Switch (AIMS) is OFF (Anti-Clockwise rotation).

**NOTE: the ADS-DV will now have its brakes locked on.**

**It is not possible to power down the vehicle without the brakes being locked on
