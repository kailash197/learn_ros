# ROS 2 Course

> Learn modern robotics with ROS 2—publish/subscribe, services, actions, parameters, lifecycle, navigation, perception, simulation, and real robot deployment.
> It's designed for learners from beginner to intermediate/advanced, with hands‑on projects, clear setup, and a structured syllabus.

!License: MIT  
!ROS 2

***

## Table of Contents

*   Who This Course Is For
*   Learning Outcomes
*   Prerequisites
*   System Setup
*   Course Structure
*   Module Overview
*   Hands‑On Projects
*   Assessments
*   Repository Layout
*   How to Use This Repo
*   Contribution Guide
*   Support & Community
*   License

***

## Who This Course Is For

*   **Beginners** who want a practical, guided entry into ROS 2.
*   **Developers** moving from ROS 1 to ROS 2.
*   **Researchers/Students** building prototypes in simulation and on real robots.
*   **Roboticists** targeting production systems with QoS, lifecycle, and DDS.

***

## Learning Outcomes

By the end, you will be able to:

*   Install ROS 2 and **create packages** in C++ and Python.
*   Implement **nodes, topics, services, actions**, and **parameters**.
*   Use **QoS** profiles to build robust communications.
*   Manage **node lifecycle** and launch complex systems.
*   Simulate robots in **Gazebo** and visualize with **RViz**.
*   Build **Navigation2 (Nav2)** pipelines for autonomous navigation.
*   Integrate **perception** (ROS 2 image pipeline) and sensor drivers.
*   Write **tests**, use **ros2 launch**, and containerize with **Docker**.
*   Deploy to real hardware and debug effectively.

***

## Prerequisites

*   Programming: **Python** (functions, classes) and/or **C++14/17** (classes, pointers, build basics).
*   Linux basics: shell, packages, environment variables.
*   Math: basic linear algebra + geometry helpful (TF frames).

If you’re brand new to Linux or Python/C++, start with the included **prep notebooks** under `prep/`.

***

## System Setup

*   **OS**: Ubuntu 22.04 LTS (recommended).
*   **ROS 2**: Humble or Iron (LTS/stable). Avoid Rolling for production coursework unless you’re contributing upstream.
*   **Tools**: `git`, `colcon`, `vcstool`, `rosdep`, `RViz`, `Gazebo`, `Nav2`.

### Quick Install (Ubuntu 22.04)

```bash
# Locale & sources
sudo apt update && sudo apt install -y locales curl gnupg lsb-release
sudo locale-gen en_US en_US.UTF-8
sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
export LANG=en_US.UTF-8

# Add ROS 2 apt repo
sudo apt install -y software-properties-common
sudo add-apt-repository universe
sudo apt update
sudo apt install -y curl
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key \
| sudo gpg --dearmor -o /usr/share/keyrings/ros-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] \
http://packages.ros.org/ros2/ubuntu $(lsb_release -sc) main" | \
sudo tee /etc/apt/sources.list.d/ros2.list

# Install ROS 2 (Humble Desktop)
sudo apt update
sudo apt install -y ros-humble-desktop

# Env setup
echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc
source ~/.bashrc

# Build tools
sudo apt install -y python3-colcon-common-extensions python3-vcstool
sudo apt install -y ros-humble-rviz2 ros-humble-gazebo-ros-pkgs
sudo apt install -y ros-humble-nav2-bringup
```

> If you prefer **Iron**, replace `humble` with `iron` in the commands.

***

## Course Structure

*   **Duration**: 6–8 weeks (flexible, self-paced).
*   **Format**: Short lessons → labs → mini projects → a capstone.
*   **Languages**: Python & C++ (examples for both).
*   **Evaluation**: Quizzes + project rubrics + automated tests.

***

## Module Overview

1.  **Orientation & ROS 2 Basics**
    *   ROS 2 vs ROS 1, DDS, QoS, package layout, workspaces.
    *   `colcon build`, `ros2 run`, `ros2 topic echo/list`.

2.  **Nodes, Topics, Services, Actions**
    *   Publishers/subscribers (Python/C++).
    *   Synchronous services vs long-running actions.
    *   Designing interfaces: messages, services, actions.

3.  **Parameters, Launch, Lifecycle**
    *   Dynamic params, YAML configs.
    *   `ros2 launch`, composing systems.
    *   Lifecycle nodes (configure/activate/deactivate).

4.  **TF & Sensor Integration**
    *   Coordinate frames, `tf2`, `static_transform_publisher`.
    *   Camera/LiDAR drivers and image pipeline.

5.  **Simulation & Visualization**
    *   URDF/Xacro, Gazebo Classic/Garden, RViz.
    *   Building a simple mobile robot sim and teleop.

6.  **Navigation2 (Nav2)**
    *   Map server, costmaps, planners, controllers, behavior tree (BT).
    *   Bringup, tuning, waypoint following.

7.  **Perception & Intro to Planning**
    *   Vision stack, basic detection/tracking.
    *   Action servers for pick-and-place stubs.

8.  **Quality, Testing, Packaging**
    *   `ament_lint`, `ament_cmake`, `ament_python`.
    *   Unit/integration tests, Continuous Integration (CI).

9.  **Deployment & Containers**
    *   Docker for ROS 2, multi-stage builds.
    *   Hardware deployment tips, debugging.

10. **Capstone**
    *   Choose: Navigation task or manipulation/prototyping.
    *   Final demo + report + code review.

***

## Hands‑On Projects

*   **Mini Project A:** Topic + QoS demo  
    Build pub/sub with different QoS profiles and visualize message loss under network constraints.

*   **Mini Project B:** Service & Action  
    Create a calculator service and a long-running action (e.g., file processing/robot move mock).

*   **Mini Project C:** TF + Sensors  
    Add frames and integrate a simulated camera; process images with `image_transport`.

*   **Mini Project D:** Simulation + Teleop  
    Simulate a differential drive robot in Gazebo; control with keyboard.

*   **Capstone (Pick 1):**
    1.  **Nav2 Autonomy** — map, localize, plan, and navigate waypoints in simulation.
    2.  **Manipulation Prototype** — action server controlling a “pick-and-place” mock in simulation (or real robot if available).

Each project includes a rubric and an automated test harness.

***

## Assessments

*   **Quizzes**: Short, concept checks per module.
*   **Labs**: Marked by passing unit/integration tests.
*   **Capstone**: Graded on functionality, reliability (QoS/configs), documentation, and code quality.

***

## Repository Layout

    ros2-course/
    ├─ index.md                 # You are here (course landing page)
    ├─ prep/                    # Optional Linux/Python/C++ refreshers
    ├─ docs/                    # Lesson notes & slides (Markdown or PDF)
    ├─ demos/                   # Small runnable examples
    │  ├─ cpp/
    │  └─ py/
    ├─ projects/
    │  ├─ mini_a_qos/
    │  ├─ mini_b_action_service/
    │  ├─ mini_c_tf_sensors/
    │  ├─ mini_d_sim_teleop/
    │  └─ capstone_nav2_or_manip/
    ├─ sim/                     # URDF/Xacro, Gazebo worlds, RViz configs
    ├─ tests/                   # PyTest/ament test suites
    ├─ scripts/                 # Utilities (setup, lint, CI)
    ├─ .github/
    │  ├─ workflows/ci.yaml     # CI (build, lint, tests)
    │  └─ ISSUE_TEMPLATE.md
    ├─ LICENSE
    └─ README.md                # Quickstart for the repo itself

***

## How to Use This Repo

1.  **Clone & Build**
    ```bash
    git clone https://github.com/<your-org>/ros2-course.git
    cd ros2-course
    # Set up a workspace if using local packages
    mkdir -p ws/src && cp -r demos projects sim ws/src/
    cd ws
    rosdep update
    rosdep install --from-paths src --ignore-src -y
    colcon build
    source install/setup.bash
    ```

2.  **Run a Demo**
    ```bash
    # Python pub/sub demo
    ros2 run demo_py talker
    ros2 run demo_py listener
    ```

3.  **Launch Simulation**
    ```bash
    ros2 launch sim_bringup demo_world.launch.py
    ```

4.  **Execute Nav2 Bringup**
    ```bash
    ros2 launch nav2_bringup bringup_launch.py use_sim_time:=true
    ```

5.  **Run Tests**
    ```bash
    colcon test --event-handlers console_direct+ --packages-select demo_py
    colcon test-result --verbose
    ```

***

## Contribution Guide

We welcome improvements, examples, and bug fixes!

*   **Issues**: Use GitHub Issues with clear reproduction steps.
*   **PRs**: Fork → feature branch → PR with description, screenshots/logs.
*   **Style**: Follow `ament_lint` and `clang-format` / `black`.
*   **Docs**: Keep `docs/` updated with any new features.
*   **Tests**: Add/maintain unit/integration tests under `tests/`.

***

## Support & Community

*   Q\&A via GitHub Issues.
*   Office hours / discussions (optional): open a Discussion thread for schedules.
*   For upstream ROS 2 questions, use ROS Answers (tag `ros2`).

***

## License

This course is released under the **MIT License**. See `LICENSE`.

***

### Notes & Assumptions

*   Commands are tailored for **Ubuntu 22.04 + ROS 2 Humble/Iron**.

***

### Contact
Kailash Khadka | +1 437 216 9589 | k.khadka343@gmail.com
