# Self-Regulated Learning in Multi-Agent Systems

*** 

## Hierarchical Self-Regulation
	
A system of hierarchical intelligent agents that are each responsible for managing the performance of lower-level agents using a genetic process of creating, deleting, and revising decision rules implemented by their subordinates can result in self-regulated learning where the top agents make predictions that are used to measure the performance of lower levels. This is transformed into a reward signal that causes change at lower levels and ultimately improves the predictions at the top level. 

![](https://github.com/CarsonScott/Processing-Agents/blob/master/img/Structure.png)

---

## Propagators (Level 1)

Adjust the weights and thresholds of connections based on a decision rule regarding input/output states and weight/threshold values. 

Propagator Function:

1. Calculate the outputs using inputs from level 0 (initial inputs to the system)
2. Consider the current weights and thresholds of the connections as they relate to the input states and output states
3. Increase or decrease the weights and thresholds using a decision rule

---

## Connectors (Level 2)

Create and delete propagators based on a decision rule and a fitness function that uses previous performance ratings from higher-level agents (supervisors) to infer the performance of lower-level agents (subordinates).

Connector Function:

1. Calculate the outputs using inputs from propagators, measure the performance of lower-level propagators as they compare to expected performance
2. Store memories of decision rules and their perceived fitness, update expected performance of existing propagators
3. Replace poorly performing propagators with new agents that have decision rules expected to outperform the originals

---

## Predictors (Level 3)

Create and delete connectors based on a fitness function that uses prediction errors to measure the performance of lower-level agents.

Predictor Function:

1. Calculate the predictions using current/previous inputs from connectors, measure the performance of lower-level connectors as they compare to expected performance
2. Store memories of decision rules and their perceived fitness, updated expected performance of existing connectors
3. Replace poorly performing connectors with new agents that have decision rules expected to outperform the originals


