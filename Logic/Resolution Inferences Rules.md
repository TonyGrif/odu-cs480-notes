---
Module: Knowledge, Reasoning, and Planning
Chapter: 7
Lectures:
  - "18"
---
# Unit Resolution Rule
From a clause, if one literal is false you can infer the other one is true.
# Full Resolution Rule
From two clauses, a new clause is produced containing all literals except the one pair of complementary literals. Only one pair of complementary literals can be resolved at a time.
## Example
$$
\dfrac{\alpha\lor\beta, \lnot\beta\lor\gamma}{\alpha\lor\gamma} or
\dfrac{\lnot\alpha\rightarrow\beta, \beta\rightarrow\gamma}{\lnot\alpha\rightarrow\gamma}
$$
