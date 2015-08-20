# Agent Effectors #

Effectors allow agents to perform actions within the simulation. Agents control them by sending messages to the server, and the server changes the game state accordingly. Effectors are the logical dual of perceptors. 

Effector messages take the form of s-expressions that the client sends to the server. The following effector messages are accepted by the server:

### 1. Hinge Joint  
**(<name> <ax>)**  
This sets the joint velocities of the agent in the server. <name> is the name of the joint in the agent's model while <ax> is in radians per second.

### 2. Say  
**(say <msg>)**  
This creates a message that will be broadcast to all other agents in the server. <msg> must be no more than 20 characters long and contain characters from the ASCII subset [0x21; 0x7E] excluding [0x28; 0x29]. 

### 3. Init  
**(init (unum <playernumber>)(teamname <yourteamname>))**  
This creates an agent in the server's game world with a unique id <playernumber> and belonging to the team <yourteamname>

### 4. Beam  
**(beam <x> <y> <rot>)**  
This beams the agent to a particular location on the field. XY coordinates are specified with <x> and <y>, while <rot> specifies the orientation of the agent when beamed. The Z coordinates are fixed height unique to the body type of the agent.

### 5. Body Type
**(scene <bodytypename>)**  
This specifies the body type of the agent that will be created later with the Init effector. The <bodytypename> must match one of the supported body types. The only supported body type right now is "NaoOfficialBT".

# Monitor Effectors #
Monitor effectors allow the a third party to change certain states of the game. The currently supported commands are listed below.

### 1. Beam
**(agent (unum <num>) (team <team>) (pos <x> <y> <z>)
                                   (move <x> <y> <z> <rot>))**  

This is similar to the agent's Beam effector except that an additional <z> (height) dimension is added. The message may contain either a pos or move s-expression.  