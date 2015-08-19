Effectors allow agents to perform actions within the simulation.  Agents control them by sending messages to the server, and the server changes the game state accordingly. Effectors are the logical dual of perceptors. 

Effector messages take the form of s-expressions that the client sends to the server. The following effector messages are accepted by the server:

1. Hinge Joint  
(<name> <ax>)

2. Say  
(<say> <msg>)