Certain configuration variables related to gameplay can be set in `robocup3d.world`, the SDF file used to load the robocup3ds plugin. Variables can either take on floating point values (ex: 2.359) or boolean values (true/false). All variable names must be in lowercase. 

The format used for these variables is the following:

**<variablename>[value]</variablename>**


They are the following:  
1. **gamestate_secondsfullgame** - Duration of a complete game. Setting this also overwrites any previous values for gamestate_secondseachhalf [default = 600].  
2. **gamestate_secondseachhalf** - Duration of each half of a game. Setting this also overwrites any previous values for gamestate_secondsfullgame [default = 300].  
3. **gamestate_secondskickinpause** - Duration of pause when transitioning to the KickIn play mode. During pauses, gameplay rules are not enforced [default = 1].  
4. **gamestate_secondskickin** - Duration of KickIn, CornerKick, GoalKick, and Freekick play modes. Once the time limit is exceeded, the play mode automatically transitions to PlayOn [default = 15].  
5. **gamestate_secondsbeforekickoff** - Duration of BeforeKickOff play mode. The timer only starts when at least 1 agent is on the field. If the value is negative the timed transition is disabled [default = -1].  
6. **gamestate_secondskickoff** - Duration of KickOff play mode. Transitions to PlayOn afterwards [default = 15].  
7. **gamestate_dropballradius** - Radius around ball in meters that is cleared when a drop ball occurs. One or both teams are not allowed with this radius of the ball [default = 2].  
8. **gamestate_usecounterforgametime** - Used for debugging purposes. When set to true, the game time is 0.02 * X, where X is the number of completed update cycles for gamestate [default = false].  
9. **gamestate_playerlimit** - The maximum number of people allowed on a team [default = 11].  
10. **gamestate_beamheightoffset** - The offset added to the agent's height for the Z coordinate whenever the agent is moved around the field [default = 0.05].  
11. **gamestate_crowdingenableradius** - Crowding control around the ball is enabled whenever two agents from opposing teams are within this many meters of the ball [default = 0.8].  
12. **gamestate_innercrowdingradius** - When two agents of the same team are within this many meters of the ball, the farther away one is moved away [default = 0.4].  
13. **gamestate_outercrowdingradius** - When three agents of the same team are within this many meters of the ball, the farthest away one is move away [default = 1.0].  
14. **gamestate_immobilitytimelimit** - An agent who does not move for longer than this amount of time is moved to side of field [default = 15].  
15. **gamestate_fallentimelimit** - An agent who has fallen for longer than this amount of time is moved to side of field [default = 30].  
16. **percept_hfov** - The horizontal field of vision of the agent [default = 120].  
17. **percept_vfov** - The vertical field of vision of the agent [default = 120].  
18. **percept_restrictvision** - When set to true, the vision of the agent is restricted to the values set by percept_hfov and percept_vfov [default = true].  
19. **percept_groundtruthinfo** - When set to true, ground truth information regarding the position and orientation of the agent and ball are sent back to the client as a s-expression [default = false].  
20. **robocup3dsplugin_monitorport** - Port number used for sending monitor messages [default = 3200].  
21. **robocup3dsplugin_clientport** - Port number used for sending agent messages [default = 3100].  
22. **robocup3dsplugin_syncmode** - Turns on sync mode. When sync mode is turned on, the server waits all agents to send a syn message before going to next iteration of simulation [default = false]. 
 
Additionally, players can configure the joint PID parameters of each of the supported body types for agents. The configuration variable name must have the format pid_**[bodytypename]**_**[jointname]**, where **[bodytypename]** is the name of the body type and **[jointname]** is name of the model of the joint. Three floating point values separated by spaces must be specified. They are:  
  1. P gain  
  2. I gain  
  3. D gain  

This is partial view of a modified `robocup3d.world` with some custom parameters:


```
#!c++

<?xml version="1.0" ?>
<sdf version="1.5">
  <world name="default">

    <physics type="ode">
      <max_step_size>0.001</max_step_size>
    </physics>

    <! ... -->

    <!-- RoboCup 3D simulator ball -->
    <include>
      <pose>0 0 0 0 0 0</pose>
      <uri>model://robocup_3Dsim_ball</uri>
    </include>

    <!-- Load the RoboCup 3D plugin -->
    <plugin name="robocup3dplugin" filename="librobocup3dsPlugin.so">
      <robocup3dsplugin_syncmode>false</robocup3dsplugin_syncmode>
      <gamestate_immobilitytimelimit>7</gamestate_immobilitytimelimit>
      <gamestate_fallentimelimit>5</gamestate_fallentimelimit>
      <gamestate_secondskickoff>5</gamestate_secondskickoff>
      <gamestate_secondseachhalf>20</gamestate_secondseachhalf>
      <percept_groundtruthinfo>true</percept_groundtruthinfo>
    </plugin>
  </world>
</sdf>
```