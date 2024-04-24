---
Module: Knowledge, Reasoning, and Planning
Chapter: 7
Lectures:
  - "15"
  - "16"
  - "17"
  - "18"
---
Logic is formal languages for representing information to draw conclusions. *Syntax* defines the structure of sentences; *Semantics* define the meaning of sentences. In standard logic, all sentences must be either true or false.
# Models
A model is a mathematical abstraction to determine the truth/falsity of a sentence. A model (m) exists for a sentence if the sentence is true in the model. $M(sentence)$ is the set of all models of the sentence.
# Logical Reasoning
Logical reasoning relies on relationship between sentences and inferences that can be drawn from the link.
## Entailment
This is the idea that a sentences follows logical from another.
* Syntax: $\alpha\vDash\beta$ iff $M(\alpha) \subseteq M(\beta)$
* Semantics: Sentence $\alpha$ entails sentence $\beta$ if when $\alpha$ is true, $\beta$ is also true

Note: If the first sentence is false, then the second can be any value and the formula still holds.
## Logical Inference
The process of applying [[#Entailment | entailment]] to derive conclusions from a knowledge base.
* Syntax: $KB\vDash_{i}\alpha$
* Semantics: $\alpha$ is derived from $KB$ by inference procedure $i$

An inference is satisfiable if: $KB\vDash\alpha$ if and only if ($KB \land \lnot\alpha$) is unsatisfiable (proof by contradiction).

A sentence is *satisfiable* if it is true in some model; it is *valid* if it is true in all models.
### Truth Table Approach
Enumerate all the [[#Models | models]] and check that $\alpha$ is true in all instances $KB$ is also true using [[Propositional Logic | propositional logic]].
### Inference Rules
Given the premise is true, apply [[inference-rules.png | inference rules]] to verify the conclusion. Continue applying the rules, until a determination is reached on if the new sentence can be derived from the knowledge base's sentences.
### Resolution Algorithm
This algorithm applies the [[Resolution Inferences Rules | resolution inferences rules]] to derive any conclusion from the knowledge base. All sentences in the knowledge base must be in [[Conjunctive Normal Form | CNF]] for the rules to work.

1. Convert $KB\land\lnot\alpha$ to [[Conjunctive Normal Form | CNF]].
2. Once all $KB$ clauses and $\lnot\alpha$ are in CNF, apply [[Resolution Inferences Rules | resolution rules]] to each clause to create new clauses.
3. Continue until:
    * No new clauses can be added ($KB$ does **not entail** $\alpha$).
    * Two clauses resolve to yield an empty clause ($KB$ **does entail** $\alpha$.