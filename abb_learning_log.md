# ABB IRC5 External Control (Python/RWS)  
**Date:** Jan 2026  
**Hardware:** ABB IRB 1200 (Virtual Controller)  
**Driver:** abb-motion-program-exec  

## Goal
Bypass the standard Teach Pendant programming to control the robot via an external Python script. This is to establish a workflow for "Sim-to-Real" deployment, where trajectories generated in simulation (Isaac Sim) can be executed on hardware.

## Technical Notes

### 1. Work Objects (wobj) vs. Base Frame
Initially confused why we couldn't just plan relative to the robot base.
* **Issue:** If the fixture/table moves relative to the robot, hard-coded coordinates become useless.
* **Solution:** Defined a `wobj` at `[600, 0, 550]`. This creates a local coordinate system. Moving the table only requires updating this one definition rather than re-teaching all points.

### 2. Zoning Strategies
* `fine`: Robot comes to a complete stop (velocity = 0). Essential for the start/end of weld seams.
* `z50`: Robot maintains velocity but blends the corner by 50mm. Much smoother for air moves.

### 3. Controller Configuration (PC Interface)
Python script initially failed to connect. Found that the standard virtual controller doesn't expose the RWS ports needed for external control.  
* **Fix:** Rebuilt the system in RobotStudio with option **616-1 PC Interface** enabled. This opened the socket for the Python driver.

## Debugging

### File Path Error
Ran into a `FileNotFoundError` when executing the driver from VS Code. The script was looking for the config YAML in the current working directory rather than relative to the script location.

**Fix:** Standardized path finding using `os`.

```python
# Old (Failed)
# with open('config.yml', 'r') as file:

# New (Fixed)
script_dir = os.path.dirname(os.path.abspath(__file__))
config_path = os.path.join(script_dir, '..', 'config', 'config.yml')
with open(config_path, 'r') as file:
