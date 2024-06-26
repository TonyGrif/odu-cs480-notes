---
Module: Problem Solving
Chapter: 4
Lectures:
  - "6"
  - "7"
  - "8"
---
This method of searching evaluates & modifies one or more current [[Environment Overview | states]] without maintaining and storing the paths. To do this, a single current node is selected and moves only to its neighbors to improve the state. Local search is preferable for problems where only the end goal matters.

Each node can be a solution. As a result, a local search algorithm requires a *fitness function $f(s)$* that specifies how good a state is.
# Greedy Local Search
This is a loop that moves in the direction of increasing values. At each new node, it will compare to the current largest. If it is greater, it will be the new current; else, the new node is discarded. This method only checks the neighbors of the current node and returns the local maxima. This method is also called *hill-climbing*. Without additional checks, this method can easily get stuck on local maxima, plateaus, and ridges.
## Psuedocode
```
fn HILL-CLIMBING(problem) -> state at local maxima:
    current <- MADE-NODE(problem.initial_state)
    loop do:
        neighbor <- highest-valued successor of curent node
        if neighbor <= current.value:
            return current.state
        current <- neighbor
```
## Variations
* Sideways Moves: If no uphill moves, allow moving to state with the same value.
* Stochastic Hill-Climbing: Chooses at random from among uphill moves.
* First-Choice Hill-Climbing: Stochastic climbing that generates successors until one is better than the current state.
* Random-Restart Hill-Climbing: Series of hill-climbing searches from random initial states until an adequate goal has been reached.
# Simulated Annealing
This method allows the algorithm to make "worse" moves in the hope that it could lead to a better outcome, avoiding the local maxima problem. The goal is to move the current node out of the local maxima to a location that is able to reach the global maxima. A probability is tracked that determines if the algorithm can make a "worse" move. The probability decreases as the program continues to prevent leaving a path that is more likely to reach the global maxima.
## Psuedocode
```
fn SIMULATED-ANNEALING(problem , schedule) -> solution:
    schedule: a mapping from time to temperature

    current <- MAKE-NODE(problem.initial_state)
    for t=1 to infinity do:
        T <- schedule(t)
        if T = 0: return current
        next <- randomly selected successor of current
        delta_e <- next.value - current.value
        if deleta_e == 0: current <- next
        else: current <- next with probablity of delta_e / T
```
# Genetic Algorithm
In this method, successors are generated by combining two parent states. These begin with a random set of states (*population*) where each state (*individual*) is represented as a string over a finite alphabet (commonly a binary string). The fitness function can be used to help in the probability of selecting the states for reproduction. The states continue to reproduce until an acceptable solution is found.
## Selection
This involves the process of selecting individuals to use as parents for reproduction. This could be random; however, there are other methods available given the problem.
* Roulette-Wheel Selection: More fit individuals are given a high rate of selection.
* Rank Selection: Select higher ranked individuals.
* Elitist Selection: Only fit individuals pass to next gen without any crossover or mutation.
* Tournament Selection: Select random number of individuals and push the best of them to become a parent.
* Cutoff Selection: Only individuals above a certain cutoff go forward.
## Reproduction
These are methods to create offspring for the next generation.
### Crossover
Crossover occurs between the parents in creation of a child.
Each parent has a spot(s) chosen in their string to mix together into an offspring's string. There are multiple methods to select a point(s) for crossover.
* One-Point: Uses one point for crossover.
* Multi-Point: Uses multiple points for crossover.
* Uniform: Each gene is treated separately and is selected for crossover randomly.

[[crossover.png | Demonstration]]
### Mutation
Each location in the string could be subject to mutation, a probability that the child could be modified in some capacity before being added to the next population.
* Bit Flip
* Random Resetting: Random value from valid values is assigned to random gene.
* Swap: Swap two random genes.
* Scramble: Scramble up a substring of genes.
* Inversion: Invert a substring of genes.
## Pseudocode
```
function REPRODUCE(x, y) -> individual:
    x, y: parent individuals

    n <- length(x)
    c <- random number from 1 to n
    return APPEND(substring(x, 1, c), substring(y, c+1, n))

function GENETIC-ALGORITHM(population, fit_fn) -> individual:
    repeat:
        new_population <- empty set
        for i = 1 to size(population) do:
            x <- RAND-SELECTION(population, fit_fn)
            y <- RAND-SELECTION(population, fit_fn)
            child <- REPRODUCE(x, y)
            if(small rand prob) then child <- MUTATE(child)
            new_population.insert(child)
        population <- new_population
    until some individual is fit enough or time has elapsed
    return best individual in population
```