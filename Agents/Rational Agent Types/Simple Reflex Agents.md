---
Module: Artificial Intelligence
Chapter: 2
Lectures:
  - "1"
---
These types of [[Rational Agents | rational agents]] are the most simple ones to implement. Actions depend only on current percept with no memory of percept history. The agent function is based on condition-action rules.
# Pros & Cons
* Pros: Easy to implement and efficient if [[Environment Overview| environment]] is fully observable.
* Cons: Has limited power and utility in complex [[Environment Overview| environment]].
# Psuedocode
```
fn SIMPLE-REFLEX-AGENT(current_percept) -> action
    persistent rules: set of condition-action rules

    state := INTERPRET-INPUT(percept)
    rule := RULE-MATCH(state, rules)
    action := RULE-ACTION(rule)
    return action
```