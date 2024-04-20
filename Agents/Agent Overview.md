---
Module: Artificial Intelligence
Chapter: 2
Lectures:
  - "1"
---
An **agent** is an entity that interacts with its [[Environment Overview| environment]]. Agents perceive through **sensors** and does actions through **effectors** or **actuators**.
# Terminology
* Percept: An agent's perceptual inputs.
* Percept Sequence: The complete history of everything the agent has perceived.
* Agent Function: The mapping of any given percept sequence to action. The input for this is the entire percept history.
* Agent Program: Program running on physical architecture to produce the agent function, *concrete implementation*. The input for this is the current percept.
* Agent: The architecture combined with the agent program.