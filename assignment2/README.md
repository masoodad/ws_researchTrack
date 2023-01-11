# Research Track Assignment 2

### Objective
- Create a new package, in which you will develop three nodes:
  - (a) A node that implements an action client, allowing the user to set a target (x, y) or to cancel it. The node also publishes the robot position and velocity as a custom message (x,y, vel_x, vel_z), by relying on the values published on the topic /odom. Please consider that, if you cannot implement everything in the same node, you can also develop two different nodes, one implementing the user interface and one implementing the publisher
of the custom message.
  - (b) A service node that, when called, prints the number of goals reached and cancelled;
  - (c) A node that subscribes to the robot’s position and velocity (using the custom message) and prints the distance of the robot from the target and the robot’s average speed. Use a parameter to set how fast the node publishes the information.


![base_config](robot.png)  
  
### Content
- [Package Organization](#Package-Organization)
- [Installation](#Installation)
- [Pseudocod](#Pseudocode)

## Package Organization
This package have following files structure. Name of package is 'control' and and inside the package, following is the structure of files.

- **src:** Folder to place the all the nodes of the project. There are total of four nodes in the src files.
  - *sub-files:* Nodes of the project.
- **launch:** Folder with the launch files for the robots.
- **srv:** Folder with the service files for the robots.   
- **msg:** Folder with the msg files for the robot.
- **Other files:** Folders and other files are also important such as CMakelist and package files.
    - ***include:*** Folder with the common module files, similar to the Libs.

## Installation
To install this package, just clone it inside your ROS workspace, running:

``` 
$ git clone https://github.com/masoodad/ws_researchTrack/tree/main/assignment2
```
This command will clone the `master` branch which is compatible with "ROS-notic".


## Pseudocode 
The basic modules of this package are inside the file ***common_macro.urdf.xacro*** that is at *urdf/include* folder as described above. This file work as a library and you can add it to your robot description like [this](https://github.com/pxalcantara/mobile_robot_description/blob/48819dcec6f897b7d02e8d4aa6c66d803ddf6239/urdf/mobile_robot.urdf.xacro#L7):

```xml
<xacro:include filename="$(find ${package_name})/urdf/include/common_macros.urdf.xacro" />
```
