# Automatic Water Tank Level Control System

## System Architecture

**Platform:** CODESYS Development System V3.5 SP22 Patch 4\
**Runtime:** CODESYS Control Win V3 x64\
**Main programming language:** Ladder Diagram (LD)

------------------------------------------------------------------------

## 1. Architecture Overview

The system uses a centralized PLC control architecture. The PLC receives
level conditions and operator commands, evaluates the control logic, and
determines the pump command. The HMI provides the operator with
monitoring and control functions.

The main functional sections are:

1.  Level detection
2.  PLC control
3.  Pump actuation
4.  HMI monitoring and operator control

The complete application is implemented as a software simulation in
CODESYS Control Win V3 x64.

## 2. Main Components

### 2.1 Water Storage Tank

The tank represents the storage vessel whose water level is monitored.
The HMI provides a visual representation of the simulated water level.

### 2.2 Low Level Sensor

The Low Level Sensor represents the lower operating threshold. In
Automatic Mode, detection of the low-level condition generates a request
to begin filling.

### 2.3 High Level Sensor

The High Level Sensor represents the upper operating threshold. When the
high-level condition is detected, the pump is stopped. This interlock is
intended to remain active in both Automatic and Manual modes.

### 2.4 PLC Control Program

The PLC is the central controller. The main control logic is implemented
in Ladder Diagram (LD), with supporting simulation logic where required.

The PLC control program handles: - System Start and Stop. - Automatic
and Manual operating modes. - Level-based pump control. - Manual pump
command evaluation. - High Level interlock. - Alarm-related control
functionality.

### 2.5 Water Pump

The pump is the simulated actuator that transfers water into the tank.
Its command is determined by the PLC based on the selected operating
mode and applicable protection conditions.

### 2.6 Human-Machine Interface

The HMI is developed using CODESYS Visualization. Its functions
include: - Tank water-level visualization. - Low Level and High Level
indications. - Pump status indication. - Operating mode selection. -
Start and Stop commands. - Manual pump command. - Alarm/system status
indication and reset control.

## 3. Functional Signal Overview

  -----------------------------------------------------------------------
  Functional group        Signals or functions    Purpose
  ----------------------- ----------------------- -----------------------
  Level detection         Low Level Sensor, High  Represent tank level
                          Level Sensor            conditions

  Operator commands       Start, Stop, mode       Receive operator
                          selection, Manual Pump  requests
                          command                 

  PLC processing          Mode logic, pump logic, Evaluate conditions and
                          interlock,              generate control
                          alarm-related logic     decisions

  Actuation               Pump command            Control simulated
                                                  filling

  HMI feedback            Water level, sensor     Inform the operator
                          status, pump status,    
                          mode, system/alarm      
                          status                  
  -----------------------------------------------------------------------

This is a functional overview, not a physical I/O address assignment or
wiring schedule.

## 4. Automatic Mode Sequence

1.  The operator issues the Start command.
2.  Automatic Mode is selected.
3.  The PLC monitors the Low Level and High Level conditions.
4.  When the Low Level condition is detected, the PLC requests pump
    operation.
5.  The pump continues the filling process.
6.  When the High Level condition is detected, the PLC stops the pump.
7.  The system returns to level monitoring for the next filling cycle.

## 5. Manual Mode Sequence

1.  The operator issues the Start command.
2.  Manual Mode is selected.
3.  The operator issues a Manual Pump ON command through the HMI.
4.  The PLC evaluates the command and applicable protection conditions.
5.  The pump operates when the command is permitted.
6.  The pump stops when the operator issues an OFF command or the High
    Level interlock is activated.

## 6. Start/Stop Behavior

The Start command enables system operation. The Stop command disables
the operating process and stops the pump according to the programmed
control logic.

The control logic includes restart behavior. Functional testing
confirmed that the system could stop and restart during an intermediate
water-level condition after a correction to the automatic fill request
logic.

## 7. Interlock and Alarm Functions

### 7.1 High Level Interlock

The High Level condition prevents the pump from continuing to fill the
tank after the upper level limit is reached. The interlock was
functionally tested during Manual Mode.

### 7.2 Filling Timeout Alarm

A filling timeout function is included in the control design to identify
a filling process that exceeds its configured time limit. Its behavior
was not included in the completed functional test sequence and remains
unverified.

## 9. Simulation Environment

The control application, simulated process conditions, pump behavior,
and HMI are evaluated in the CODESYS software environment using CODESYS
Control Win V3 x64.

No physical PLC, pump, or field sensors are connected to this project.

## 10. Architecture Limitations

-   The application represents one water tank.
-   Level detection is represented by two digital sensor conditions.
-   Pump actuation is simulated in software.
-   No physical I/O wiring or hardware commissioning is covered.
-   Sensor fault injection and filling timeout behavior have not been
    validated by completed functional tests.
-   The simulated interlock is a control demonstration, not a certified
    safety function.

------------------------------------------------------------------------

**Document type:** Technical System Architecture\
**Project category:** Industrial Automation and PLC Control Simulation
