# Autonomous Delivery Robot - Requirements
## Overview
This document specifies the functional and behavioral requirements for the autonomous delivery robot system.
## Requirements

| Req. ID | Requirement |
| :--- | :--- |
| R1 | The robot shall initialize in IDLE state at the warehouse upon startup and wait for a delivery request. |
| R2 | The robot shall transition from IDLE to NAVIGATING state and start moving when a valid delivery request is received. |
| R3 | The robot shall continuously scan surroundings while moving and enter AVOIDING_OBSTACLE state if an obstacle is detected. |
| R4 | The robot shall return to NAVIGATING state toward the destination once the obstacle has been avoided. |
| R5 | The robot shall abort its journey and enter RETURNING state toward the warehouse if the battery level becomes critically low. |
| R6 | The robot shall transition to DELIVERING state upon reaching the destination coordinates. |
| R7 | The robot shall enter RETURNING state to go back to the warehouse after the package delivery is completed. |
| R8 | The robot shall enter IDLE state upon reaching the warehouse and wait for the next delivery request. |
| R9 | The robot must not transition directly from IDLE to DELIVERING state without receiving a request and navigating first. |
| R10 | The robot must not transition directly from AVOIDING_OBSTACLE state to DELIVERING state under any circumstances. |
