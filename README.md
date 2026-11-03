# CooperativeRobotics_Assignment1
## Task-Priority Bimanual Manipulation

MATLAB simulation of two Franka Emika Panda arms approaching and manipulating a shared object. The arms are controlled as a coupled bimanual system using a task-priority framework.

### Control approach

- Robot kinematics and Jacobians for both arms.
- Tool-pose tasks for approaching the object.
- Explicit rigid-grasp constraint during shared-object motion.
- Joint-limit and minimum-altitude tasks.
- Action transitions between approach, object motion and stopping.
- Simulation logging and plots of the executed motion.

### Requirements

MATLAB with Robotics System Toolbox and DSP System Toolbox, the included robot model and controller files, and the course simulation interface used by the UDP helpers. The code uses `getTransform`, robot Jacobians and the `dsp.UDPSender` / `dsp.UDPReceiver` classes.

### Run

```bash
git clone https://github.com/MattiaTinfena/CooperativeRobotics_BimanualManipulation.git
```

Set the repository root as MATLAB’s current folder. Configure and start the compatible external visualiser if required by the UDP interface, then run:

```matlab
main
```

`main.m` defaults to `real_robot = false`, a 5 ms integration step and a 20 s simulation horizon. It loads `panda.mat`, initialises the two arm bases and defines the object goals.

### Source organisation

- `panda_arm.m`: arm model and kinematics.
- `bimanual_sim.m`: coupled-system simulation.
- `ActionManager.m`, `tasks/`, `icat/`: actions and task-priority control.
- `UDP_interface.m`, `simulation_scripts/`: simulator communication and timing.
- `SimulationLogger.m`: logging and plots.

The UDP visualisation interface is environment-dependent; the repository should be used with its matching course simulator configuration.
