# Surgical Digital Twin - Engineering Log
**Production Code:** [isaacsim-surgical-teleop](https://github.com/abouzk/isaacsim-surgical-teleop)

### 2026-03-07: Phase 0 & 1 Kinematic Validation via ROS 2 Turtlesim
* **Objective:** Validate the baseline ROS 2 teleoperation architecture (keyboard and XInput gamepad) to ensure robust topic publishing before bridging the network to the computationally heavy NVIDIA Isaac Sim digital twin.
* **Architecture Decisions:**
  * Utilized `turtlesim` as the intermediate Verification and Validation (V&V) node.
    * *Reasoning:* Decouples ROS 2 input and message debugging from Omniverse rendering overhead. This proves the hardware-to-software bridge and `/cmd_vel` publisher logic are 100% sound before introducing the complexity of Isaac Sim's Omnigraph and inverse kinematic solvers.
  * Standardized Phase 1 input on XInput (Standard Gamepad) via the ROS 2 `joy` and `teleop_twist_joy` packages. 
    * *Reasoning:* Provides a scalable, easily accessible hardware abstraction layer. This allows Mercer XLab students to understand the difference between discrete (keyboard) and continuous (joystick) control signals before advancing to complex haptic hardware like the Novint Falcon.
* **Blockers/Constraints:** Isaac Sim requires significant computational overhead and precise Omnigraph ROS 2 Bridge configuration to subscribe to external topics. Temporarily isolating the simulation environment allowed for rapid, zero-latency validation of the local network and hardware controllers. 
* **Next Action Items:**
  * Configure the Isaac Sim Omnigraph to subscribe to the validated `/cmd_vel` topic and successfully drive a 3D digital twin (Finalizing Phases 0 & 1).
  * Create and post Mercer Documentation for Phases 0 & 1
  * Begin Phase 2: Compile legacy `libnifalcon` drivers to replace the gamepad with the Novint Falcon for baseline 3-DOF spatial control.
