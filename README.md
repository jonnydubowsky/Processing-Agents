# Processing Agents

##Structure

Processing agents are agents that perform actions in their environment. Processing agents select actions according to their current states and their goal states, where the current state is an observed state of the environment and the goal state is a desired state of the environment. Agents are "motivated" to reduce the difference between their current states and their goal states, and attempt to do so by selecting actions based on their "beliefs", or their knowledge about the effects of actions in particular states, relative to goals.

##Interactions

Processing agents form hierarchies of supervisors and subordinates (sub-agents). These labels are purely relative and are dependent on the point-of-view that an agent is referenced from. Three types of messages are passed between processing agents:

1.	Commands are from supervisors to sub-agents. The supervisor overrides the goal of the sub-agent with a new goal.
2.	Reports are from sub-agents to supervisors. The supervisor measures the progress of the sub-agent, given its current state.
3.	Rewards are from supervisors to sub-agents. The supervisor reinforces the behavior of the sub-agent, given its current state and goal. 

Passing a message to a sub-agent is equal to performing an action in an environment. Therefore, message passing is a learned behavior, adjusted using the reward mechanism, and selected in order to reach a goal. A supervisor’s environment is the set of its sub-agents, the actions within the environment are messages passed, and the inputs from the environment are messages received.
 
![Process](https://github.com/CarsonScott/Processing-Agents/blob/master/img/Process.png)
