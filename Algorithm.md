# Architecture for Intelligent Agent Systems
 
### Overview
	If x is an input and c is a cost, ɸ(x,c) is a function that returns an output. The input is a set of values received from a sensory system, the cost is a value received from a utility system, and the output is a set of values passed to a motor system.

### Algorithm
Five processing steps are required to produce an output from a given input and cost. The steps are: receive (perception), update (learning), find (reasoning), set (prediction), and send (action). Each step contains two functions, which are listed below:

Perception
- Receive input from the sensory system
- Receive utility from the performance system

Learning
- Update memory with respect to predicted and actual input
- Update memory with respect to predicted and actual cost

Reasoning
- Find expected input and cost of each action
- Find lowest cost and select associated action

Prediction
- Set input prediction of selected action
- Set cost prediction of selected action

Action
- Send output to motor system
- Send output to previous action
