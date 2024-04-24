---
Module: Knowledge, Reasoning, and Planning
Chapter: 7
Lectures:
  - "15"
---
A knowledge-based [[Agent Overview | agent]] uses reasoning to decide which actions to take. These agents require:
* *Knowledge Base*: Set of sentences, expressed in a knowledge representation language, representing an assertion/fact about the world.
* *Inference Engine*: Derives new sentences from the old.
* List of actions of an agent.
    * `TELL`: Allows the agent to tell the knowledge base new sentences.
    * `ASK`: Allows the agent to ask the knowledge base what is known.

These agents must be able to represent [[Environment Overview | environment]] states, incorporate new percepts, update internals of state, deduce hidden properties of the world, and deduce the proper actions.
# Pseudocode
```
fn KB-AGENT(percept) -> Action:
    persistent knowledge_base
    persistent tc := a time counter

    TELL(knowledge_base, MAKE-PERCEPT-SENTENCE(percept, tc))
    action <- ASK(knowledge_base, MAKE-ACTION-QUERY(tc))

    // Tells the KB which action was choosen
    TELL(knowledge_base, MAKE-ACTION-SENTENCE(action, tc))
    
    t := t + 1
    return action
```
# Levels
The knowledge-based agent holds multiple levels that make it up.
## Knowledge Level
The behavior of the [[Agent Overview | agent]] is determined by the current knowledge it has perceived and the goal of the agent.
### Types of Knowledge
* Declarative: Knowledge about facts and things; defines the constraints and is used to perform [[Logic Overview#Logical Inference| inferences]].
* Procedural: Knowledge about how to do something; these can only be used in execution.
## Logical Level
This is the logical representation of the [[#Knowledge Level | knowledge level]]. This defined how to encode knowledge into a sentence through [[Logic Overview| logic]].
## Implementation Level
This is the physical representation of [[#Logical Level | logical]] and [[#Knowledge Level | knowledge]] levels. The programming languages and data structures used make up this level.