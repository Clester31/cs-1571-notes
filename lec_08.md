# Lecture 8

## Knowledge Representation

* Objective: Express knowledge about the world in a computer-tractable form
* Use knowledge representation languages (KRLs)
* Related Problem:
  * Develop procedures (inference procedures) that can actively use knowledge to support inferences, that is, procedures that can derive (infer) statements that follow from the knowledge but are not explicitly stated
 
### Knowledge Bases

![image](https://github.com/user-attachments/assets/66c58da1-6735-4f2d-983e-53369b96d39f)

* Knowledge base = set of sentences in a formal language
* Declarative approach to building an agent: **Tell it what it needs to know**
* Then it can ask itself what to do - answers should follow from the knowledge base
* Agents can be viewed at the knowledge level
  * i.e., what they know, regardless of how implemented
* or, at the implementation level
  * i.e., data structures in KB and algorithms that manipulate them   

### Wumpus world Characterization

* Observable: no - only local perception
* Deterministic: yes - outcome exactly specified
* Episodic: no - sequential at the level of actions
* Static: yes - wumpus and pits do not move
* Discrete: yes
* Single-agent: Yes - wumpus is essnetially a natural feature

## Logic in general

* **Logics** are formal languages for representing information such that conclusions can be drawn
* **Syntax** defines the sentences in the language
* **Semantics** define the "meaning" of sentences
  * i.e., define truth of a sentence in a world

### Entailment

* Entailment means that one thing follows from another
  * KB |= a 
* Knowledge base KB entails sentance a iff a is true in all worlds where KB is true
* E.g., the KB containing "The Giants won" and "The Reds won" entails "Either the Giants won or the Reds won"
* E.g., x + y = 4 entails 4 = x + y
* Entailment is a relationship between sentences that is based on semantics

### Models

* Logicians typically think in terms of models, which are formally structured worlds with respect to which truth can be evaluated
* We say m is a model of a sentance a if a is true in m
* M(a) is the set of all models of a
* Then KB |= a iff M(KB) ⊆ M(a)
* E.g., KB = Giants won and Reds won, a = Giants won

### Propositional Logic Syntax

* Atomic sentences: Constructed from constants and propositional symbols
  * True, false are (atomic) sentences
  * P, Q or _Light in the room is on. it rains outside_ are atomic sentences
* Composite sentences: Constructed from valid sentences via logical connectives 
