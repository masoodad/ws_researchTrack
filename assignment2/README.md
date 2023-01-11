# Research Track Assignment 2

### Objective
- Create a new package, in which you will develop three nodes:
  - (a) A node that implements an action client, allowing the user to set a target (x, y) or to cancel it. The node also publishes the robot position and velocity as a custom message (x,y, vel_x, vel_z), by relying on the values published on the topic /odom. Please consider that, if you cannot implement everything in the same node, you can also develop two different nodes, one implementing the user interface and one implementing the publisher
of the custom message.
  - (b) A service node that, when called, prints the number of goals reached and cancelled;
  - (c) A node that subscribes to the robot’s position and velocity (using the custom message) and prints the distance of the robot from the target and the robot’s average speed. Use a parameter to set how fast the node publishes the information.
  
### Observation
![base_config](robot.png)


- [Package Organization](#Package-Organization)
- [Installation](#Installation)
- [Usage](#Usage)
- [Contributing](#Contributing)

## Package Organization
This project has the following folder structure.

- **config:** Folder to place the config files with the parameters of the parts of the robot and also some config files to the RVIZ.
    - *sub-folder:* The config files to a specific project should be placed in a sub-folder in order to make it possible to have different models in the same project.
- **launch:** Folder with the launch files for the robots.
- **meshes:** Folder to place the mesh files for the links of the robot. These meshes files will be used **only** as visual. The collision of the links is set as basic shapes to reduce the computational cost as the Gazebo tutorial suggests.
    - *sub-folder:* The specific mesh files of each project should be placed in the sub-folder with the name of the project.
- **rviz:** Folder with the RVIZ configuration for the robot.
- **urdf:** Folder with the URDF and xacro files.
    - ***include:*** Folder with the common module files, similar to the Libs.

## Installation
To install this package, just clone it inside your ROS workspace, running:

``` 
$ git clone https://github.com/ros-mobile-robots/mobile_robot_description.git
```
This command will clone the `master` branch which is compatible with "ROS 1". If you intend to use ROS 2 (Foxy), use this command:

``` 
$ git clone -b ros2-foxy https://github.com/ros-mobile-robots/mobile_robot_description.git
```
Check the `ros2-foxy` branch [documentation](https://github.com/ros-mobile-robots/mobile_robot_description/tree/ros2-foxy) to know some differences.

## Usage 
The basic modules of this package are inside the file ***common_macro.urdf.xacro*** that is at *urdf/include* folder as described above. This file work as a library and you can add it to your robot description like [this](https://github.com/pxalcantara/mobile_robot_description/blob/48819dcec6f897b7d02e8d4aa6c66d803ddf6239/urdf/mobile_robot.urdf.xacro#L7):

```xml
<xacro:include filename="$(find ${package_name})/urdf/include/common_macros.urdf.xacro" />
```
