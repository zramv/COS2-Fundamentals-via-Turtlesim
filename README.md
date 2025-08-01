# COS2 Fundamentals via Turtlesim

## Node
A node is an executable program, and each node has a specific responsibility to fulfill. Multiple nodes work together to build a robotic system.
<p align="center">
 <img src="https://github.com/user-attachments/assets/823d27f2-f5a9-4ae0-b322-b5785c38ba47" width="500"/>
</p>

### Task with turtlesim

- **Start the first node (turtlesim_node):** This launches a node that shows a turtle in a window

      ros2 run turtlesim turtlesim_node 

- **Start the second node (turtle_teleop_key):** This node allows the user to move the turtle with their keyboard.

      ros2 run turtlesim turtle_teleop_key
  
- This command is used to check the run nodes.

      ros2 node list
  
- This command is used to show information about the /turtlesim node.

      ros2 node info

### Result 
- **turtlesim_node:** draws the turtle.
- **teleop_turtle:** moves the turtle.
<br>
<p align="center">
 <img src="https://github.com/user-attachments/assets/3c6bb315-f61b-4bdc-a1de-1702ccc45798" alt="node result" width="800"/>
</p>


## Parameter 

## topic

## service 

## action
