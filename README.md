# Processing Agents

## Structure and Function

Processing agents are agents that perform actions in their environment. Agents select actions according to their current states and their goal states, where the current state is an observed state of the environment and the goal state is a desired state of the environment. Agents are "motivated" to reduce the difference between their current states and their goal states, and attempt to do so by selecting actions based on their "beliefs", or their knowledge about the effects of actions in particular states, relative to goals.

## Organization and Communication

Organizations of agents, called societies, are hierarchical systems of agents called supervisors and subordinates. These labels, although purely relative, determine how interactions occur between agents in a society. Signals, called messages, are sent from supervisors to subordinates and vice-versa. These signals propagate through a society using specific message types. 

Command messages allow an agent to set the goal of another agent. They propagate downward from supervisor to subordinate.

Report messages allow an agent to broadcast its progress to another agent. They propagate upward from subordinate to supervisor. 

Reward messages allow an agent to reinforce the behavior of another agent. They propagate downward from supervisor to subordinate.


##Learning

An agent must accumulate knowledge from the standpoint of both a supervisor and a subordinate. Supervisors learn sub-agents’ abilities via reports over time, while sub-agents learn correct actions to take via rewards over time.
	
Data is held in two separate knowledge bases. Information about sub-agents and their ability to reach goals is held in a supervisor-store, while information about actions and their ability to gain rewards is held in a subordinate-store.
	
Information in the supervisor-store is obtained via supervised learning, where a subordinate’s progress is used to approximate the fitness with respect to a goal. Information in the subordinate-store is obtained via reinforcement learning, where a supervisor’s reward is used to infer the best actions to take with respect to a goal.

![Learning Process](https://github.com/CarsonScott/Processing-Agents/blob/master/img/Learning Process.png)
