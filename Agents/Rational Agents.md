---
Module: Artificial Intelligence
Chapter: 2
Lectures:
  - "1"
---
A rational [[Agent Overview | agent]] is the one that does the "right thing" based on its perception and the actions it can perform. It is not omniscient as percepts may not supply all relevant information, nor is clairvoyant as the action outcomes may not be as expected. **Rationality** seeks to maximize the expected performance, while **perfection** seeks to maximize actual performance. Rationality requires exploration, learning, and autonomy.

The **right thing** is to select the action that will cause the agent to be most successful. This is measured through a **performance measure** which must utilize an objective measure for success of agent's behavior by evaluating any given sequence of [[Environment Overview| environment]] states.
# Formal Definition
For each possible percept sequence, a rational agent should select an action that is expected to maximize its performance measure, given the evidence provided by the percept sequence and whatever build-in knowledge the agent has.
# Agent Types
Agents can utilize different ways to map percepts to actions with differing levels of complexities.
* [[Simple Reflex Agents]]
    * [[Model Based Reflex Agent]]
* [[Goal Based Agent]]
* Utility-Based Agents
    * These agents require a *utility function*:
        * Internalization of the performance measure that maps state to a real number called the *degree of happiness*.
        * The agent chooses the action that maximizes expected utility.
    * Pros: Effective for conflicting goals or when requiring trade-offs between goals. This also permits rational actions for more complex tasks.
    * Cons: Difficult to have perfect utility function because of computational complexity.
* Learning Agents
    * Agents can learn by experience through:
        * Performance Element: Takes in percepts to decide on actions. This can be one of the [[#Agent Types | previously described agents]].
        * Learning Element: Evaluates correctness of performance element with feedback from the critic.
        * Critic: Provides feedback about performance of the agent. This can be external or part of [[Environment Overview| environment]].
        * Problem Generator: Suggests actions to the agent. This is required for novel solutions  that require creativity.
    * Pros: Improves performance over time in dynamic environment.
    * Cons: Requires sufficient learning and is complex to design and implement.