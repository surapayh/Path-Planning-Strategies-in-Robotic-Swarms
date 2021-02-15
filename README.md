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
Genetic algorithm gives optimal position of robots in swarm at any particular position. Path obtained is error free as compared to behavior based. Genetic
algorithm-based swarm maintenance is not smooth, as GA is run at every time step to obtain optimal distance of all robots in swarm. This genetic algorithm is taking
higher runtime than behavior based for higher number of robots but the results are error free and path formed from GA is free of collisions. All robots are getting
updated at single time step. In behavior based more precise control of swarm is observed, But weightage of individual behavior changes for different obstacle environment. In
some cases where influence of multiple vectors on velocity, is causing the robot to collide with obstacle. In some cases, robot is colliding with the obstacle because
it is following goal seeking, collision avoidance and obstacle avoidance behavior at same time step. This is due to weightage of collision avoidance among robots
and obstacle avoidance. For higher number of robots, Swarm maintenance is not good and robots start to collide due multiple robot influence for collision avoidance. Hence it needs more careful tuning. Only one robot position is updated at single time step, which is particularly disadvantageous when robot is heading towards a stationary robot in swarm.

