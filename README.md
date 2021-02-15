# Path-Planning-Strategies in Robotic Swarms
The multi robot path planning is an extensively researched field. Here, we implemented two strategies that can be implemented on a multi-robot system to reach from a starting position to a goal position avoiding collisions with obstacles and surrounding robots. The major features which are required for completing such a task are Formation Control and Obstacle Avoidance. Further features can be taken into account depending upon the complexity of the environment
# Evolutionary Algorithm based strategy
This strategy is divided into Global Path Planning and Local Path Planning
## Global Path Planning
In this, the details of the [Environment](/Images/Environment.jpg) filled with obstacles is considered. Voronoi Tessellation of this environment provides us with the [network](/Images/Tessellated.jpg) of safe routes the robotic swarm can take to avoid obstacles. Then Dijkstra's algorithm was implemented to obtain the [shortest safe path](/Images/shortest_safe.jpg) to the target from initial position
## Local Path Planning
After obtaining the optimum path from the global path planner, Evolutionary Algorithm ensures that each robot in the swarm doesn't collide with obstacles and other robots in its surroundings. A proper fitness function was determined which heavily penalizes the undesirable actions and rewards the desirable actions at each and every intermeddiate way point. The best individuals in each and every generation are selected appropriately for the next generations until desirable solution is obtained. 
# Behavior-based Planning
Overall behavior of robot constitutes several subbehaviors. They are seeking goal, avoiding collision with robot nearby and avoiding obstacle. Each robot has a velocity vector which is a sum of all these characteristics depending upon their weights. Weights of these vectors can be adjusted manually depending on the environment or can be evolved using
a genetic algorithm. Here we manually adjusted the weights based on the environment.
# Comparision
Both the algorithms are good in their own way. Path planning used for GA can be improved further to get better optimal path using better algorithms other than Voronoi tessellation. Intermediate goal points needs to be increased for smooth transition in the case of GA based approach. Though GA gives better results in terms of distance travelled by each robot, it can’t be used in practical dynamic applications due to its computational delay.  Behavior based is nice tradeoff between computational time and accuracy
