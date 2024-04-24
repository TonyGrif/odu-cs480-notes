---
Module: Knowledge, Reasoning, and Planning
Chapter: 8
Lectures:
  - "19"
---
First-Order [[Logic Overview | Logic]] assumes the world contains objects, relations, and functions and presents a logical system for reasoning the relations among objects.

*Objects* are the nouns, *Relations* are the verbs, and *Functions* map objects to objects.
# Quantifiers

| Symbol        | Meaning       | Main Connective |
| :------------ | ------------- | --------------- |
| $\forall(x)$  | All x...<br>  | $\rightarrow$   |
| $\exists(x)$  | Some x...     | $\land$         |
| $\nexists(x)$ | No x...       |                 |
| $\exists!$(x) | Only one x... |                 |

Quantifiers of the same type are commutative, but ones of different types are not.

Quantifiers can change types through [[quantifiers-demorgan.png | De Morgan's Law]]
# Sentences
Sentences take the form of $predicate(term_1, ..., term_n)$ or $term_1 = term_2$. A term refers to a constant, variable, or function.

Complex sentences can then be formed using connectives. First-order logic uses the same as [[Propositional Logic#Symbols| propositional logic]]. 

Two terms can be equal to each other only if they have the same interpretation. This only applies to objects; to apply to propositions, use $\iff$.