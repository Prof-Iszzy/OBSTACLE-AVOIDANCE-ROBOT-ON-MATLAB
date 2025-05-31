
#  Obstacle Avoidance Robot – Model-Based Design using MATLAB/Simulink & SolidWorks

##  Overview

This project showcases the end-to-end development of an **autonomous obstacle avoidance robot** using the **Model-Based Design (MBD)** paradigm. Developed as part of a robotics course at Bells University of Technology, this robot system was designed, modeled, simulated, and deployed using:

-  **MATLAB/Simulink** (control system, simulation, code generation)
-  **Simscape Multibody** (physics-based 3D modeling)
-  **SolidWorks** (mechanical design, integrated via `.swj` macro)
-  **Embedded Coder** (automatic code generation)
-  GitHub (version control, documentation)

##  Project Contents

\`\`\`plaintext
ObstacleAvoidanceRobot/
│
├── README.md                     # This documentation
├── swxJRNL.swj                   # SolidWorks journal macro (mechanical model workflow)
├── MATLAB_Models/
│   ├── robot_simulation.slx      # Full Simulink system model
│   ├── control_logic.slx         # State machine for obstacle handling
│   └── sensor_model.slx          # Distance and environment sensing
│
├── Generated_Code/
│   ├── src/
│   └── include/
│
├── SimResults/
│   ├── distance_vs_time.png
│   └── motor_control_plots.png
│
└── Docs/
    ├── Final_Report.pdf
    └── system_diagram.png
\`\`\`

##  How It Works

The robot uses **ultrasonic sensors** simulated via `Transform Sensor` blocks in Simscape Multibody. It continuously monitors the environment and makes real-time decisions:

-  **Forward Movement**: If no obstacle is within 30cm.
-  **Turn Left/Right**: If an obstacle is detected within 30cm, but only one side is blocked.
-  **Stop or Reroute**: If multiple obstacles are detected close by.

The behavior is defined using **Stateflow** diagrams inside Simulink, ensuring intuitive, visual programming and real-time decision logic.

##  Running the Project

###  Requirements
- MATLAB R2021a or later
- Simulink, Simscape Multibody, Embedded Coder
- SolidWorks (for `.swj` replay)
- Arduino Uno (for deployment)

###  Steps

1. Open `robot_simulation.slx` in Simulink.
2. Load mechanical model via the journal:  
   `SolidWorks > Tools > Macro > Run > swxJRNL.swj`
3. Simulate the environment (MIL, SIL).
4. Generate code using Embedded Coder.
5. Deploy to Arduino using Simulink's hardware support.

##  Simulation & Testing Workflow

The robot system was verified through a rigorous MBD pipeline:

- **MIL** – Verifies model behavior in Simulink.
- **SIL** – Tests code on host PC.
- **PIL** – Executes code on microcontroller, with simulation loop.
- **HIL** – Runs the full system in real hardware conditions.

##  Key Features

- **SolidWorks-Driven Physical Design**: Automated via `swxJRNL.swj` for repeatable CAD integration.
- **Multibody Dynamics**: Fully simulated robot interaction with the floor and environment.
- **Automatic Code Generation**: No manual code written; Simulink is the sole source of logic.
- **Sensor Fusion**: Simulated front-mounted range finders to detect and respond to objects.
- **Real-Time Control**: Actuator response and decision-making in < 100 ms loops.

##  Team Members

- Anamalu Malachi Okechukwu (2023/12542)
- Arowosaye Emmanuel (2023/12378)
- Akinwola Israel (2023/12643)
- Arowolo Mubarak (2023/12144)
- Asenuga Morifeoluwa (2023/12137)

##  References

- MathWorks. [Model-Based Design](https://www.mathworks.com/discovery/model-based-design.html)
- Simscape Multibody. [Documentation](https://www.mathworks.com/help/physmod/sm/)
- Embedded Coder. [Auto Code Generation](https://www.mathworks.com/products/embedded-coder.html)
- SolidWorks. [User Guide](https://www.solidworks.com/)
- Siegwart et al., *Introduction to Autonomous Mobile Robots*, MIT Press

##  Notes

- All code must be generated, not hand-written.
- Use the `.swj` macro to regenerate mechanical design from scratch if needed.
- Contact project team via GitHub issues for collaboration or replication help.
