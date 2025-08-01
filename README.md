# COS2 Fundamentals via Turtlesim

# Node
### Concept:
A **node** is an executable program, and each node has a specific responsibility to fulfill. Multiple nodes work together to build a robotic system.
<br> 

<p align="center">
 <img src="https://github.com/user-attachments/assets/823d27f2-f5a9-4ae0-b322-b5785c38ba47" width="500"/>
</p>
<br>

### Task: Control the Turtle with the Keyboard

- **Start the first node (turtlesim_node):** This launches a node that shows a turtle in a window:

      ros2 run turtlesim turtlesim_node 
- **Start the second node (turtle_teleop_key):** This node allows the user to move the turtle with their keyboard:

      ros2 run turtlesim turtle_teleop_key
- This command is used to check the run nodes:

      ros2 node list
- This command is used to show information about the /turtlesim node:

      ros2 node info /turtlesim
### Result:
- **turtlesim_node:** draws the turtle.
- **teleop_turtle:** moves the turtle.
<br>
<p align="center">
 <img src="https://github.com/user-attachments/assets/3c6bb315-f61b-4bdc-a1de-1702ccc45798" alt="node result" width="800"/>
</p>


# Parameter 
### Concept:
**Parameters** are settings for a node, they can be changed at runtime without modifying the code. Think of them as "configuration values"(like background color, robot speed limits, etc).

### Task: Change The Background Color to Green
- Check available parameters of turtlesim:
  
      ros2 param list
- Get the value of the green color:

      ros2 param get /turtlesim background_g
- Change a parameter value for green and blue color:

      ros2 param set /turtlesim bacground_g 255
      ros2 param set /turtlesim bacground_b 0
### Result:
- Change the background to **green**.

<p align="center">
 <img src="https://github.com/user-attachments/assets/edab62ab-9e70-4882-9ebc-7ad5d4757367" alt="param result" width="800"/>
</p> 

  
# topic
### Concept:
A **Topic** is a communication channel in ROS2 where one node publishes data and another subscribes to it.  
It is used for **Topic** is a communication like sensor readings or robot positions.  

You can imagine it like: 
- One person(node) **talks(publishes)**.
- Others(nodes) can **choose to listen(subscribe)**.
- If nobody listens, the message is still spoken but ignored.
<br>  
<p align="center">
 <img src="https://github.com/user-attachments/assets/100c8738-748d-4808-930f-040ed1873545" width="500"/>
</p>
<br>

### Task: Subscribe to the Turtle's Pose Topic

- Check available topics:

      ros2 topic list
- Subscribe to the Topic /turtle1/pose:

      ros2 topic echo /turtle1/pose
- Move the turtle with the keyboard.

### Result: 
- **Publisher**: turtlesim_node (talks, sending pose updates).
- **Subscribe**: your terminal (ros2 topic echo, listens to the updates).

<p align="center">
 <img src="https://github.com/user-attachments/assets/8720c156-d268-4755-93d0-4405d4e2f45e" alt="Topic result" width="800"/>
</p> 

# service 
### Concept:
A **Service** is a way for nodes to communicate with a request → response pattern.  
- One node acts as a Server (offers the service).  
- Another node acts as a Client (asks for something).  
- The server does not keep sending data like a topic; it only responds when requested.  
<br>
<p align="center">
 <img src="https://github.com/user-attachments/assets/68d17ec2-cca8-43cf-a522-a8aec68229aa" alt="Topic result" width="500"/>
</p> 
<br>

### Task: Call the Clear Service to Erase the Turtle path
- Check available service:

      ros2 service list
- Check the type of /clear service (check for know if it needs to input data):

      ros2 service type /clear
- Call the service to clear the turtle trail:

      ros2 service call /reset std_srvs/srv/Empty

### Result:
**Server**: turtlesim_node(offers the /clear servers).<br>
**Client**: Your terminal(requested to clear).

<p align="center">
 <img src="https://github.com/user-attachments/assets/66832a24-aa48-4a5b-bcd1-cce7f2ec2934" alt="service result" width="800"/>
</p> 


## action
