# Agents and Societies

## Structure and Function

Processing agents are agents that perform actions in their environment. Agents select actions according to their current states and their goal states, where the current state is an observed state of the environment and the goal state is a desired state of the environment. Agents are "motivated" to reduce the difference between their current states and their goal states, and attempt to do so by selecting actions based on their "beliefs", or their knowledge about the effects of actions in particular states, relative to goals.

## Organization and Communication

Organizations of agents, called societies, are hierarchical systems of agents called supervisors and subordinates. These labels, although purely relative, determine how interactions occur between agents in a society. Signals, called messages, are sent from supervisors to subordinates and vice-versa. These signals propagate through a society using specific message types. 

Command messages allow an agent to set the goal of another agent. They propagate downward from supervisor to subordinate.

Report messages allow an agent to broadcast its progress to another agent. They propagate upward from subordinate to supervisor. 

Reward messages allow an agent to reinforce the behavior of another agent. They propagate downward from supervisor to subordinate.


## Knowledge and Learning

An agent must accumulate knowledge from the standpoint of both a supervisor and a subordinate. Supervisors learn sub-agents’ abilities via reports over time, while sub-agents learn correct actions to take via rewards over time.
	
Data is held in two separate knowledge bases. Information about sub-agents and their ability to reach goals is held in a supervisor-store, while information about actions and their ability to gain rewards is held in a subordinate-store.
	
Information in the supervisor-store is obtained via supervised learning, where a subordinate’s progress is used to approximate the fitness with respect to a goal. Information in the subordinate-store is obtained via reinforcement learning, where a supervisor’s reward is used to infer the best actions to take with respect to a goal.

![Learning Process](https://github.com/CarsonScott/Processing-Agents/blob/master/img/Learning Process.png)

## Goal Representation and Reinforcement
A goal value is a label for some unknown state of the environment. The correct target state of each goal must somehow be realized. The agent stores a predicted target state for each goal and performs iterative changes in order to fit the real state. Target updates are based on current and previous states, along with the associated rewards. At each time step, the agent calculates the state delta and multiplies each value by the reward and learning rate, which is then added to the target state.

T  = T  + ∂r(S - P)

- T is an element of the target state
- S is an element of the current state
- P is an element of the previous state
- r is the reward
- ∂ is the learning rate

***

# Business Analogy and Employees

## Society as a Business
A society is an entity with a hierarchical structure that executes specific tasks in order to reach a goal. Agents perform individual actions that collectively achieve something bigger than themselves. The functional and structural properties of a society resemble a business in which supervisors distribute tasks, measure progress, and make adjustments to optimize the performance of their subordinates.

## Subordinate as an Employee
A supervisor has the ability to terminate a subordinate agent. In the event that a sub-agent fails to perform adequately on a consistent basis, or causes a decline in its coworker’s performance, it may be reset. In other words, the sub-agent’s memory is cleared to get rid of all malicious behavior, thus replacing the bad agent with a “new” employee.

A terminated agent must learn everything from the ground up. The new agent cannot be expected to perform as well as the others until it has received the proper amount of training, therefore a supervisor must treat a new agent differently than the previous agent.

Following a termination, the supervisor clears all data regarding the previous agent's abilities by wiping a portion of its own memory. All information regarding the new agent is held in the storage space that becomes available after the old agent is fired.




