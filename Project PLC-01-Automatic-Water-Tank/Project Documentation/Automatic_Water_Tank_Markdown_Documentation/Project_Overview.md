# Automatic Water Tank Level Control System

## Project Overview

**Project category:** Industrial Automation · PLC Programming · HMI
Development\
**Project type:** PLC-based water tank control simulation\
**Project level:** Intermediate\
**Development software:** CODESYS Development System V3.5 SP22 Patch 4\
**Runtime:** CODESYS Control Win V3 x64\
**Main programming language:** Ladder Diagram (LD)\
**HMI platform:** CODESYS Visualization

------------------------------------------------------------------------

## 1. Project Background

Water level control is a common application in industrial automation,
particularly in water storage and distribution systems. This project
focuses on developing a PLC-based control system that manages a
simulated water-filling process using two digital level sensors.

The Low Level Sensor and High Level Sensor provide feedback to the PLC.
Based on these signals and the selected operating mode, the PLC controls
the water pump to maintain the tank level between the defined low and
high operating limits.

The project is developed and simulated in CODESYS to demonstrate
practical PLC programming, operator control, interlocking, monitoring,
and functional testing concepts.

## 2. Project Objectives

The objectives of this project are to:

-   Develop a water tank control application using Ladder Diagram
    programming.
-   Implement automatic pump control based on low- and high-level sensor
    conditions.
-   Provide manual pump operation through an HMI.
-   Implement system Start and Stop commands.
-   Apply high-level interlock protection in both operating modes.
-   Develop an HMI for system monitoring and operator control.
-   Perform functional testing using the CODESYS Control Win runtime.

## 3. System Description

The simulated system consists of a water storage tank, a water pump, two
digital level sensors, a PLC control program, and an HMI.

In **Automatic Mode**, the PLC requests the pump to start when the Low
Level condition is detected. The pump continues filling the tank until
the High Level condition is detected, at which point the pump is
stopped.

In **Manual Mode**, the operator can issue pump ON and OFF commands
through the HMI. The High Level interlock remains active so that manual
operation cannot continue filling after the upper level condition is
reached.

The HMI provides water-level visualization, sensor indications, pump
status, operating mode selection, Start/Stop controls, manual pump
control, and alarm/system status indications.

## 4. Main Features

### 4.1 Automatic Mode

-   Automatic pump operation based on level sensor conditions.
-   Pump start request at the Low Level condition.
-   Pump shutdown at the High Level condition.
-   Repeated filling operation as the level conditions change.

### 4.2 Manual Mode

-   Operator-controlled pump operation through the HMI.
-   Manual pump ON/OFF command.
-   High Level interlock remains active.

### 4.3 Start/Stop Control

-   Start command to enable system operation.
-   Stop command to stop the operating process and pump.
-   Restart behavior included in the control logic.

### 4.4 Level and Pump Monitoring

-   Low Level and High Level sensor status indication.
-   Dynamic tank-level visualization on the HMI.
-   Pump Running/Stopped status indication.

### 4.5 Alarm and Protection Design

-   High Level interlock protection.
-   Filling timeout alarm functionality included in the control design.
-   Alarm and system status indication/reset interface on the HMI.


## 5. Development Environment

  -----------------------------------------------------------------------
  Component                           Specification
  ----------------------------------- -----------------------------------
  PLC development software            CODESYS Development System V3.5
                                      SP22 Patch 4

  Runtime                             CODESYS Control Win V3 x64

  Main programming language           Ladder Diagram (LD)

  Supporting language                 Structured Text (ST), where
                                      required

  HMI                                 CODESYS Visualization

  Test environment                    CODESYS Control Win software
                                      simulation
  -----------------------------------------------------------------------

All PLC programming, variable declaration, simulation, testing, and HMI
development were performed within the CODESYS environment.

## 6. Project Scope and Limitations

This project is an educational and portfolio-oriented software
simulation. It does not include a physical PLC, actual pump equipment,
or field-installed level sensors.

The simulation demonstrates the control logic and operator interface of
a single-tank water-level application using two digital level sensors.

The project is not a
commissioned industrial installation, and the simulated interlock is not
a substitute for a certified physical safety system.

## 7. Project Outcome

The completed project includes Automatic and Manual operating modes,
Start/Stop control, pump control, level monitoring, High Level interlock
protection, and an HMI developed using CODESYS Visualization.

The completed functional tests verified automatic filling, manual pump
operation, high-level interlock behavior, and system Stop/Restart
behavior in the software simulation environment.

The CODESYS project build completed with **zero errors and zero
warnings**.

------------------------------------------------------------------------

**Project status:** Completed software simulation; selected functions
remain unverified as noted above.
