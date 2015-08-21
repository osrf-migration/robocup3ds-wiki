These the following s-expressions that are sent by robocup3ds back to the client at the end of every cycle:

# Non Vision Perceptors #
**(GS (t <time>) (pm <playmode>))**  
**(hear <time> self/<direction> <message>)**  
**(GYR (n <name>) (rt <x> <y> <z>))**  
**(HJ (n <name>) (ax <ax>))**  
**(FRP (n <name>) (c <px> <py> <pz>) (f <fx> <fy> <fz>))**  
**(ACC (n <name>) (a <x> <y> <z>))**  
**(mypos <x> <y> <z>) (myorien <yaw>) (ballpos <x> <y> <z>)**  

# Vision Perceptor #
(See +(<name> (pol <distance> <angle1> <angle2>))  
    +(P (team <teamname>) (id <playerID>) +(<bodypart> (pol <distance> <angle1> <angle2>)))  
    +(L (pol <distance> <angle1> <angle2>) (pol <distance> <angle1> <angle2>)))  