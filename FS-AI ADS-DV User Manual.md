FS-AI ADS-DV User Manual

Version	Date	Changes
1.0	2026-03-XX	First issue of document.


ToDo: Inertia Switch

NOTE: The master copy of this document is stored at [URL]. Always check you have the latest version as printed copies, PDFs, downloads or clones may be out of date.


Table of Contents

1.	Introduction
2.	Key Equipment
3.	User Interface
4.	Inspection
5.	Preparation for Operation
5.1.	Equipment Required
5.2.	Procedure
6.	Autonomous Operation
6.1.	Equipment Required
6.2.	Procedure
7.	Preparation for Storage
7.1.	Equipment Required
7.2.	Procedure
8.	Charging the Traction Battery
8.1.	Equipment Required
8.2.	Procedure
9.  Charging the RES Battery
9.1.	Equipment Required
9.2.	Procedure
10.	Support Contacts
 

1.	Introduction

This document provides details of the procedures that should be followed to operate the FS-AI ADS-DV safely.

 
2.	Key Equipment

The Key Equipment for operating the ADS-DV consists of:
•	ADS-DV
•	Remote Emergency Stop (RES)
•	Switch Keys (x3)
•	AI Power Switch Key
•	MPP Dongle
•	MPP Joystick
•	Datalogger Memory Card
•	Traction Battery Charger
•	RES Battery Charger

NOTE: The ADS-DV may be provided with additional items not listed above, this is not a complete inventory. These may include:
•	Quick Lift Jack
•	Trolleys (x2)
•	Plastic Ramps
•	Spares

(Photos will be added) 


3.	User Interface

The key elements of the ADS-DV User Interface are:

Key Switches (x3)

Remote Emergency Stop (RES)

Side Emergency Stop Buttons (x2)

AI Power Switch & AI Power Switch Key

Multi-Purpose Port (MPP) & MPP Dongle

Charge Port

TSAL LED Indicators

Touch Screen Interface

(Photos to be added) 


4.  Inspection

Before operating the ADS-DV it must be inspected for any damage or anomaly by a competent person.

The exact inspection schedule and level of detail depends upon how long the vehicle has been in storage.

(Inspection Schedule to follow)


5.	Preparation for Operation

5.1.	Equipment
•	MPP Dongle
•	Remote Emergency Stop (RES)
•	Switch Keys (x1)

5.2.	Procedure
1.	Verify the AI Power Switch is switched ‘Off’.
2.	Connect the MPP Dongle to the MPP.
3.	Ensure the RES has a charged RES Battery installed.
4.	Enable the RES by twisting the RES Emergency Stop button until it pops up.
5.	Verify the RES is active by observing the Red LED is lit.

(Photo to be added)

NOTE: The RES Red LED will flash if the RES Battery is low on charge. It may also emit an audible tone. If this occurs, swap the RES Battery for a charged one and recharge the flat one using the provided RES Battery Charger.

6.	Verify the Side Emergency Stop Switches are ‘Out’. (If not, twist them so they pop out).
7.	Turn ‘On’ the LV Master Switch.
8.	Verify the TSAL indicator LEDs show Green.
9.	Verify the Touch Screen Interface starts up.
10.	Verify the E-Stop Loop indicator on the Touch Screen shows Green.

(Photo to be added)

NOTE: To complete the E-Stop Loop all the following need to be correct:
•	RES active
•	Side Emergency Stop Switches ‘Out’
•	MPP Dongle present
•	Inertia Switch ‘Closed’

11.	Verify the LV Battery voltage is above 13.5V, indicating the DCDC converter is working. Typically, this will show 13.6V, but may fluctuate slightly.

NOTE: If the LV Battery voltage remains below 13.0V, turn off the LV Master Switch and contact FS-AI Technical Support.

(Photo to be added)

12.	Verify the Traction Battery voltage is above 47.5V. If it is lower than this, do not operate the vehicle. Instead, charge the Traction Battery according to the procedure below.

(Photo to be added)

13.	Verify the status of the ADS-DV systems on the Touch Screen as follows:
AS Init
OP Init
TS Init
EBS Init

(Photo to be added)

Assuming the above is all correct, the ADS-DV is now ready for Autonomous Operation.


6.	Autonomous Operation

Autonomous Operation of the ADS-DV requires the presence of valid CAN signals from the Compute Platform to the ADS-DV.

NOTE: Currently the software interface is unchanged from previous years and the document ‘ADS-DV_Software_Interface_Specification_v4.0.pdf’ remains valid.

6.1.	Equipment
•	MPP Dongle
•	Remote Emergency Stop (RES)
•	Switch Keys (x3)
•	AI Power Switch Key
•	Datalogger Memory Card
•	Compute Platform

NOTE: The Compute Platform refers to any hardware used to send CAN signals to the ADS-DV. This may be the provided InCarPC or any other hardware used to control the ADS-DV.

6.2.	Procedure
1.	Verify the ADS-DV is ready according to 'Inspection' and ‘Preparation for Operation’ above.
2.	Verify the Compute Platform is connected to one of the AI Power & CAN connectors of the ADS-DV.
3.	Insert the AI Power Switch Key and turn on the AI Power Switch (or confirm it is already on), to supply power to the Compute Platform.

(Photos to be added)

4.	Turn on the LV Master Switch (or confirm it is already on). 

(Photo to be added)

5.	Turn ‘On’ the AS Master Switch and turn ‘On’ the Traction System Master Switch.

(Photo to be added)

6.	Ensure the Compute Platform is sending CAN signals to the ADS-DV.

NOTE: As soon as valid CAN signals are received by the ADS-DV, the Traction System and Emergency Brake System will activate.

7.	Wait for the TSAL Indicator LEDs to show Red, indicating the Traction System is active.
8.	Wait for the Emergency Brake System to transition from ‘EBS Init’ to ‘EBS Armed’ (the sound of the pump running may be heard).

NOTE: If the Emergency Brake System has been completely discharged for storage, it may take more than one pump cycle to Arm. This is normal. The status of the Emergency Brake System can be viewed on the Touch Screen. It will progress from ‘EBS Init’ through ‘EBS Charging’ to ‘EBS Armed’.

9.	Wait for the Autonomous System to progress from ‘AS Init’ to ‘AS Off’.

(Photo to be added)

10.	Insert the Datalogger Memory Card (or confirm insertion), if required.

(Photo to be added)

11.	Select a Mission using the Touch Screen drop-down and press ‘Set’.

(Photo to be added)

12.	Wait for the Autonomous System to progress from ‘AS Off’ to ‘AS Ready’, indicated on the Touch Screen and also by the TSAL Indicator LEDs showing Red + Yellow.

(Photo to be added)

13.	Wait for the TSAL Indicator LEDs to flash Blue as well as show Red + Yellow, indicating the 5 second timer has elapsed. This 5 second timer is to allow the ASR to move away from the vehicle.

(Photo to be added)

NOTE: The Autonomous State Machine CAN signal requirements are fully documented in ‘ADS-DV_Software_Interface_Specification_v4.0.pdf’. The ADS-DV will not progress from 'AS Off' to ‘AS Ready’, or from 'AS Ready' to 'AS Driving' if these requirements are not strictly followed.

14.	Activate the RES ‘Go’ switch by toggling it from ‘0’ to ‘1’. This will transition the Autonomous System from ‘AS Ready’ to ‘AS Driving’.

(Photo to be added)

15.	Conduct the Mission by correctly controlling the ADS-DV using the CAN signals.

NOTE: The ADS-DV MUST be observed at all times by the ASR. The Remote Emergency Stop MUST be used if the ADS-DV shows any anomalous behaviour.
NOTE: Full details on ADS-DV Operational Safety, for both Static and Dynamic operation, are documented separately.

16. Regardless of the success or failure of the Mission (resulting in either ‘AS Finished’ or ‘Emergency Brake’) the ADS-DV must be reset after every Mission by turning ‘Off’ the LV Master Switch, AS Master Switch and TS Master Switch.

17.	Remove the Datalogger Memory Card if the data is required for analysis.

18.	Optionally, power down the Compute Platform by turning ‘Off’ the AI Power Switch.

NOTE: If the AI Power Switch is left ‘On’ it is important to minimise the time spent with the LV Master Switch ‘Off’, to avoid the Compute Platform over-discharging the LV Battery and causing degradation of the battery performance.

NOTE: Ensure the AI Power Switch is switched ‘Off’ even if the Compute Platform is removed.

EITHER: Prepare the ADS-DV for storage (see below) OR return to Step 1 to conduct another mission.


7.	Preparation for Storage

The ADS-DV should be prepared for storage any time it is left unattended.

7.1.	Equipment
•	MPP Dongle
•	Remote Emergency Stop (RES)
•	Switch Keys (x1)
•	Datalogger Memory Card

7.2.	Procedure
1.	Remove the AS Master Switch and Traction System Master Switch keys (if present) and store securely.
2.	Remove the Datalogger Memory Card (if present) and store securely.
3.	Connect the MPP Dongle to the MPP.
4.	Verify the AI Power Switch is switched ‘Off’, remove the AI Master Switch Key (if present) and store securely.

NOTE: Ensure the AI Power Switch is switched ‘Off’ even if no Compute Platform is installed.

5.	Ensure the RES has a charged battery installed.
6.	Enable the RES by twisting the Emergency Stop button until it pops up.
7.	Verify the RES is active by observing the Red LED is lit.

NOTE: The RES Red LED will flash if the battery is low on charge. It may also emit an audible tone. If this occurs, swap the RES battery for a charged one and recharge the flat one.

8.	Verify the Side Emergency Stop Switches are ‘Out’. (If not, twist them so they pop out).
9.	Turn ‘On’ the LV Master Switch.
10.	Verify the TSAL indicator LEDs show Green.
11.	Verify the Touch Screen Interface starts up.
12.	Verify the E-Stop Loop indicator on the Touch Screen shows Green.

NOTE: To complete the E-Stop Loop all the following need to be correct:
•	RES active
•	Side Emergency Stop Switches ‘Out’
•	MPP Dongle present
•	Inertia Switch ‘Closed’

13.	Verify the Traction Battery voltage is above 47.5V. If it is lower than this, charge the Traction Battery to at least 50.0V according to the procedure below.
15.	On the Touch Screen, switch to the ‘Service’ page and press the ‘Brake Discharge’ button. Ensure the button shows pressed.

(Photo to be added)

16.	Verify the Emergency Brake System is discharging by observing the two Brake Pressures on the Touch Screen. These will deplete as the Emergency Brake System is pulsed on and off (this may be audible at first but will usually go quiet BEFORE the brakes are fully discharged).

NOTE: When the Brake Pressures are depleted AND the wheels of the ADS-DV can be turned manually, the discharge is complete.

17.	Turn ‘Off’ the LV Master Switch, remove the Switch Key and store securely.
18.	Turn ‘Off’ the RES by pressing in the Emergency Stop button and observing the Red LED is unlit.
19.	Store the RES securely and recharge the RES Battery if required.
20.	Remove the MPP Dongle and store securely.

NOTE: During storage the brake lines remain locked-off by a normally closed valve. Thus, a variation in temperature or ambient pressure may result in the wheels re-locking. If this occurs the residual brake line pressure is still very low compared to the deployed EBS pressure.

 
8.	Charging the Traction Battery

NOTE: The Traction Battery MUST be recharged if the voltage displayed on the Touch Screen is below 47.5V with the ADS-DV idle, or in preparation for storage.

8.1.	Equipment
•	MPP Dongle
•	Remote Emergency Stop (RES)
•	Switch Keys (x1)
•	Traction Battery Charger

(Photo to be added)

8.2.	Procedure
1.	Ensure the Traction Battery Charger is unplugged from the mains and the Power Switch on the rear of the Traction Battery Charger is set to ‘0’ (Off).

(Photo to be added)

2.	Connect the Traction Battery Charger Output Connector to the Charge Port at the rear of the ADS-DV.

NOTE: Ensure the Traction Battery Charger Output Connector is fully engaged and the Red latch is pushed forward.

(Photo to be added)

3.	Connect the MPP Dongle to the MPP.
4.	Ensure the RES has a charged battery installed.
5.	Enable the RES by twisting the Emergency Stop button until it pops up.
6.	Verify the RES is active by observing the Red LED is lit.

NOTE: The RES Red LED will flash if the battery is low on charge. It may also emit an audible tone. If this occurs, swap the RES battery for a charged one and recharge the flat one.

7.	Verify the Side Emergency Stop Switches are ‘Out’. (If not, twist them so they pop out).
8.	Turn ‘On’ the LV Master Switch.
9.	Verify the TSAL indicator LEDs show Green.
10.	Verify the Touch Screen Interface starts up.
11.	Verify the E-Stop Loop indicator on the Touch Screen shows Green.

NOTE: To complete the E-Stop Loop all the following need to be correct:
•	RES active
•	Side Emergency Stop Switches ‘Out’
•	MPP Dongle present
•	Inertia Switch ‘Closed’

12.	Verify the LV Battery voltage is above 13.5V, indicating the DCDC converter is working. Typically, this will show 13.6V, but may fluctuate slightly.
13.	On the Touch Screen, switch to the ‘Service’ page and press the ‘Charge Enable’ button. Ensure the button shows pressed.

(Photos to be added)

14.	Plug the Traction Battery Charger into the mains.
15.	Turn the Power Switch on the rear of the Traction Battery Charger to ‘1’ (On).
16.	Verify that the LED on the Traction Battery Charger shows Orange (or Green) but not Red. If not, or if charging does not start, cycle the Power Switch on the rear of the Traction Battery Charger from ‘1’ to ‘0’ and back to ‘1’.

(Photo to be added)

17.	Verify on the Touch Screen that the Traction Battery voltage increases and the current goes negative (showing current is flowing to the Traction Battery).

(Photo to be added)

NOTE: Depending on the state of charge the current will vary from -25.0A to approx. -2.0A while the Traction Battery voltage will vary from approx. 52.0V to approx. 58.0V.

NOTE: The Traction Battery charge may be terminated at any time, but it is recommended to wait until the current is lower than 5.0A and / or the voltage is higher than 56.0V.

18.	Turn the Power Switch on the rear of the Traction Battery Charger to ‘0’ (Off).
19.	Unplug the Traction Battery Charger from the mains.
20.	Turn ‘Off’ the LV Master Switch.
21.	Turn ‘Off’ the RES by pressing in the Emergency Stop button and observing the Red LED is unlit.
22.	Disconnect the Traction Battery Charger Output Connector from the Charge Port at the rear of the ADS-DV.

NOTE: First pull the Red latch rearwards, then depress BOTH the Orange latch tabs before pulling the Charger Output Connector off the Charge Port. Otherwise, connector damage may occur.

(Photos will be added)

23.	Store the Traction Battery Charger safely and securely to avoid damage.

NOTE: At this point, follow either the ‘Preparation for Operation’ procedure, or the ‘Preparation for Storage’ procedure, depending upon requirements,


9.	Charging the RES Battery

9.1.	Equipment
•	RES Battery Charger

(Photo to be added)

9.2.	Procedure
1.	TBD

(Photo to be added)
 
 
9.	Support Contacts

IMechE Formula Student Office
Formula Student <fs@imeche.org>

IMechE Formula Student AI Technical Support
Ian Murphy <ian.murphy@member.imeche.org>
