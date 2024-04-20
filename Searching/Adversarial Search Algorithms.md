---
Module: Problem Solving
Chapter: 5
Lectures:
  - "12"
  - "13"
---
Games are adversarial search problems. Adversarial search algorithms are utilized on multi-agent, competitive [[Environment Overview | environments]] to solve these problems. Games can be either deterministic or chance based. They can also give perfect or imperfect information.

Zero-sum games with two agents (Min & Max) are formally made up of:
* Initial State
* Player(s): Defines which player has the move in a state.
* Actions: Set of legal moves in state.
* Terminal Test: True when the game is over.
* Utility Function: Defines the final numerical value for a game that ends in terminal state for player.

All together, this creates a game [[Basic Data Structures#Tree | tree]] where nodes are game states & edges are moves.
# Optimal Strategy
This assumes that both players will play optimally and make no mistakes. Start by generating the full game tree using [[Search Algorithms#Depth-First Search | DFS]] and label each terminal node with its utility value. Propagate the the value up based on who's turn it is; meaning, for a Max player, the highest value will move up to the parent node, lowest for the Min player. This value is referred to the *Mini-Max value*. Continue propagating upwards until the root node is reached; from there, an optimal path can be determined.

[[minimax.png | Demonstration]]
# Alpha-Beta Pruning
*Pruning* allows the algorithm to ignore portions of the search tree that will have no bearing on the decision. This results in the same moves as [[#Optimal Strategy | Mini-Max]], but with less overhead. If at any point, a sub-tree would not be reached by an optimal agent, prune it.

[[ab-pruning.gif | Demonstration]]
## Alpha ($\alpha$)
This variable keeps track of the highest-value choice found so far at any point along the path for Max. This has an initial value of $-\infty$ and is only updated on Max's turn.
## Beta ($\beta$)
This variable keeps track of the lowest-value choice found so far at any point along the path for Min. This has an initial value of $+\infty$ and is only updated on Min's turn.