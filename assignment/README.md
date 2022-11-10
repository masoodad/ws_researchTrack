###Assignment 1 python script

#Objective: Main code is after the definition of the functions. The code should make the robot:
	- 1) find and grab the silver marker (token)
	- 2) move the marker close to golden marker (token) and release it
	- 3) start again from 1

#Theory: The method see() of the class Robot returns an object whose attribute info.marker_type may be MARKER_TOKEN_GOLD or MARKER_TOKEN_SILVER, depending of the type of marker (golden or silver). 
Modify the code of the exercise2 to make the robot:

1- retrieve the distance and the angle of the silver marker  which was previously not grabbed. If no silver marker is detected, the robot should rotate in order to find a marker.
2- drive the robot towards the marker and grab it
3- retrieve the distance and the angle of the closest golden marker which was previously not grabbed. If no golden marker is detected, the robot should rotate in order to find a marker.
4- find a golden marker, carry silver marker close to golden marker and release(use the method release() of the class Robot in order to release the marker)
5- start again from 1

#Run:	When done, copy this python file in folder of simulator and run with:
	$ python run.py assignment.py



[flow.drawio.pdf](https://github.com/masoodad/ws_researchTrack/files/9984206/flow.drawio.pdf)

