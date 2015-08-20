<img src="https://bitbucket.org/repo/A9ekGz/images/1349408363-RCSSServer3D-Play-Modes.png" width="48">

The play modes supported by the robocup3ds plugin are described below:

1. **BeforeKickOff**  
Before the match  
The ball is at (0,0), the midfield and may not be moved. Players may use their beam effectors. Game time does not progress. This state is only left when a user instructs the simulator to start.

2. **KickOffLeft**  
Kick off for the left team  
The left team have a period in which to make their first kick. During this time the right team are lot allowed to cross the center line, or inside the center circle. The left team may not cross the center line, unless they are within the goal circle.

3. **KickOffRight**  
Kick off for the right team  
The right team have a period in which to make their first kick. During this time the left team are lot allowed to cross the center line, or inside the center circle. The right team may not cross the center line, unless they are within the goal circle.

4. **PlayOn**  
Regular gameplay  
	
5. **KickInLeft**  
Kick in left team  
The right team have kicked the ball off the side of the field. The ball is positioned on the sideline at the position it left the field. The right team are not allowed within a fixed radius of the ball, and the left team have a period of time in which to kick the ball back into play.

6. **KickInRight**  
Kick in right team  
The left team have kicked the ball off the side of the field. The ball is positioned on the sideline at the position it left the field. The left team are not allowed within a fixed radius of the ball, and the right team have a period of time in which to kick the ball back into play.

7. **CornerKickLeft**  
Corner kick left team  

8. **CornerKickRight**  
Corner kick right team	

9. **GoalKickLeft**  
Goal kick for left team	

10. **GoalKickRight**  
Goal kick for right team	

11. **GameOver**  
After the match  
Play has finished. Agents may still move about, but no actions will have an effect upon the result of the match.  

12. **GoalLeft**  
Goal scored by the left team  
This state exists for a few moments, before transitioning to KickOffLeft.

13. **GoalRight**  
Goal scored by the right team  
This state exists for a few moments, before transitioning to KickOffRight.

14. **FreeKickLeft**  
Free kick for left team  
The right team are not allowed within a fixed radius of the ball, and the left team have free access. PlayOn commences when the left team touches the ball, or if they fail to do so after a fixed period.

15. **FreeKickRight**  
Free kick for right team  
The left team are not allowed within a fixed radius of the ball, and the right team have free access. PlayOn commences when the right team touches the ball, or if they fail to do so after a fixed period.