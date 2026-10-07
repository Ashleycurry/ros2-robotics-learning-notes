# ROS 2 Robotics Development Learning Notes

[中文](README.md) | [English](README-English.md)

This repository organizes introductory ROS 2 robotics development materials based on [`docs/ROS2学习记录.pdf`](docs/ROS2学习记录.pdf). The course starts with ROS 2 concepts and environment setup, then covers nodes, packages, topics, services, parameters, Launch files, TF, visualization tools, data recording, Git, and URDF-based robot modeling and simulation.

The repository currently contains only the study-record PDF. It does not include a complete ROS 2 workspace with the example source code from the course. The commands and directory examples in this README are intended to reproduce the learning process and may need adjustment for the installed ROS 2 distribution, dependency versions, and workspace path.

## Course Information

- Material: [ROS2学习记录.pdf](docs/ROS2学习记录.pdf)
- Length: 165 pages
- Course baseline: Ubuntu 22.04 series and ROS 2 Humble
- Main languages: Python and C++
- Main build tools: `colcon`, `ament_python`, and `ament_cmake`
- Main tools: `ros2` CLI, `rqt`, `rviz2`, `ros2 bag`, and Gazebo

## Learning Roadmap

```text
ROS 2 Fundamentals
    -> Robots, the essence of ROS 2, and ROS 1 versus ROS 2
    -> Architecture, distributions, communication, and debugging tools
    -> Linux, VS Code, Git, Python, C++, and environment variables
            |
            v
Nodes and Packages
    -> Python and C++ nodes
    -> rclpy, rclcpp, logging, and node lifecycle
    -> ament_python, ament_cmake, and colcon workspaces
    -> Object-oriented design, threads, and callbacks
            |
            v
ROS 2 Communication
    -> Topic publishers and subscribers
    -> Service clients and servers
    -> Custom messages, service interfaces, and parameters
    -> Launch-based multi-node startup and configuration
            |
            v
Robotics Toolchain
    -> Static and dynamic TF transforms
    -> rqt, RViz2, and ros2 bag
    -> URDF, Xacro, and robot model visualization
    -> Gazebo simulation fundamentals
```

## Chapter Overview

### 1. Getting Started

- Understand the relationship between robots, sensors, actuators, and decision systems.
- Understand ROS 2 as a communication library and toolset for building robot software.
- Understand how ROS 2 connects sensors, decision systems, and actuators.
- Compare ROS and ROS 2 in communication stability, real-time behavior, security, and C++ standards.
- Learn the ROS 2 architecture, distributions, and release lifecycle.
- Review ROS 2 communication mechanisms, debugging tools, visualization tools, and the robotics ecosystem.
- Introduce open-source tools and application frameworks such as Gazebo, Navigation 2, and MoveIt 2.
- Set up a basic development environment with Linux, VS Code, Git, Python, and C++.
- Practice Linux file operations, Python/C++ compilation, execution, and environment variables.
- Run Turtlesim and inspect node relationships with the `rqt` Node Graph.

### 2. Nodes

- Write a first ROS 2 node in Python.
- Write a first ROS 2 node in C++.
- Use `rclpy` and `rclcpp` to initialize the client library, create nodes, and log messages.
- Inspect nodes with commands such as `ros2 node list` and `ros2 node info`.
- Organize Python nodes in an `ament_python` package.
- Organize C++ nodes in an `ament_cmake` package.
- Understand the roles of `package.xml`, `setup.py`, `setup.cfg`, and `CMakeLists.txt`.
- Build multi-package workspaces with `colcon build` and source `install/setup.bash`.
- Use object-oriented design to organize nodes and application logic.
- Learn C++ features commonly used in ROS 2 nodes, including `auto` and smart pointers.
- Review Python and C++ examples involving threads and callbacks.

### 3. Topics

- Understand the publisher, subscriber, topic name, and message type in Topic communication.
- Inspect topics with `ros2 topic list`, `ros2 topic echo`, and `ros2 topic info`.
- Inspect message definitions with `ros2 interface show`.
- Use `geometry_msgs/msg/Twist` to move, rotate, and drive Turtlesim in a circle.
- Write Topic publishers and subscribers in Python.
- Subscribe to turtle poses and implement basic closed-loop control.
- Send novel text through a Topic and synthesize speech with `espeak-ng`.
- Use queues and threads to coordinate message reception and speech synthesis.
- Collect system status with `psutil` and share it through ROS 2 Topics.
- Build a simple Qt interface and display subscribed ROS 2 data.
- Create custom interface packages with `rosidl_default_generators`.
- Learn Git basics, including repository initialization, commits, and remote collaboration.

### 4. Services

- Understand the request-response model of Service communication.
- Inspect service names and types with `ros2 service list -t`.
- Inspect service data structures with `ros2 interface show`.
- Learn how to call services such as the Turtlesim `/spawn` service.
- Understand ROS 2 parameter communication through parameter-related services.
- Load preconfigured node parameters from YAML files.
- Define a custom service in Python and implement a face-detection server and client.
- Define a custom service in C++ and implement a patrol-turtle server and client.
- Declare, read, and update parameters in Python nodes.
- Declare and read parameters, receive parameter events, and modify other node parameters in C++.
- Use Python Launch files to start multiple nodes.
- Pass parameters through Launch files and study more advanced Launch organization.

### 5. ROS 2 Tools

- Inspect and debug TF transforms from the command line.
- Understand TF trees, frames, transforms, and timestamps.
- Publish a static TF from a robotic-arm base to a camera in Python.
- Publish dynamic TF data and query TF relationships in Python.
- Publish static and dynamic map-related TF data in C++.
- Query TF relationships in C++.
- Inspect nodes, topics, and TF trees with `rqt` and `rqt_tf_tree`.
- Display transforms and robot state in `RViz2`.
- Record Topic data with `ros2 bag record` and replay the data for testing.
- Learn advanced Git operations, including reviewing changes, undoing code, and managing branches.

### 6. Simulation

- Understand the basic workflow of robot modeling and simulation.
- Introduce Gazebo as a robot simulation platform.
- Create ROS 2 `ament_cmake` description packages.
- Describe robot links, joints, and structural relationships with URDF.
- Generate robot model graphs with `urdf_to_graphviz`.
- Load and display robot models in RViz2.
- Simplify and reuse URDF files with Xacro.

## ROS 2 Core Concepts

| Concept | Role | Learning direction in the course |
| --- | --- | --- |
| Node | A runtime unit that performs a specific task | Python/C++ nodes, logging, and node inspection |
| Topic | Asynchronous communication for continuous data streams | Velocity, pose, system status, and text data |
| Service | Request-response communication for discrete operations | Turtle spawning, face detection, and patrol control |
| Action | Feedback-capable and cancelable long-running tasks | An extension direction within the ROS 2 communication model |
| Parameter | Runtime-configurable node data | Declaration, reading, updating, and YAML loading |
| Interface | Defines the data structure for communication | `.msg`, `.srv`, and interface generation |
| Launch | Organizes multiple nodes and runtime parameters | Multi-node `*.launch.py` startup |
| TF | Manages coordinate-frame relationships | Static TF, dynamic TF, and TF lookup |

## Environment Setup

The course uses the Ubuntu 22.04 series and ROS 2 Humble as its primary learning environment. A Linux development environment should provide:

- Ubuntu 22.04 or a Linux system compatible with the selected ROS 2 distribution.
- ROS 2 Humble and its base tools.
- Python 3, a C++ compiler, and CMake.
- `colcon`, `ament_python`, and `ament_cmake`.
- VS Code, Git, `rqt`, `rviz2`, and Turtlesim.
- Additional dependencies used by the course, including `espeak-ng`, `psutil`, Qt, TF, URDF, and Gazebo packages.

Source the ROS 2 environment in every new terminal:

```bash
source /opt/ros/humble/setup.bash
```

If another distribution is installed, replace `humble` with the actual distribution name and confirm that the package names and commands used in the course are still applicable.

## Create and Build a Workspace

Create a ROS 2 workspace for practice:

```bash
mkdir -p ~/ros2_learning_ws/src
cd ~/ros2_learning_ws
```

Build the workspace with `colcon`:

```bash
colcon build
source install/setup.bash
```

After building a package, source the workspace again:

```bash
source ~/ros2_learning_ws/install/setup.bash
```

Common ROS 2 package build types:

| Build type | Typical language | Common files |
| --- | --- | --- |
| `ament_python` | Python | `package.xml`, `setup.py`, `setup.cfg`, and the Python package directory |
| `ament_cmake` | C++ | `package.xml`, `CMakeLists.txt`, and `src/` |
| Interface package | Message, service, and action interfaces | `msg/`, `srv/`, `action/`, and interface-generation configuration |

## Common Commands

### Nodes and Packages

```bash
ros2 pkg list
ros2 pkg create --help
ros2 node list
ros2 node info /node_name
```

### Turtlesim

```bash
ros2 run turtlesim turtlesim_node
ros2 run turtlesim turtle_teleop_key
```

### Topics

```bash
ros2 topic list
ros2 topic echo /turtle1/pose
ros2 topic info /turtle1/cmd_vel
ros2 interface show geometry_msgs/msg/Twist
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist \
  "{linear: {x: 0.5, y: 0.0}, angular: {z: 0.0}}"
```

### Services and Parameters

```bash
ros2 service list -t
ros2 service type /spawn
ros2 param list
ros2 param get /turtlesim background_r
ros2 param set /turtlesim background_r 255
```

### Tools and Data Recording

```bash
rqt
rviz2
ros2 bag record /turtle1/cmd_vel
ros2 bag info <bag_directory>
```

## Recommended Study Order

1. Learn Linux directories, files, environment variables, and terminal operations.
2. Install ROS 2, run Turtlesim and keyboard control, and inspect the graph with `rqt`.
3. Write minimal ROS 2 nodes in Python and C++ to understand `rclpy` and `rclcpp`.
4. Create `ament_python` and `ament_cmake` packages and learn `package.xml` and build configuration.
5. Use Turtlesim to learn Topic publishing, subscription, message types, and closed-loop control.
6. Define custom message and service interfaces and understand interface generation, servers, and clients.
7. Learn parameter declaration, parameter events, YAML configuration, and multi-node Launch files.
8. Use TF, `rqt_tf_tree`, and RViz2 to inspect coordinate relationships and robot state.
9. Record and replay data with `ros2 bag`, then use Git to manage experiments.
10. Build a foundation in robot modeling and simulation with URDF, Xacro, and Gazebo.

## Engineering Notes

- The ROS 2 distribution, Ubuntu version, and Python/C++ dependencies must be compatible.
- Run `colcon build` again after changing `package.xml`, `setup.py`, or `CMakeLists.txt`.
- Source `install/setup.bash` after a successful build, or the terminal may not find new packages and nodes.
- Topic names, message types, QoS settings, and publisher/subscriber directions must agree.
- Before running a Service client, confirm that the server is running and has registered the expected service.
- Parameter names, node names, and namespaces must match. YAML indentation and hierarchy must also be correct.
- After changing a `.msg`, `.srv`, or `.action` interface, regenerate the interface and check all dependent nodes.
- TF lookup depends on correct parent and child frame names, timestamps, and TF broadcasters.
- Multi-threaded callbacks require an explicit strategy for shared data, thread shutdown, and synchronization.
- Vision detection, speech synthesis, Qt, and Gazebo examples require additional third-party dependencies.
- Before running robot or simulation programs, verify speed limits, control targets, and the safety of the test environment.

## Repository Structure

```text
ros2-robotics-learning-notes/
├── README.md
├── README-English.md
└── docs/
    └── ROS2学习记录.pdf
```

## Current Scope

This repository is currently a learning-material index covering:

- ROS 2 fundamentals and the Linux development environment.
- Python/C++ nodes and packages.
- Topics, Services, Parameters, and Launch files.
- Custom message and service interfaces.
- TF, rqt, RViz2, and ros2 bag.
- Introductory URDF, Xacro, and Gazebo simulation.

The repository does not currently provide a complete buildable source workspace. It also does not cover complete navigation, mapping, manipulator planning, hardware drivers, or production-grade robot systems.

## Keywords

`ROS 2` `Humble` `rclpy` `rclcpp` `colcon` `ament_python` `ament_cmake` `Node` `Topic` `Service` `Action` `Parameter` `Launch` `TF` `RViz2` `rqt` `ros2 bag` `URDF` `Xacro` `Gazebo` `Python` `C++`
