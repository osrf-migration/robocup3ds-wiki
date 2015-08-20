Certain configuration variables related to gameplay can be set in robocup3d.world, the SDF file used to load the robocup3ds plugin. 

They are the following:  
1. **gamestate_secondsfullgame** - Duration of a complete game. Setting this also overwrites any previous values for gamestate_secondseachhalf.  
2. **gamestate_secondseachhalf** - Duration of each half of a game. Setting this also overwrites any previous values for gamestate_secondsfullgame.  
3. **gamestate_secondskickinpause** - Duration of pause when transitioning to the KickIn play mode. During pauses, gameplay rules are not enforced.  
4. **gamestate_secondskickin** - Duration of KickIn playmode. Once the time limit is exceeded, the play mode automatically transitions to PlayOn.