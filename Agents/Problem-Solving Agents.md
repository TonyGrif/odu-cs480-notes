---
Module: Problem Solving
Chapter: 3
Lectures:
  - "2"
---
A type of [[Goal Based Agent | goal-based]] [[Agent Overview | agent]] that works by finding sequence(s) of actions that lead to desirable [[Environment Overview | states]] in the form of goals.
# Problem Solving Process
* Formulate A Goal
    * Organize the agent behavior by limiting the amount of objectives and actions to be considered.
    * The goal is formed as *set of world states* based on the current situation & performance measure.
* Formulate A Problem
    * Decide which actions and world states to consider.
    * Actions cause transition between world states.
    * **Well-Defined Problem** is defined by:
        * Initial state.
        * List of actions the agent can do.
        * *Transition Model*: Description of what each actions does; also known as the *successor function*.
        * Goal Test: Determines if the state is a goal state.
        * Path Cost Function: Assigns a numeric cost to each path. This must include a step cost to calculate the cost of each action.
* Search For A Solution
    * This is the process of finding a sequence of actions that reaches the goal.
    * Implemented using [[Search Algorithms | search algorithms]].
* Execute The Solution
    * Execute actions in solution one at a time.
# Psuedocode
```
fn SIMPLE-PROBLEM-SOLVING-AGENT(percept) -> action:
    persistent seq := action sequence
    persistent state
    persistent goal
    persistent problem_formulation

    state <- UPDATE-STATE(state, percept)
    if seq is empty:
        goal <- FORMULATE-GOAL(state)
        problem <- FORMULATE-PROBLEM(state, goal)
        seq <- SEARCH(problem)
        if seq is a failure return null action
    action <- FIRST(seq)
    seq <- REST(seq)
    return action
```
# Performance Terminology
* Completeness: Algorithm guaranteed to find a solution if there is one.
* Optimality: Strategy finds the optimal solution.
* Time Complexity: Measures how long it takes to find a solution.
* Space Complexity: Measures how much memory is needed to perform the search.

Complexity is usually expressed in terms of three qualities:
* Branching Factor: Maximum number of successors of any node.
* Depth: The shallowest goal node.
* M: The maximum length of any path in the state space.