# Research Track Assignment 2

### Objective
- Create a new package, in which you will develop three nodes:
  - (a) A node that implements an action client, allowing the user to set a target (x, y) or to cancel it. The node also publishes the robot position and velocity as a custom message (x,y, vel_x, vel_z), by relying on the values published on the topic /odom. Please consider that, if you cannot implement everything in the same node, you can also develop two different nodes, one implementing the user interface and one implementing the publisher
of the custom message.
  - (b) A service node that, when called, prints the number of goals reached and cancelled;
  - (c) A node that subscribes to the robot’s position and velocity (using the custom message) and prints the distance of the robot from the target and the robot’s average speed. Use a parameter to set how fast the node publishes the information.


![Screenshot from 2023-01-11 04-45-58](https://user-images.githubusercontent.com/48551115/211718216-c5359878-052d-4491-8543-d0c1db8dd183.png)

  
### Content
- [Package Organization](#Package-Organization)
- [Installation](#Installation)
- [Running](#Running)
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

### Running


![Screenshot from 2023-01-11 03-08-03](https://user-images.githubusercontent.com/48551115/211718427-559d5ab7-240f-49f9-9977-3a9eb7bf3587.png)
![Screenshot from 2023-01-11 03-08-32](https://user-images.githubusercontent.com/48551115/211718431-d348bcba-0f46-4fb6-8b5f-68aba49db64a.png)
![Screenshot from 2023-01-11 03-09-00](https://user-images.githubusercontent.com/48551115/211718433-85bae67a-a070-4f45-aa16-c21630244f42.png)
![Screenshot from 2023-01-11 03-09-12](https://user-images.githubusercontent.com/48551115/211718441-7ae05197-c406-4e97-9b46-73dc679d15fb.png)
![Screenshot from 2023-01-11 03-09-34](https://user-images.githubusercontent.com/48551115/211718444-bc972869-7eb2-42af-a092-98b21a8724ed.png)
![Screenshot from 2023-01-11 03-37-33](https://user-images.githubusercontent.com/48551115/211718451-591a2c41-1318-4dd8-877e-1c8043f63b4b.png)


## Pseudocode 
The basic modules of this package are inside the file ***common_macro.urdf.xacro*** that is at *urdf/include* folder as described above. This file work as a library and you can add it to your robot description like [this](https://github.com/pxalcantara/mobile_robot_description/blob/48819dcec6f897b7d02e8d4aa6c66d803ddf6239/urdf/mobile_robot.urdf.xacro#L7):

```xml
<xacro:include filename="$(find ${package_name})/urdf/include/common_macros.urdf.xacro" />
```
