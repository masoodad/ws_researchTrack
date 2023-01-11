# Research Track Assignment 2

### Objective
- Create a new package, in which you will develop three nodes:
  - (a) A node that implements an action client, allowing the user to set a target (x, y) or to cancel it. The node also publishes the robot position and velocity as a custom message (x,y, vel_x, vel_y), by relying on the values published on the topic /odom. Please consider that, if you cannot implement everything in the same node, you can also develop two different nodes, one implementing the user interface and one implementing the publisher
of the custom message.
  - (b) A service node that, when called, prints the number of goals reached and cancelled;
  - (c) A node that subscribes to the robot’s position and velocity (using the custom message) and prints the distance of the robot from the target and the robot’s average speed. Use a parameter to set how fast the node publishes the information.


![Screenshot from 2023-01-11 04-45-58](https://user-images.githubusercontent.com/48551115/211718216-c5359878-052d-4491-8543-d0c1db8dd183.png)

  
### Content
- [Package Organization](#Package-Organization)
- [Installation](#Installation)
- [Running](#Running)
- [Pseudocode](#Pseudocode)

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
For running this file we assume that you already have ROS workspace created and other required files. To install this package, just clone it inside your ROS workspace, running:

``` 
$ git clone https://github.com/masoodad/ws_researchTrack/tree/main/assignment2
```
Since this is a private file it may not work in some case. Hence it is suggestted that please download root respository and then copy "control" package into workspace.
```
git clone https://github.com/masoodad/ws_researchTrack.git
```
### Running

To run this package, first run userinterface file then other launch files. 

``` 
roslaunch assignment_2_2022 assignment1.launch
```
- **Start user interface**
``` 
rosrun control client_node
```
Once node is started, follow the instruction on the terminal. Please find the screenshot for more details. 

![Screenshot from 2023-01-11 03-08-03](https://user-images.githubusercontent.com/48551115/211718427-559d5ab7-240f-49f9-9977-3a9eb7bf3587.png)

- **Launch assign_solution.launch**
``` 
roslaunch control assign_solution.launch
```

![Screenshot from 2023-01-11 05-53-26](https://user-images.githubusercontent.com/48551115/211720964-47cd5881-b9a6-4d51-a27e-9f64d80a6176.png)
![Screenshot from 2023-01-11 05-53-43](https://user-images.githubusercontent.com/48551115/211720972-12f26d68-37e5-4a55-a45d-2e72735148fc.png)
![Screenshot from 2023-01-11 05-54-52](https://user-images.githubusercontent.com/48551115/211720980-436af9ef-2e76-4620-9125-69b905f72d4d.png)


## Pseudocode 
This sudo code is for only two nodes of package, "client_node" and "client_sub_node".

- **client_node**
- Action client is created which calls Action server "Planning".
- Ininite Loop
  - Press one then goal location from the user is taken
  - Press zero then Goal is cancelled
  - (For proper functionality of code please cancel goal after setting goal)
- Loop finished
- **client_sub_node**
- Publisher is created called pub with call back function "Cbkodom"
  - Inside Call back function 
  - Custom msg was defined    
- Subcriber is created called sub which subcribes "/odom"
