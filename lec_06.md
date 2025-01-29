# Lecture 5

## Genetic Algorithms

* Create a population of random configurations
* Create a new population through:
  * Biased selection of pairs of configurations from the previous population
  * Crossover (combination) of selected pairs
  * Mutation of resulting individuals
* Evolve the population over multiple generation cycles

* Elite selecttion: Top percentage of the population in one generation is transferred to the next generation
* Culling: bottom percentage of the population not considered for reproduction

## Optimal Configuration Search

* Configurations are described in terms of variables and their values
* Each configuration has a quality measure
* Goal: Find the configuration with the best value

### Parametric Optimization

* Configurations are described by a set of variables with real-valued values. A specific set of values assigned to variables defines a configuration. These can be a real value vector _w_
* Goal: We want to find the best set of values w* from among all possible values of w optimizing the objective function f (w). w* = argmax f (w)

...


## Constraint Satisfaction Problem

* Path search: We seek a path from the initial state to a state satisfying the goal condition (Puzzle8, Route Finding)
* Configutation search: We seek a state (configuration) satisfying the goal condition

* Constraint Satisfaction Problem
  * A configuration search problem where
    * A state is defined by a set of variables and their values
    * Goal condition is represented by a set of constraints on possible variable values

### CSP Example: N-queens

* Goal: n queens placed in non-attacking positions on the  _n_ x _n_ board
* Variables:
  * Represent queens, one for each column
    * Q1, Q2, Q3, Q4 
  * Values:
    * Row placement of each queen on the board {1, 2, 3, 4}
 
* Constraints
  * qi =/= qj (Two queens not in the same row)
  * |qi - qj| /=/ |i - j| (Two queens not on the same diagonal)

## Satisfiability Problem

* Determine whether a sentence in the conjuncitve normal form (CNF) is satisfiable (can evaluate to true)
* Variables
  * Propositional Symbols (P, R, T, S)
  * Values: True, False
* Constraints
  * Every conjunct must evaluate to true, at least one of the literals must evaluate to true   
