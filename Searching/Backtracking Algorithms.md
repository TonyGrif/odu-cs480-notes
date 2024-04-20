---
Module: Problem Solving
Chapter: 6
Lectures:
  - "9"
  - "10"
  - "11"
---
# Constraint Satisfaction Problem
This method allows us to use a factored representation of each state to solve problems. Each problem requires a set of variables, a set of domains, and a set of constraints to specify valid combinations of values. The order of value assignments is irrelevant and the path is not stored.
## Constraints
Each constraint is a pair in the form $<scope, relation>$. Scope contains the affected variables while relation describes the possible values or a functional relation for said variables.
## State
A state is complete when all variables have a value. This state is also consistent if all assignments are in line with the constraints.
# Backtracking Algorithm
This type of search is the basic uninformed search for [[#Constraint Satisfaction Problem | CSPs]]. The is a [[Search Algorithms#Depth-First Search | depth-first search]] with no path tracking and assignment only occurs if it is in line with the given constraints.
## Pseudocode
```
fn BACKTRACKING-SEARCH(csp) -> solution | failure:
    return BACKTRACKING({}, csp)

fn BACKTRACKING(assignment, csp) -> solution | failure:
    if assignment is complete: return assignment

    var := UNASSIGNED-VAR(VARIABLES[csp], assignment, csp)
    for each val in ORDER-DOMAIN-VALUES(var, assignment, csp):
        if val is consistent with assignment:
            assignment += {var=value}
            result := BACKTRACK(assignment, csp)
            if result is success: return result
            else: remove {var=value} from assignment
    return failure
```
## Heuristics
Heuristics can be introduced to improve the previous [[#Pseudocode | uninformed search]].
### Variable Ordering
Dynamic ordering can be used to determine the choice for the next variable given what the state is in.
#### Minimum Remaining Values (MRV) Heuristic
This entails choosing the variable with the fewest legal moves. Failure is detected when a variable has no more legal values. This requires keeping track of the remaining legal values for variables.
#### Degree Heuristic
This chooses the variable involved in the largest number of constraints on other unassigned variables. To do this, you must keep track of the updated degrees for all unassigned variables.
### Value Ordering
These heuristics are used to determine which value to assign to the selected variable.
#### Least Constraining Value
This selects the least constraining (rules out the fewest values) value for the variable to maximize flexibility for other variables. This requires keeping track of remaining legal values for all other variables.
### Inference
Inference can be used to detect inevitable fails early. When a variable is chosen, prune the space by removing inconsistent values from other variables.
#### Forward Checking
This only checks the neighbors of the most recently assigned variable after each assignment. Backtracks whenever a variable has no legal values remaining.
#### Constraint Propagation
This checks the whole state for illegal values remaining. When a value is deleted from a variable's domain, check all variables connected to it. Continue this loop until all illegal values are pruned from the domain.