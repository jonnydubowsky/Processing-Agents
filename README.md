# Processing Agents

##Structure

Processing agents are agents that perform actions in their environment. Processing agents select actions according to their current states and their goal states, where the current state is an observed state of the environment and the goal state is a desired state of the environment. Agents are "motivated" to reduce the difference between their current states and their goal states, and attempt to do so by selecting actions based on their "beliefs", or their knowledge about the effects of actions in particular states, relative to goals.

##Interactions

Processing agents form hierarchies of supervisors and subordinates (sub-agents). These labels are purely relative and are dependent on the point-of-view that an agent is referenced from. Three types of messages are passed between processing agents:

1.	Command (Supervisor → Subordinate): 
The supervisor overrides the goal of the subordinate with a new goal.
2.	Report (Subordinate → Supervisor):
The supervisor measures the progress of the subordinate, given its current state.
3.	Reward (Supervisor → Subordinate):
The supervisor reinforces the behavior of the subordinate, given its current state and goal. 

Passing a message to a sub-agent is equal to performing an action in an environment. Therefore, message passing is a learned behavior, adjusted using the reward mechanism, and selected in order to reach a goal. A supervisor’s environment is the set of its sub-agents, the actions within the environment are messages passed, and the inputs from the environment are messages received.
 
##Learning

An agent must accumulate knowledge from the standpoint of both a supervisor and a subordinate. Supervisors learn sub-agents’ abilities via reports over time, while sub-agents learn correct actions to take via rewards over time.
	
Data is held in two separate knowledge bases. Information about sub-agents and their ability to reach goals is held in a supervisor-store, while information about actions and their ability to gain rewards is held in a subordinate-store.
	
Information in the supervisor-store is obtained via supervised learning, where a subordinate’s progress is used to approximate the fitness with respect to a goal. Information in the subordinate-store is obtained via reinforcement learning, where a supervisor’s reward is used to infer the best actions to take with respect to a goal.

![Learning Process](https://github.com/CarsonScott/Processing-Agents/blob/master/img/learning-process.png)
