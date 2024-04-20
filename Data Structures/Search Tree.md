---
Module: Problem Solving
Chapter: 3
Lectures:
  - "3"
---
Search [[Basic Data Structures#Tree| trees]] are used to solve formulated problems. These are generated by the initial state (root node) and the successor function. The corresponding successor function is applied to expand the tree by creating child nodes. Newly generated nodes are added to the [[#Frontier | frontier]].

A *search strategy* determines the next node to be expanded based on the choices in the frontier. Searching is over when the goal state is reached.
# Node Structure
* State: The state to which the node correspond to.
* Parent: The node in the search tree that generated it.
* Action: The action that was applied to the parent to generate it.
* Path-Cost: The cost of the path from the initial node.
* Depth: The number of steps along the path from the initial state.
# Frontier
Set of search nodes that have been generated, but not expanded yet. This utilizes a [[Basic Data Structures#Queue| queue]] or a [[Basic Data Structures#Stack| stack]] with insert and remove operations to implement. How the frontier is organized is determined by the [[Search Algorithms| search strategy]].
# Explored Set
This is utilized to prevent a cyclic path by appending the states that have occurred to a set. Each expansion is checked for duplicate and is disregarded if it is one.