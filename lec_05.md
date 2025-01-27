# Lecture 5

## Local Search and Optimization Problems

* In many optimization problems, path is irrelevant; the goal state itself is the solution
* Then state space = set of "complete" configurations; find **optimal** configuration
* Iterative improvement algorithms keep a "current" state, and try to improve it
* Local search algos operate by serving from a start state to a neighboring state without keeping track of the paths, nor the set of state that have been reached

### Optimal Configuration Problem

* Objective: Find the best configuration/state
  * Quality of the state is defined by a quality measure that reflects our preference towards each configuratino (or state)
  * Also referred to as the Objective Function
* Goal: find a configuration that gives the best objective function value

### Search for optimal configuration

* Optimal search configuration problem
  * State (configuration) space
  * Objective function q(s) that reflect our prefernce towards state s
  * GOal: find the configuration with the best value
 
### Iterative Optimization Methods

* Search the apce of "complete" configurations
* Take advantage of local moves
  * Define operators that make "local" changes to "complete" configurations
* Keep track of just one state (the curent state)

### Simulated Annealing

* A modification of the random walk search procedure
  * Permits both "good" and "bad" moves, but good moves are preferred over bad moves
  * **Gradually Decreases** the frequency of "bad" moves and ther size'
 
* Idea: escape local maxima by allowing some "bad" moves **but gradually decrease their size and frequency**
* Random walk will always accept the better state. Annealing with choose at random to pick a good or bad state

#### Simulated Annealing Algorithm

* Basic iteration step:
  * Choose uniformly at random one of the local neighbors of the current state as a candidate state (the same as random walk)
  * **if** the candidate state is better than the current state
    *  **then** accept the cnadidate and make it the current state
  *  **else** calculate the probability p(ACCEPT) of accepting it; using p(ACCEPT) choose randomly whether to reject or accept the candidate
* End

* Properties of hte simulated annealing methods
  * If temperature T is decreased slowly enough, the best configuration (state) is reached with high confidence
 
#### Simulate Annealing Limitations

* Only persues one state configuration at a time
* Changes to configurations are typically local

## Genetic Algorithm

* Create a population of random configurations
* Create a new population through
  * Biased selection of pairs of configurations from the previous population
  * Crossover (combination) of selected pairs
  * Mutation of resulting individuals 
