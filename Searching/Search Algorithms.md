---
Module: Problem Solving
Chapter: 3
Lectures:
  - "3"
  - "4"
  - "5"
---
These strategies utilize a [[Search Tree | search tree]] to formulate solutions for [[Problem-Solving Agents | problem solving agents]].
# Uninformed Search
One search strategy that requires no information about the path cost from the current state to the goal. The state is searched blindly by generating successors and delineating between goals and not goals.
## Breadth-First Search
This method expands the *shallowest* node in the current frontier of the search tree. The [[Search Tree#Frontier | frontier]] must utilize a [[Basic Data Structures#Queue| queue]] data structure.

[[bfs.gif | Demonstration]]
### Evaluation
* Complete, but not always optimal. It is only optimal if the cost is a non-decreasing function only of depth.
* Time Complexity: $O(b^d)$ where $b^d$ is the number of nodes generated. $b$ is the branching factor and $d$ is the depth of the shallowest goal node.
* Space Complexity: $O(b^d)$ where $b^d$ is the number of nodes generated. $b$ is the branching factor and $d$ is the depth of the shallowest goal node.
* Space is usually the bigger problem over time.
## Uniform Cost Search
This is similar to [[#Breadth-First Search | BFS]]; however, it will expand the node with the lowest path cost first. This method must use a [[Basic Data Structures#Priority Queue| priority queue]] sorted by path cost. This must also apply the goal-test when a node is selected for expansion, not when generated.
## Depth-First Search
This method expands the *deepest* node in the current frontier of the of the search tree. The [[Search Tree#Frontier | frontier]] must utilize a [[Basic Data Structures#Stack| stack]] data structure.

[[dfs.gif | Demonstration]]
### Evaluation
* Complete, but non-optimal for general cost functions. It is optimal if the cost is non-decreasing function of only depth.
* Time Complexity: $O(b^d)$.
* Space Complexity: $O(bd)$.
### Depth-Limited Search
Counters some of the issues of [[#Depth-First Search | DFS]] by limiting the search depth to a predetermined depth. This will require some predetermined information about the problem to determine a good depth.
### Iterative Deepening Search
This variation of [[#Depth-Limited Search | DLS]] will gradually increment the depth limit until a goal is found.
## Bidirectional Search
This method runs two simultaneous searches, one starting from the initial state and the other from the goal state. It will continue to expand both ways until their [[Search Tree#Frontier | frontiers]] intersect.
# Informed Search
Also known as *Heuristic Search*, this is a search strategy that must know if one non-goal state is more promising than another. This strategy can find solutions much more efficiently than [[#Uninformed Search | uniformed search]] by using an evaluation function $f(n)$ for each node. The [[Search Tree#Frontier | frontier]] will be implemented with a [[Basic Data Structures#Priority Queue| priority queue]] and the goal test must occur when the node is expanded.

The *Heuristic Function* $h(n)$ is an estimated cost from a node to the goal. To be an admissible heuristic, it must never overestimate the cost to reach the goal.
## Greedy Best-First Search
This tries to expand the node that is the closest to the goal; as a result, the nodes are evaluated just off of their heuristic function value.
### Evaluation
* Not complete as it can get stuck in loops and not optimal.
* Time Complexity: $O(b^m)$.
* Space Complexity: $O(b^m)$.
## A* Search
This method tries to combine [[#Uniform Cost Search| uniform cost search]] and [[#Greedy Best-First Search | greedy best-first search]] by using an estimated cost of the cheapest solution through $f(n) = g(n) + h(n)$.

$g(n)$ is gives the path cost from the start node to node $n$ and is used by uniform cost search. $h(n)$ is the heuristic function to estimate the cheapest path from node $n$ to the goal and is used by greedy best-first search.
### Evaluation
* Complete and optimal.
* Time Complexity: $O(b^d)$ at worst.
* Space Complexity: $O(b^d)$.