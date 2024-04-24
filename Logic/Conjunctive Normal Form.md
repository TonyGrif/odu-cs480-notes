---
Module: Knowledge, Reasoning, and Planning
Chapter: 7
Lectures:
  - "18"
---
Conjunctive normal form is a way to express [[Logic Overview | sentence]] clauses as a dis-junction of literals.
# Conversion to CNF
1. Replace $\alpha\Longleftrightarrow\beta$ with $(\alpha\rightarrow\beta)\land(\beta\rightarrow\alpha)$
2. Replace $\alpha\rightarrow\beta$ with $\lnot\alpha\lor\beta$
3. Move $\lnot$ inwards, pay attention to [[logical-equivalences.png| De Morgan's Law]]
4. Distribute $\lor$ over $\land$: $(\alpha\lor\beta)\land\gamma$ becomes $(\alpha\lor\gamma)\land(\beta\lor\gamma)$ 
5. Flatten nesting: $(\alpha\land\beta)\land\gamma$ becomes $\alpha\land\beta\land\gamma$