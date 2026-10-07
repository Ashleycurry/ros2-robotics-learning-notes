# ROS 2 机器人开发学习笔记

[中文](README.md) | [English](README-English.md)

本仓库用于整理 ROS 2 机器人开发入门学习资料，内容来自 [`docs/ROS2学习记录.pdf`](docs/ROS2学习记录.pdf)。课件从 ROS 2 的基本概念和环境搭建开始，逐步介绍节点、功能包、话题、服务、参数、Launch、TF、可视化工具、数据记录、Git 以及 URDF 机器人建模与仿真。

当前仓库只包含学习记录 PDF，不包含课件中示例代码对应的完整 ROS 2 工作空间。README 中的命令和目录示例用于复现课件中的学习过程，实际运行时需要根据本机 ROS 2 发行版、依赖版本和工作空间路径进行调整。

## 课件信息

- 资料文件：[ROS2学习记录.pdf](docs/ROS2学习记录.pdf)
- 课件页数：165 页
- 课件环境基线：Ubuntu 22.04 系列、ROS 2 Humble
- 主要语言：Python、C++
- 主要构建工具：`colcon`、`ament_python`、`ament_cmake`
- 主要工具：`ros2` CLI、`rqt`、`rviz2`、`ros2 bag`、Gazebo

## 学习路线

```text
ROS 2 基础
    -> 机器人、ROS 2 本质、ROS 1 与 ROS 2 对比
    -> 系统架构、发行版、通信机制和调试工具
    -> Linux、VS Code、Git、Python、C++ 和环境变量
            |
            v
节点与功能包
    -> Python 节点和 C++ 节点
    -> rclpy、rclcpp、日志和节点生命周期
    -> ament_python、ament_cmake 和 colcon 工作空间
    -> 面向对象、多线程和回调函数
            |
            v
ROS 2 通信
    -> Topic 发布与订阅
    -> Service 客户端与服务端
    -> 自定义消息、服务接口和参数
    -> Launch 多节点启动与配置
            |
            v
机器人工具链
    -> TF 静态与动态坐标变换
    -> rqt、RViz2 和 ros2 bag
    -> URDF、Xacro 和机器人模型可视化
    -> Gazebo 仿真基础
```

## 章节目录

### 1. 启程

- 认识机器人、传感器、执行器和决策系统之间的关系。
- 理解 ROS 2 的本质：用于快速构建机器人软件的通信库和工具集。
- 理解 ROS 2 在传感器、决策系统和执行器之间承担的数据连接作用。
- 对比 ROS 与 ROS 2 在通信稳定性、实时性、安全性和 C++ 标准方面的差异。
- 了解 ROS 2 系统架构、发行版和版本生命周期。
- 了解 ROS 2 的通信机制、调试工具、可视化工具和机器人开发生态。
- 认识 Gazebo、Navigation 2 和 MoveIt 2 等开源工具和应用框架。
- 使用 Linux、VS Code、Git、Python 和 C++ 搭建基础开发环境。
- 学习 Linux 文件操作、Python/C++ 编译执行和环境变量。
- 运行 Turtlesim，并使用 `rqt` 的 Node Graph 观察节点关系。

### 2. 节点

- 使用 Python 编写第一个 ROS 2 节点。
- 使用 C++ 编写第一个 ROS 2 节点。
- 使用 `rclpy` 和 `rclcpp` 初始化 ROS 2 客户端库、创建节点和输出日志。
- 使用 `ros2 node list`、`ros2 node info` 等命令检查节点。
- 使用 `ament_python` 功能包组织 Python 节点。
- 使用 `ament_cmake` 功能包组织 C++ 节点。
- 理解 `package.xml`、`setup.py`、`setup.cfg` 和 `CMakeLists.txt` 的职责。
- 使用 `colcon build` 构建多功能包工作空间，并加载 `install/setup.bash`。
- 通过面向对象编程组织节点和业务逻辑。
- 学习 C++ 中的 `auto`、智能指针等 ROS 2 节点开发常用特性。
- 了解 Python 和 C++ 中的多线程与回调函数示例。

### 3. 话题

- 理解 Topic 通信中的发布者、订阅者、话题名称和消息类型。
- 使用 `ros2 topic list`、`ros2 topic echo`、`ros2 topic info` 检查话题。
- 使用 `ros2 interface show` 查看消息接口定义。
- 使用 `geometry_msgs/msg/Twist` 控制 Turtlesim 前进、旋转和画圆。
- 使用 Python 编写话题发布器和订阅器。
- 订阅海龟位姿并实现基础闭环控制。
- 通过 Topic 传输小说文本，并使用 `espeak-ng` 进行文本转语音。
- 使用队列和线程协调消息接收与语音合成。
- 通过 `psutil` 获取系统状态，并通过 ROS 2 话题共享数据。
- 使用 Qt 构建简单界面并显示订阅到的 ROS 2 数据。
- 使用 `rosidl_default_generators` 创建自定义通信接口包。
- 学习 Git 基础操作，包括仓库初始化、提交和远程协作基础。

### 4. 服务

- 理解 Service 通信的请求响应模型。
- 使用 `ros2 service list -t` 查看服务名称和服务类型。
- 使用 `ros2 interface show` 查看服务接口的数据结构。
- 理解 Turtlesim `/spawn` 等服务的调用方式。
- 通过参数相关服务理解 ROS 2 参数通信。
- 使用 YAML 文件为节点加载预配置参数。
- 使用 Python 自定义服务接口，实现人脸检测服务端和客户端。
- 使用 C++ 自定义服务接口，实现巡逻海龟服务端和客户端。
- 在 Python 节点中声明参数、读取参数和处理参数更新。
- 在 C++ 节点中声明参数、读取参数、接收参数事件和修改其他节点参数。
- 使用 Python Launch 文件启动多个节点。
- 使用 Launch 文件传递参数，并学习 Launch 的进阶组织方式。

### 5. ROS 2 工具

- 使用命令行查看和调试 TF 坐标变换。
- 理解 TF 坐标树、坐标系、变换关系和时间信息。
- 使用 Python 发布机械臂底座到相机的静态 TF。
- 使用 Python 发布动态 TF 并查询 TF 关系。
- 使用 C++ 发布地图坐标系相关的静态 TF 和动态 TF。
- 使用 C++ 查询 TF 关系。
- 使用 `rqt` 和 `rqt_tf_tree` 检查节点、话题和 TF 树。
- 使用 `RViz2` 显示坐标变换和机器人状态。
- 使用 `ros2 bag record` 记录话题数据，并回放记录进行测试。
- 学习 Git 进阶操作，包括查看修改、撤销代码和分支管理。

### 6. 仿真

- 了解机器人建模与仿真的基本流程。
- 认识 Gazebo 机器人仿真平台及其应用方向。
- 创建 ROS 2 `ament_cmake` 描述功能包。
- 使用 URDF 描述机器人连杆、关节和结构关系。
- 使用 `urdf_to_graphviz` 生成机器人模型结构图。
- 在 RViz2 中加载并显示机器人模型。
- 使用 Xacro 简化和复用 URDF 文件。

## ROS 2 核心概念

| 概念 | 作用 | 课件中的学习方向 |
| --- | --- | --- |
| Node | ROS 2 中执行具体任务的运行单元 | Python/C++ 节点、日志、节点查询 |
| Topic | 面向持续数据流的异步通信 | 速度、位姿、系统状态、文本数据 |
| Service | 面向请求和响应的一次性通信 | 海龟生成、人脸检测、巡逻控制 |
| Action | 面向可反馈、可取消的长时间任务 | 作为 ROS 2 通信体系的扩展方向 |
| Parameter | 节点运行时可配置的数据 | 参数声明、读取、更新和 YAML 加载 |
| Interface | 描述 Topic、Service 等通信数据结构 | `.msg`、`.srv` 和接口生成 |
| Launch | 组织多个节点和运行参数 | `*.launch.py` 多节点启动 |
| TF | 管理机器人中的坐标系关系 | 静态 TF、动态 TF、TF 查询 |

## 环境准备

课件使用 Ubuntu 22.04 系列和 ROS 2 Humble 作为主要学习环境。建议在 Linux 环境中准备：

- Ubuntu 22.04 或与 ROS 2 发行版匹配的 Linux 系统。
- ROS 2 Humble 及其基础工具。
- Python 3、C++ 编译器和 CMake。
- `colcon`、`ament_python` 和 `ament_cmake`。
- VS Code、Git、`rqt`、`rviz2` 和 Turtlesim。
- 课件示例中使用的 `espeak-ng`、`psutil`、Qt、TF、URDF 和 Gazebo 相关依赖。

每次打开新的终端后，先加载 ROS 2 环境：

```bash
source /opt/ros/humble/setup.bash
```

如果本机安装的是其他发行版，请将 `humble` 替换为实际的发行版名称，并确认课件示例中的包名和命令仍然适用。

## 创建和构建工作空间

创建一个用于练习的 ROS 2 工作空间：

```bash
mkdir -p ~/ros2_learning_ws/src
cd ~/ros2_learning_ws
```

使用 `colcon` 构建工作空间：

```bash
colcon build
source install/setup.bash
```

构建功能包后，需要重新加载工作空间环境：

```bash
source ~/ros2_learning_ws/install/setup.bash
```

ROS 2 常见功能包构建类型：

| 构建类型 | 适用语言 | 常用文件 |
| --- | --- | --- |
| `ament_python` | Python | `package.xml`、`setup.py`、`setup.cfg`、Python 包目录 |
| `ament_cmake` | C++ | `package.xml`、`CMakeLists.txt`、`src/` |
| Interface package | 消息、服务和动作接口 | `msg/`、`srv/`、`action/`、接口生成配置 |

## 常用命令

### 节点与功能包

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

### 话题

```bash
ros2 topic list
ros2 topic echo /turtle1/pose
ros2 topic info /turtle1/cmd_vel
ros2 interface show geometry_msgs/msg/Twist
ros2 topic pub /turtle1/cmd_vel geometry_msgs/msg/Twist \
  "{linear: {x: 0.5, y: 0.0}, angular: {z: 0.0}}"
```

### 服务与参数

```bash
ros2 service list -t
ros2 service type /spawn
ros2 param list
ros2 param get /turtlesim background_r
ros2 param set /turtlesim background_r 255
```

### 工具与数据记录

```bash
rqt
rviz2
ros2 bag record /turtle1/cmd_vel
ros2 bag info <bag_directory>
```

## 推荐实践顺序

1. 先掌握 Linux 目录、文件、环境变量和终端操作。
2. 安装 ROS 2 后运行 Turtlesim、键盘控制和 `rqt`，确认基础环境可用。
3. 分别使用 Python 和 C++ 编写最小 ROS 2 节点，理解 `rclpy` 与 `rclcpp`。
4. 创建 `ament_python` 和 `ament_cmake` 功能包，掌握 `package.xml` 和构建配置。
5. 通过 Turtlesim 学习 Topic 的发布、订阅、消息类型和闭环控制。
6. 使用自定义消息和服务接口，理解接口生成、服务端和客户端。
7. 学习参数声明、参数事件、YAML 配置和 Launch 多节点启动。
8. 使用 TF、`rqt_tf_tree` 和 RViz2 检查坐标关系与机器人状态。
9. 使用 `ros2 bag` 记录和回放数据，再使用 Git 管理实验代码。
10. 最后使用 URDF、Xacro 和 Gazebo 建立机器人建模与仿真基础。

## 工程注意事项

- ROS 2 发行版、Ubuntu 版本和 Python/C++ 依赖需要保持兼容。
- 修改 `package.xml`、`setup.py` 或 `CMakeLists.txt` 后，应重新执行 `colcon build`。
- 构建成功后必须重新 `source install/setup.bash`，否则终端可能找不到新功能包或节点。
- Topic 的名称、消息类型、QoS 配置和发布订阅方向需要保持一致。
- Service 客户端运行前，应确认服务端已经启动并注册对应服务。
- 参数名称、节点名称和命名空间需要保持一致，YAML 缩进和层级也必须正确。
- 自定义 `.msg`、`.srv` 或 `.action` 接口变更后，应重新生成接口并检查所有依赖节点。
- TF 查询依赖正确的父子坐标系、时间戳和 TF 发布器。
- 多线程回调需要明确共享数据、线程退出和资源同步策略。
- 视觉检测、语音合成、Qt 和 Gazebo 等示例需要额外安装第三方依赖。
- 机器人和仿真程序运行前，应确认速度限制、控制对象和实验环境安全。

## 仓库结构

```text
ros2-robotics-learning-notes/
├── README.md
├── README-English.md
└── docs/
    └── ROS2学习记录.pdf
```

## 当前范围

当前仓库定位为 ROS 2 学习资料索引，重点覆盖：

- ROS 2 基础概念和 Linux 开发环境。
- Python/C++ 节点与功能包。
- Topic、Service、Parameter 和 Launch。
- 自定义消息与服务接口。
- TF、rqt、RViz2 和 ros2 bag。
- URDF、Xacro、Gazebo 仿真入门。

当前仓库暂未提供完整的可构建源码工作空间，也未覆盖完整导航、建图、机械臂规划、硬件驱动或生产级机器人系统。

## 关键词

`ROS 2` `Humble` `rclpy` `rclcpp` `colcon` `ament_python` `ament_cmake` `Node` `Topic` `Service` `Action` `Parameter` `Launch` `TF` `RViz2` `rqt` `ros2 bag` `URDF` `Xacro` `Gazebo` `Python` `C++`
