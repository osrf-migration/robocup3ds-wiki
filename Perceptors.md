These the following s-expressions that are sent by robocup3ds back to the client at the end of every cycle:

# Non Vision Perceptors #
### 1. Game State  
**(GS (t <time>) (pm <playmode>))**  
<time> is current game time in seconds, <playmode> is name of the play mode to transition to.

### 2. Hear
**(hear <time> self/<direction> <message>)**  
This perceptor broadcasts the message received via the say effector. <time> is time when corresponding say message is received. <direction> is relative bearing in degrees where the message is received. <message> displays the contents of message. 

### 3. Gyro  
**(GYR (n <name>) (rt <x> <y> <z>))**  
This displays the 3-axis angular velocities of the agent's torso.

### 4. Hinge Joint  
**(HJ (n <name>) (ax <ax>))**  
This the current angles of all the joints of on the agent's body. <name> is name of the joint and <ax> is its angle in degrees. 

### 5. Force Resistance  
**(FRP (n rfoot/lfoot) (c <px> <py> <pz>) (f <fx> <fy> <fz>))**  
This shows the center of gravity and force exerted on the left and right foot of the agent.

### 6. Acceleration  
**(ACC (n <name>) (a <x> <y> <z>))**  
This shows the 3-axis acceleration of the agent's torso.  

### 7. Ground Truth
**(mypos <x> <y> <z>) (myorien <yaw>) (ballpos <x> <y> <z>)**  
If the ground truth configuration variable is enabled. The robot's current position, orientation in degrees, and position of the ball are displayed in the format above.  

# Vision Perceptor #
**(See (<name> (pol <distance> <angle1> <angle2>))  
(P (team <teamname>) (id <playerID>) (<bodypart> (pol <distance> <angle1> <angle2>)))  
(L (pol <distance> <angle1> <angle2>) (pol <distance> <angle1> <angle2>)))** 

The vision perceptor only displays relevant objects which are within the agent's horizontal and vertical field of view.  

### 1. Line Information  
Lines are described by two points "(L (pol ...) (pol ...))". <distance> <angle1> <angle2> are the spherical coordinates of the point in the agent's local coordinate frame. 

### 2. Landmark Information
Landmarks are described by <name> and "(pol ...)", a point s-expression.  

### 3. Other Agent Body Parts  
The name (specified by <bodypart>) and position (specified by "(pol ...)") of the following body parts of all agents are displayed:  
**Body Part/Name**  
1. Head/head  
2. Right lower arm/rlowerarm  
3. Left lower arm/llowerarm  
4. Right foot/rfoot  
5. Left foot/lfoot  