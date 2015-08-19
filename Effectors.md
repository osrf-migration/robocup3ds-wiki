Effectors allow agents to perform actions within the simulation. Agents control them by sending messages to the server, and the server changes the game state accordingly. Effectors are the logical dual of perceptors. 

Effector messages take the form of s-expressions that the client sends to the server. The following effector messages are accepted by the server:

1. Hinge Joint  
(<name> <ax>)
This sets the joint velocities of the agent in the server. <name> is the name of the joint in the agent's model while <ax> is in radians per second.

2. Say  
(say <msg>)  
This creates a message that will be broadcast to the server. <msg> must be no more than 20 characters long and contain characters from the ASCII subset [0x21; 0x7E] excluding [0x28; 0x29]. 