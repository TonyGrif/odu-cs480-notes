---
Module: Artificial Intelligence
Chapter: 2
Lectures:
  - "1"
---
Environments determine the interaction between "outside world" and the [[Agent Overview | agent]]. The [[#PEAS Description | task environment]] defines the "problems" to which [[ Rational Agents | rational agents]] are the "solutions."
# PEAS Description
PEAS specifies the *task environment* of a problem.
* Performance Measures: Evaluate how well an agent solves a task. This is not always binary as some goals may conflict and require trade-offs.
* Environment: The surroundings beyond control of agent.
* Actuators: The actions agent can perform.
* Sensors: These provide information on current state of environment to the agent.
# Properties of Task Environments
* Full Observable vs. Partially Observable
    * Can sensors capture all relevant information?
    * An environment can also be unobservable.
* Deterministic vs. Stochastic
    * Are changes predictable?
* Episodic vs. Sequential
    * Do actions build on each other? Will next percepts/actions be determined by the previous?
* Static vs. Dynamic
    * Are there changes while agent is thinking?
* Discrete vs. Continuous
    * Are there limited number of distinct percpets/actions?
* Single vs. Multiple Agents
    * If there are multiple agents, are they collaborating or competitive?