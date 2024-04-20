---
Module: Artificial Intelligence
Chapter: 2
Lectures:
  - "1"
---
[[Rational Agents | Rational agents]] that maintain an internal state updated by agent actions. Agents are measured based how world evolves *independent* from agent. Actions are chosen based on knowledge of how the world works and the current percepts.
# Pros & Cons
* Pros: Can handle partially observable [[Environment Overview| environment]] by keeping state.
* Cons: No way to express goals and preferences relative to goals.
# Psuedocode
```
fn MODEL-BASED-AGENT(percept) -> action
  persistent state := agent's current conception of state
  persistent model := how next state depends on current state 
    and action
  persistent rules := set of condition-action rules
  persistent action := most recent action

  state := UPDATE-STATE(state, action, percept, model)
  rule := RULE-MATCH(state, rules)
  action := rule.Action
  return action
```