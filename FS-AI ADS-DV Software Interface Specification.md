CAN Interface Specification
Handshaking
Speed Mode
Torque Mode



ADS-Dv Software Interface Specification

Version 4.0

# Introduction

This document lists the signals on the CAN_B bus of the Formula Student ADS-DV demonstrator vehicle that is used for communications between the AI Computer and the Vehicle Control Unit (VCU), and the autonomous driving state machine that complies with the Formula Student Rules. It should be used in combination with the CAN database (ADSDV_2021_VCU_AI_interface_v2.dbc). The CAN_B bus uses the CAN 2.0B protocol and runs at a baud rate of 500 kbit/s.

This CAN interface has been designed to comply with the 2019 Formula Student Rules for driverless vehicles and the supplementary regulations for the 2018 Formula Student Germany (FSG) competition, which provide more detailed guidelines on the data that must be logged for driverless vehicles. Any signals that are only relevant to the FSG data logging rules are highlighted accordingly.

## Glossary of Terms

| ADS-DV | Autonomous Driving System - Dedicated Vehicle |
| --- | --- |
| AI Computer | Designation for the autonomous driving computer used in the Formula Student Rules |
| AMI | Autonomous Mission Indicator |
| AS  | Autonomous System |
| ASMS | Autonomous System Master Switch |
| ASSI | Autonomous System Status Indicator |
| EBS | Emergency Braking System |
| FSG | Formula Student Germany |
| MPP | Multi-Purpose Port |
| RES | Remote Emergency Stop |
| SDC | Shutdown Circuit |
| TS  | Tractive System |
| TSMS | Tractive System Master Switch |
| VCU | Vehicle Control Unit |

## Change Log

| Version | Date | Changes made |
| --- | --- | --- |
| 0.2 | 24 Oct 2018 | First release |
| 2.0 | 21 May 2019 | CAN DBC database file name added,<br><br>Drive motor torque interface simplified: axle torque request signals changed to unsigned \[0-195 Nm\],<br><br>Minimum axle torque feedback signals removed (FRONT_AXLE_TRQ_MIN_Nm & REAR_AXLE_TRQ_MIN_Nm),<br><br>List of implausible operating conditions added,<br><br>'Manual' option for AMI state removed. |
| 3.0 | 27 Jan 2021 | Friction braking messages (AI2VCU_Brake and VCU2AI_Brake) updated to allow independent variation of brake pressure requests for the front and rear axles,<br><br>steering angle limits revised to ±24.0°,<br><br>battery charging procedure and BMS faults added to VCU2AI_Status fault diagnostics,<br><br>AMI_STATE enumerations updated to include new 'Static inspection A', 'Static inspection B' and 'Autonomous demo' missions for scrutineering,<br><br>Unused VCU diagnostics messages removed,<br><br>List of reserved CAN IDs updated. |
| 4.0 | 25 Jun 2021 | CAN specifications updated to included altered message DLC values and transmission rates,<br><br>VCU_STATUS message added to CAN specification,<br><br>handshake and CAN message timeout error information updated,<br><br>list of fault conditions in autonomous driving mode added,<br><br>list of reserved CAN IDs updated. |

# CAN Messages

## AI Computer Messages

| Message name | AI2LOG_Dynamics2 |     |     |
| --- | --- |     |     | --- |
| CAN ID | 501h |     |     |
| DLC | 6   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Vehicle dynamics message to comply with Formula Student Germany (FSG) data logging requirements |     |     |
| Signal |     | Type | Description |
| Accel_longitudinal_ms2 |     | Signed | Longitudinal vehicle acceleration \[m/s<sup>2</sup>\] |
| Accel_lateral_ms2 |     | Signed | Lateral vehicle acceleration \[m/s<sup>2</sup>\] |
| Yaw_rate_degps |     | Signed | Yaw rate \[°/s\] |

| Message name | AI2VCU_Status |     |     |
| --- | --- |     |     | --- |
| CAN ID | 510h |     |     |
| DLC | 8   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | AI Computer status signals for the VCU and some FSG logging signals |     |     |
| Signal |     | Type | Description |
| HANDSHAKE |     | Unsigned | Handshake bit to check communications between the AI Computer and VCU |
| ESTOP_REQUEST |     | Enum | AI request for a vehicle emergency stop:<br><br>0 = no E-stop requested  <br>1 = E-stop requested |
| MISSION_STATUS |     | Enum | Autonomous mission status for the VCU to determine which autonomous driving state it should be in:  <br>0 = not selected<br><br>1 = mission selected<br><br>2 = running<br><br>3 = finished |
| DIRECTION_REQUEST |     | Enum | Vehicle direction request:  <br>0 = neutral  <br>1 = forward |
| LAP_COUNTER |     | Unsigned | Lap counter for the 'Track drive' mission (FSG data logging requirement) |
| CONES_COUNT_ACTUAL |     | Unsigned | Number of cones that have currently been detected (FSG data logging requirement) |
| CONES_COUNT_ALL |     | Unsigned | Running counter of detected cones (FSG data logging requirement) |
| VEH_SPEED_ACTUAL |     | Unsigned | Actual vehicle speed (FSG data logging requirement) |
| VEH_SPEED_DEMAND |     | Unsigned | Demanded vehicle speed (FSG data logging requirement) |

| Message name | AI2VCU_Drive_F |     |     |
| --- | --- |     |     | --- |
| CAN ID | 511h |     |     |
| DLC | 4   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Requests for the front drive motor |     |     |
| Signal |     | Type | Description |
| FRONT_AXLE_TRQ_REQUEST |     | Unsigned | Requested absolute front axle torque (motor torque × gear ratio). Whether torque is positive (driving) or negative (braking) will depend on the setting of the motor speed limit  <br>Range: \[0, 195\] |
| FRONT_MOTOR_SPEED_MAX |     | Unsigned | Maximum motor speed for vehicle speed control  <br>Range: \[0, 4000\] |

| Message name | AI2VCU_Drive_R |     |     |
| --- | --- |     |     | --- |
| CAN ID | 512h |     |     |
| DLC | 4   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Requests for the rear drive motor |     |     |
| Signal |     | Type | Description |
| REAR_AXLE_TRQ_REQUEST |     | Unsigned | Requested absolute rear axle torque (motor torque × gear ratio)  <br>Range: \[0, 195\] |
| REAR_MOTOR_SPEED_MAX |     | Unsigned | Maximum motor speed for vehicle speed control  <br>Range: \[0, 4000\] |

| Message name | AI2VCU_Steer |     |     |
| --- | --- |     |     | --- |
| CAN ID | 513h |     |     |
| DLC | 2   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Steer angle request |     |     |
| Signal |     | Type | Description |
| STEER_REQUEST_deg |     | Signed | Requested steer angle according to the bicycle model for vehicle dynamics. A positive angle turns the front wheels to the left according to the ISO 8855 vehicle co-ordinate system:<br><br>  Range: \[-21.0, 21.0\] |

| Message name | AI2VCU_Brake |     |     |
| --- | --- |     |     | --- |
| CAN ID | 514h |     |     |
| DLC | 2   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Hydraulic brake pressure request |     |     |
| Signal |     | Type | Description |
| HYD_PRESS_F_REQ_pct |     | Unsigned | Normalised hydraulic pressure request for the front axle friction brakes.  <br>Range: \[0, 100\] |
| HYD_PRESS_R_REQ_pct |     | Unsigned | Normalised hydraulic pressure request for the rear axle friction brakes.  <br>Range: \[0, 100\] |

## Vehicle Control UNIT (VCU) Messages

| Message name | VCU2LOG_Dynamics1 |     |     |
| --- | --- |     |     | --- |
| CAN ID | 500h |     |     |
| DLC | 8   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Vehicle dynamics message to comply with Formula Student Germany (FSG) data logging requirements |     |     |
| Signal |     | Type | Description |
| Speed_actual_kmh |     | Unsigned | Actual vehicle speed |
| Speed_target_kmh |     | Unsigned | Target vehicle speed |
| Steer_actual_deg |     | Signed | Actual steer angle (bicycle model) |
| Steer_target_deg |     | Signed | Requested steer angle (bicycle model) |
| Brake_actual_pct |     | Unsigned | Actual mechanical braking percentage |
| Brake_target_pct |     | Unsigned | Requested mechanical braking percentage |
| Drive_trq_actual_pct |     | Signed | Sum of actual front and rear axle torque |
| Drive_trq_target_pct |     | Signed | Sum of requested front and rear axle torque |

| Message name | VCU2LOG_Status |     |     |
| --- | --- |     |     | --- |
| CAN ID | 502h |     |     |
| DLC | 5   |     |     |
| Tx cycle time | 100ms |     |     |
| Description | Vehicle status reporting to comply with Formula Student Germany (FSG) data logging requirements |     |     |
| Signal |     | Type | Description |
| State_ASSI |     | Enum | Autonomous System Status Indicator (ASSI) state:  <br>1 = AS_OFF  <br>2 = AS_READY  <br>3 = AS_DRIVING  <br>4 = EMERGENCY_BRAKE  <br>5 = AS_FINISHED |
| State_EBS |     | Enum | Emergency Braking System (EBS) state:  <br>1 = unavailable<br><br>2 = armed<br><br>3 = triggered |
| AMI_STATE |     | Enum | Autonomous Mission Indicator (AMI) state:<br><br>0 = not selected<br><br>1 = Acceleration<br><br>2 = Skidpad<br><br>3 = Autocross<br><br>4 = Track drive<br><br>5 = Static inspection A<br><br>6 = Static inspection B<br><br>7 = Autonomous demo |
| State_steering |     | Enum | Steering system status:<br><br>0 = off<br><br>1 = active |
| State_service_brake |     | Enum | Service brake (mechanical friction brakes) status:<br><br>1 = disengaged<br><br>2 = engaged<br><br>3 = available |
| Lap_counter |     | Unsigned | Signal gatewayed from AI2VCU_Status (510h) |
| Cones_count_actual |     | Unsigned | Signal gatewayed from AI2VCU_Status (510h) |
| Cones_count_all |     | Unsigned | Signal gatewayed from AI2VCU_Status (510h) |

| Message name | VCU2AI_Status |     |     |
| --- | --- |     |     | --- |
| CAN ID | 520h |     |     |
| DLC | 8   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | VCU and powertrain status reporting to the AI Computer |     |     |
| Signal |     | Type | Description |
| HANDSHAKE |     | Unsigned | Handshake bit to check communications between the VCU and AI Computer |
| SHUTDOWN_REQUEST |     | Enum | VCU request for AI Computer to shut down<br><br>\[0 = no shutdown; 1 = shutdown requested\] |
| AS_SWITCH_STATUS |     | Enum | Status of the autonomous system master switch (ASMS)  <br>\[0 = off; 1 = on\] |
| TS_SWITCH_STATUS |     | Enum | Status of the tractive system master switch (TSMS)  <br>\[0 = off; 1 = on\] |
| GO_SIGNAL |     | Enum | Remote "Go" signal to allow the vehicle to start driving:<br><br>0 = no go<br><br>1 = go |
| STEERING_STATUS |     | Enum | Steering system status:  <br>0 = off<br><br>1 = active |
| AS_STATE |     | Enum | Autonomous system state:  <br>1 = AS_OFF  <br>2 = AS_READY  <br>3 = AS_DRIVING  <br>4 = EMERGENCY_BRAKE  <br>5 = AS_FINISHED |
| AMI_STATE |     | Enum | Autonomous Mission Indicator (AMI) state:<br><br>0 = not selected<br><br>1 = Acceleration<br><br>2 = Skidpad<br><br>3 = Autocross<br><br>4 = Track drive<br><br>5 = Static inspection A<br><br>6 = Static inspection B<br><br>7 = Autonomous demo |
| FAULT_STATUS |     | Enum | Flag to indicate the presence of a critical fault:<br><br>0 = no faults<br><br>1 = fault detected |
| WARNING_STATUS |     | Enum | Flag to indicate the presence of a warning. Used for fault diagnosis after a run:<br><br>0 = no warning<br><br>1 = warning active |
| WARN_BATT_TEMP_HIGH |     | Enum | High traction battery temperature warning flag:  <br>0 = no warning<br><br>1 = warning active |
| WARN_BATT_SOC_LOW |     | Enum | Low traction battery SOC warning flag:  <br>0 = no warning<br><br>1 = warning active |
| AI_ESTOP_REQUEST |     | Enum | Flag for E-stop request from the AI Computer:<br><br>0 = inactive<br><br>1 = E-stop requested |
| HVIL_OPEN_FAULT |     | Enum | Flag for open-circuit fault in the shutdown circuit / HVIL:  <br>0 = no fault<br><br>1 = fault detected |
| HVIL_SHORT_FAULT |     | Enum | Flag for short-circuit fault in the shutdown circuit / HVIL:  <br>0 = no fault<br><br>1 = fault detected |
| EBS_FAULT |     | Enum | Emergency Braking System fault flag:  <br>0 = no fault<br><br>1 = fault detected |
| OFFBOARD_CHARGER_FAULT |     | Enum | Offboard battery charger fault flag:  <br>0 = no fault<br><br>1 = fault detected |
| AI_COMMS_LOST |     | Enum | AI-VCU CAN communications fault flag:  <br>0 = no fault<br><br>1 = fault detected |
| AUTONOMOUS_BRAKING_  <br>FAULT |     | Enum | NEUTRAL direction request made while vehicle is still moving:  <br>0 = no fault<br><br>1 = fault detected |
| MISSION_STATUS_FAULT |     | Enum | MISSION_STATUS set to 'FINISHED' while vehicle is moving:  <br>0 = no fault<br><br>1 = fault detected |
| CHARGE_PROCEDURE_FAULT |     | Enum | AS or TS master switches are on when the battery is being charged:<br><br>0 = no fault<br><br>1 = fault detected |
| BMS_FAULT |     | Enum | BMS fault detection flag:<br><br>0 = no fault<br><br>1 = fault detected |
| BRAKE_PLAUSIBILITY_FAULT |     | Enum | In torque control drive motor operation, a non-zero drive torque demand is applied at the same time as a non-zero brake pressure demand:<br><br>0 = no fault<br><br>1 = fault detected |
| SHUTDOWN_CAUSE |     | Enum | Enumerated list identifying the fault that caused the VCU to shut down:<br><br>0 = no shutdown<br><br>1 = AI Computer request<br><br>2 = HVIL open-circuit fault<br><br>3 = HVIL short-circuit fault<br><br>4 = EBS fault<br><br>5 = Offboard battery charger fault<br><br>6 = AI communications fault<br><br>7 = Autonomous braking fault<br><br>8 = Mission status fault<br><br>9 = Charging procedure fault<br><br>10 = BMS fault<br><br>11 = Brake plausibility fault |

| Message name | VCU2AI_Drive_F |     |     |
| --- | --- |     |     | --- |
| CAN ID | 521h |     |     |
| DLC | 6   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Feedback from the front drive motor |     |     |
| Signal |     | Type | Description |
| FRONT_AXLE_TRQ |     | Signed | Actual front axle drive motor torque<br><br>Range: \[-195, 195\] |
| FRONT_AXLE_TRQ_REQUEST |     | Unsigned | Requested front axle torque (AI2VCU_Drive_F, FRONT_AXLE_TRQ_REQUEST_Nm) |
| FRONT_AXLE_TRQ_MAX |     | Unsigned | Maximum allowable drive torque at axle  <br>Range: \[0, 195\] |

| Message name |     | VCU2AI_Drive_R |     |     |     |     |
| --- |     | --- |     |     |     |     | --- |
| CAN ID |     | 522h |     |     |     |     |
| DLC |     | 6   |     |     |     |     |
| Tx cycle time |     | 10ms |     |     |     |     |
| Description |     | Feedback from the rear drive motor |     |     |     |     |
| Signal |     |     |     | Type |     | Description |
| REAR_AXLE_TRQ |     |     |     | Signed |     | Actual rear axle drive motor torque<br><br>Range: \[-195, 195\] |
| REAR_AXLE_TRQ_REQUEST |     |     |     | Unsigned |     | Requested rear axle torque (AI2VCU_Drive_R, REAR_AXLE_TRQ_REQUEST_Nm) |
| REAR_AXLE_TRQ_MAX |     |     |     | Unsigned |     | Maximum allowable drive torque at axle  <br>Range: \[0, 195\] |
| Message name | VCU2AI_Steer |     |     |     |     |     |
| CAN ID | 523h |     |     |     |     |     |
| DLC | 6   |     |     |     |     |     |
| Tx cycle time | 10ms |     |     |     |     |     |
| Description | Feedback from the steering controller |     |     |     |     |     |
| Signal |     |     | Type |     | Description |     |
| ANGLE |     |     | Signed |     | Actual steer angle  <br>Range: \[-21.0, 21.0\] |     |
| ANGLE_MAX |     |     | Unsigned |     | Maximum allowable steer angle. Limit is the same for steering left (+) and right (-) |     |
| ANGLE_REQUEST |     |     | Signed |     | Requested steer angle (AI2VCU_Steer, STEER_REQUEST) |     |

| Message name | VCU2AI_Brake |     |     |
| --- | --- |     |     | --- |
| CAN ID | 524h |     |     |
| DLC | 5   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Feedback from the hydraulic braking system |     |     |
| Signal |     | Type | Description |
| HYD_PRESS_F_pct |     | Unsigned | Actual normalised front axle hydraulic brake pressure<br><br>Range: \[0, 100\] |
| HYD_PRESS_F_REQ_pct |     | Unsigned | Requested normalised front axle hydraulic brake pressure (AI2VCU_Brake, HYD_PRESS_F_REQ_pct) |
| HYD_PRESS_R_pct |     | Unsigned | Actual normalised rear axle hydraulic brake pressure<br><br>Range: \[0, 100\] |
| HYD_PRESS_R_REQ_pct |     | Unsigned | Requested normalised rear axle hydraulic brake pressure (AI2VCU_Brake, HYD_PRESS_R_REQ_pct) |
| STATUS_BRK |     | Enum | Braking system status:<br><br>0 = initialising<br><br>1 = ready<br><br>2 = shutting down<br><br>3 = shutdown complete<br><br>4 = fault |
| STATUS_EBS |     | Enum | Emergency braking system status:<br><br>1 = unavailable<br><br>2 = armed<br><br>3 = triggered |

| Message name | VCU2AI_Speeds |     |     |
| --- | --- |     |     | --- |
| CAN ID | 525h |     |     |
| DLC | 8   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Wheel speed measurements |     |     |
| Signal |     | Type | Description |
| FL_WHEEL_SPEED |     | Unsigned | Front left wheel speed |
| FR_WHEEL_SPEED |     | Unsigned | Front right wheel speed |
| RL_WHEEL_SPEED |     | Unsigned | Rear left wheel speed |
| RR_WHEEL_SPEED |     | Unsigned | Rear right wheel speed |
| Message name | VCU2AI_Wheel_counts |     |     |
| CAN ID | 526h |     |     |
| DLC | 8   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | Raw pulse count measurements from the wheel speed sensors |     |     |
| Signal |     | Type | Description |
| FL_PULSE_COUNT |     | Unsigned | Pulse counts from front left wheel speed sensor  <br>Range: \[0, 65535\] |
| FR_PULSE_COUNT |     | Unsigned | Pulse counts from front right wheel speed sensor<br><br>Range: \[0, 65535\] |
| RL_PULSE_COUNT |     | Unsigned | Pulse counts from rear left wheel speed sensor<br><br>Range: \[0, 65535\] |
| RR_PULSE_COUNT |     | Unsigned | Pulse counts from rear right wheel speed sensor<br><br>Range: \[0, 65535\] |

| Message name | VCU_STATUS |     |     |
| --- | --- |     |     | --- |
| CAN ID | 120h |     |     |
| DLC | 8   |     |     |
| Tx cycle time | 10ms |     |     |
| Description | VCU status and diagnostic data |     |     |
| Signal |     | Type | Description |
| SM_SYS |     | Enum | Active VCU main state machine state:<br><br>0 = INITIAL_ACTIONS<br><br>1 = POWER_ON_SELF_TEST<br><br>2 = AUX<br><br>3 = POWERTRAIN_ENABLE<br><br>4 = DRIVE_AUTONOMOUS<br><br>5 = DRIVE_MANUAL<br><br>6 = CHARGE<br><br>7 = SHUTDOWN<br><br>8 = SHUTDOWN_OFF<br><br>9 = PUSHBAR_MODE |
| SM_AS |     | Enum | Active autonomous driving state:<br><br>1 = AS_OFF<br><br>2 = AS_READY<br><br>3 = AS_DRIVING<br><br>4 = AS_EMERGENCY_BRAKE<br><br>5 = AS_FINISHED<br><br>6 = AS_R2D |
| R1_AI2VCU_STATUS_TIMEOUT_ERROR |     | Bit | Timeout error flag for AI2VCU_Status message |
| R1_AI2VCU_DRIVE_F_TIMEOUT_ERROR |     | Bit | Timeout error flag for AI2VCU_Drive_F message |
| R1_AI2VCU_DRIVE_R_TIMEOUT_ERROR |     | Bit | Timeout error flag for AI2VCU_Drive_R message |
| R1_AI2VCU_STATUS_HANDSHAKE_ERROR |     | Bit | Timeout error flag for the AI handshake |
| R1_AI2VCU_STEER_TIMEOUT_ERROR |     | Bit | Timeout error flag for AI2VCU_Steer message |
| R1_AI2VCU_BRAKE_TIMEOUT_ERROR |     | Bit | Timeout error flag for AI2VCU_Brake message |
| SYS_ACTION_STATE |     | Enum | VCU operating mode:<br><br>0 = initialise<br><br>1 = battery charging<br><br>2 = autonomous driving<br><br>3 = manual driving<br><br>4 = shutdown |
| WARN_BRAKE_PLAUSIBILITY |     | Bit | Warning flag for the brake plausibility fault |
| WARN_KL15_UNDER_V |     | Bit | Warning flag for low 12V battery voltage |
| WARN_AI_ESTOP_REQ |     | Bit | Warning flag for an AI E-stop request |
| WARN_AI_COMMS_LOST |     | Bit | Warning flag for the AI comms lost fault |
| WARN_AUTO_BRAKING |     | Bit | Warning flag for the autonomous braking fault |
| WARN_MISSION_STATUS |     | Bit | Warning flag for the mission status fault |

## Reserved CAN Addresses

The AI Computer must not transmit any data using the following CAN IDs:

| 000h | 4E2h |
| --- | --- |
| 080h to 084h inclusive | 4FDh to 4FFh inclusive |
| 120h to 124h inclusive | 550h |
| 181h to 184h inclusive | 581h to 584h inclusive |
| 284h | 600h to 640h inclusive |
| 301h | 650h to 660h inclusive |
| 410h to 41Fh inclusive | 700h to 705h inclusive |
| 450h to 470h inclusive |     |

## Handshake and Communications Loss

A handshake must be performed between the VCU and the AI Computer when the tractive system is enabled to allow autonomous driving. The handshake bits are located in the first bytes of the AI2VCU_Status (510h) and VCU2AI_Status (520h) messages.

The VCU will alternate the value of the HANDSHAKE bit between 0 (low) and 1 (high). When the VCU sets the HANDSHAKE bit to 1 in the VCU2AI_Status message, it will wait for the AI Computer to set the corresponding HANDSHAKE bit in the AI2VCU_Status message to 1, at which point the VCU will change its HANDSHAKE value to 0 and wait for a value of 0 to be received from the AI Computer. This cycle will then continue throughout the operation of the vehicle (see figure 1) and will be used to measure the response time of the AI Computer as part of the scrutineering of all ADS-DV vehicles.

If the value of the handshake bit received from the AI Computer does not match the value of the transmitted signal within 100ms (10 consecutive messages missed), the VCU will raise an 'AI_COMMS_LOST' fault. If the vehicle is in the autonomous driving mode and in any state other than AS_OFF when this fault occurs, the vehicle emergency stop procedure will be activated.

The VCU also checks that the AI Computer is regularly sending the five 'AI2VCU' CAN messages, and will raise the 'AI_COMMS_LOST' fault if 10 consecutive messages are missed.


Figure : VCU-AI handshake and comms fault detection

# Autonomous System State Machine

Figure 2 shows the autonomous driving state machine implemented in the VCU in accordance with the Formula Student Rules. Any numbering on state transitions relates to the order in which the conditions are evaluated.


Figure 2: Autonomous driving state machine

## AS_OFF to AS_READY

The autonomous driving state machine will transition from AS_OFF to AS_READY when all the following conditions are satisfied:

- Tractive System Master Switch (TSMS) is turned on,
- Autonomous System Master Switch (ASMS) is turned on,
- An autonomous mission has been selected using the Autonomous Mission Indicator (touchscreen display),
- The Emergency Braking System (EBS) is in its ARMED state.

The selected autonomous mission will be transmitted from the VCU in the 'AMI_STATE' CAN signal ('VCU2AI_Status' message, 520h). The AI software should then update the 'MISSION_STATUS' signal ('AI2VCU_Status' message, 510h) to the SELECTED state (signal value of 1) to confirm the mission selection.

## AS_READY to AS_DRIVING

When the AS_READY state is active in the autonomous driving state machine, all powertrain components will have been initialised and be ready to act on the commands received from the AI Computer. At this point the VCU will not respond to drive or steering requests from the AI Computer to avoid any unintended motion of the vehicle. The transition from AS_READY to AS_DRIVING will be as follows:

- The VCU will remain in the AS_READY state for a minimum of 5 seconds before checking the exit conditions to move to AS_DRIVING.
- Requests from the AI Computer must meet the following criteria:
  - Front and rear drive motor torque requests must be zero,
  - Requested steering angle must be zero,
  - 'DIRECTION_REQUEST' signal ('AI2VCU_Status' message, 510h) must be set to NEUTRAL.

The intention is that the direction request is set to FORWARD when in the AS_DRIVING state. The VCU will also check that the actual steering angle of the front wheels is less than 5° to prevent any sudden steering movements when entering the AS_DRIVING state.

- Once the above conditions have been satisfied, the VCU will monitor the remote "Go" signal from the GrossFunk RES transmitter to detect a rising edge. If the switch for the "Go" signal is in the 'on' position while in AS_READY, it must be turned off and on again before the VCU will enter the AS_DRIVING state. Once the rising edge has been detected, the CAN signal 'RES_GO_SIGNAL' ('VCU2AI_Status' message, 520h) is set to TRUE and transmitted to the AI Computer. The state machine will then transition to the AS_DRIVING state.

## AS_DRIVING to AS_FINISHED

- The AI Computer must inform the VCU when the selected autonomous mission has been completed in accordance with the rules for the driverless dynamic events. The AI software is responsible for bringing the vehicle to a stop at the end of each event by applying the service brake.
- Once the vehicle has stopped, the AI Computer must set the value of the CAN signal 'MISSION_STATUS' ('AI2VCU_Status' message, 510h) to FINISHED (signal value of 3).
- When the VCU sees that the autonomous mission has been completed and the vehicle has come to rest, the autonomous driving state changes from AS_DRIVING to AS_FINISHED.
- Upon entering the AS_FINISHED state, any commands for the drive or steering motors from the AI Computer will be ignored.

## AS_FINISHED to AS_OFF

The VCU state machine will return to the AS_OFF state when the ASMS is turned off.

## AS_READY to EMERGENCY_BRAKE

The VCU state machine will enter the EMERGENCY_BRAKE state from AS_READY if the shutdown circuit (SDC) is broken, which could be caused by any of the following:

- The remote E-stop button is pressed,
- The remote E-stop receiver in the vehicle loses contact with the transmitter,
- Either of the E-stop buttons on the vehicle is pressed,
- The inertial crash sensor in the vehicle is activated,
- The VCU detects a critical system fault,
- The BMS detects a critical fault in the traction battery pack,
- The autonomous driving dongle is removed from the vehicle's Multi-Purpose Port (MPP).

## AS_READY to AS_OFF

The VCU state machine will return to the AS_OFF state if the ASMS is turned off.

## AS_DRIVING to EMERGENCY_BRAKE

The VCU will enter the EMERGENCY_BRAKE state if any of the following criteria are satisfied:

- The SDC is open (see section 3.5 for possible causes),
- The "Go" signal received from the GrossFunk RES transmitter is turned off,
- The AS master switch is turned off,
- An autonomous driving fault condition is detected (see section 4).

## AS_FINISHED to EMERGENCY_BRAKE

The emergency stop procedure will be activated if the shutdown circuit is broken while the VCU state machine is in the AS_FINISHED state.

## EMERGENCY_BRAKE to AS_OFF

Once the 15 second timer for the emergency braking procedure has elapsed, the state machine will return to AS_OFF when the ASMS is turned off. A power cycle of the vehicle will be required to return to a state where the vehicle can be driven again.

# Fault conditions

The following is a list of operating conditions that are not permissible when the ADS-DV is in its autonomous driving state (AS_DRIVING). If any of these conditions are met, the VCU will execute an emergency stop to bring the vehicle to a halt.

| Fault designation | Fault conditions |
| --- | --- |
| MISSION_STATUS_FAULT | AI sets the MISSION_STATUS (AI2VCU_Status message) to FINISHED while any of the wheel speed measurements are above 10rpm. |
| AUTONOMOUS_BRAKING_FAULT | AI sets the DIRECTION_REQUEST (AI2VCU_Status message) to NEUTRAL while any of the wheel speed measurements are above 10rpm. |
| AI_COMMS_LOST_FAULT | 10 consecutive messages are missed for any of the five AI2VCU CAN messages, or the AI handshake bit does not follow the VCU handshake within 100ms. |
| BRAKE_PLAUSIBILITY_FAULT | When operating the drive motors in torque control mode, this fault is triggered if either front or rear drive motor torque request is greater than zero, and either hydraulic braking request (front or rear axle) is greater than zero. |