Certain configuration variables related to gameplay can be set in robocup3d.world, the SDF file used to load the robocup3ds plugin. Variables can either take on floating point values (ex: 2.359) or boolean values (true/false). 

The format used for these variables is the following:

**<variablename>[value]</variablename>**


They are the following:  
1. **gamestate_secondsfullgame** - Duration of a complete game. Setting this also overwrites any previous values for gamestate_secondseachhalf.  
2. **gamestate_secondseachhalf** - Duration of each half of a game. Setting this also overwrites any previous values for gamestate_secondsfullgame.  
3. **gamestate_secondskickinpause** - Duration of pause when transitioning to the KickIn play mode. During pauses, gameplay rules are not enforced.  
4. **gamestate_secondskickin** - Duration of KickIn, CornerKick, GoalKick, and Freekick play modes. Once the time limit is exceeded, the play mode automatically transitions to PlayOn.  
5. **gamestate_secondsbeforekickoff** - Duration of BeforeKickOff play mode. The timer only starts when at least 1 agent is on the field.  
6. **gamestate_secondskickoff** - Duration of KickOff play mode. Transitions to PlayOn afterwards.  
7. **gamestate_dropballradius** - Radius around ball in meters that is cleared when a drop ball occurs. One or both teams are not allowed with this radius of the ball.  
8. **gamestate_usecounterforgametime** - Used for debugging purposes. When set to true, the game time is 0.02 * X, where X is the number of completed update cycles for gamestate.  
9. **gamestate_playerlimit** - The maximum number of people allowed on a team.  
10. **gamestate_beamheightoffset** - The offset added to the agent's height for the Z coordinate whenever the agent is moved around the field.  
11. **gamestate_crowdingenableradius** - Crowding control around the ball is enabled whenever two agents from opposing teams are within this many meters of the ball.  
12. **gamestate_innercrowdingradius** - When two agents of the same team are within this many meters of the ball, the farther away one is moved away.  
13. **gamestate_outercrowdingradius** - When three agents of the same team are within this many meters of the ball, the farthest away one is move away.  
14. **gamestate_immobilitytimelimit** - An agent who does not move for longer than this amount of time is moved to side of field.  
15. **gamestate_fallentimelimit** - An agent who has fallen for longer than this amount of time is moved to side of field.  
16. **percept_hfov** - The horizontal field of vision of the agent.  
17. **percept_vfov** - The vertical field of vision of the agent.  
18. **percept_restrictvision** - When set to true, the vision of the agent is restricted to the values set by percept_hfov and percept_vfov.  
19. **percept_groundtruthinfo** - When set to true, ground truth information regarding the position and orientation of the agent and ball are sent back to the client as a s-expression.  
20. **robocup3dsplugin_monitorport** - Port number used for sending monitor messages.  
21. **robocup3dsplugin_clientport** - Port number used for sending agent messages.  
22. **robocup3dsplugin_syncmode** - Turns on sync mode. When sync mode is turned on, the server waits all agents to send a syn message before going to next iteration of simulation. 
 