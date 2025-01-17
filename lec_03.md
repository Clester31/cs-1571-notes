# Lecture 3

## Problem Solving Agents

### Problem Types

* Deterministic, fully observable => single-state problem
  * Agent knows exactly which stae it will be in; solution is a sequenece
 
* Non-observable => conformant problem
  * Agent may have no idea where it is; solution (if any) is a sequence
 
* Non-deterministic and/or partially observable => contingency problem
  * percepts provide new information about current state
  * Solution is a contingent plan or a policy
  * often interleave search, execution
 
* Unknown state space => exploration problem (outline)

### Single-state problem formulation

* A problem is defined by four items
  * Inital State => e.g., "at Arad"
  * Successor function => S(x) = set of action-state pairs
    * e.g., S({Arad -> Zerind, Zerind} ,...}
  * Goal test, can be
    * explicit, e.g., x = "at Bucharest"
    * implicit, e.g., NoDirt(x)
  * Path cost (additive)
    * e.g., sum of distances, number of actions executed, etc.
    * c(x, a, y) is the step cost, assumed to be >= 0
  * A **solution** is a sequence of actions leading from the inital state to a goal state
 
### Selecting a State Space

* Real world is absurdly complex
  * State space must be abstracted for problem solving
 
* (Abstract) state = set of real states
* (Abstract) action = complex combination of real actions
  * e.g., "Arad -> Zerind" represents a complex set
    * Of possible routes, detours, rest stops, etc.
* For guaranteed reliability, any real state "in Arad"
* (Abstract) solution = set of real paths that are solutions in the real world
* Each abstract action should be “easier” than the original problem

## Example Problems

### Vacuum Robot

![image](https://github.com/user-attachments/assets/1326c8f7-986f-4438-afaa-a99428a3ae84)

### The 8-Puzzle

![image](https://github.com/user-attachments/assets/5399eac2-3a6d-45ec-b024-cd1f0a38ef76)

### Robotic Assembly

![image](https://github.com/user-attachments/assets/efdfcdda-9d31-43e4-bce9-41aeff1da57b)

* states: real-valued coordinates of robot joint angles parts of the object to be assembled
* actions: continuous motions of robot joints
* goal test: complete assembly with no robot included!
* path cost: time to execute

## Search strategies

* A strategy is defined by picking the order of node expansion
* Strategies are evaluated along the following circumstances
  * Completeness - does it always find a solution if one exists
  * Time complexity - number of nodes generated/expanded
  * Space complexity - maximum number of nodes in memory
  * Optimally - does it always find a least-cost solution
 
* Time and space complexity are measured in terms of
  * b - maximum branching factor of the search tree (how many children does each node in the tree have)
  * d - depth of least solution
  * m - maximum depth of the state (may be infinite)
 
* Uninformed strategies only use the information available in the problem definition

### Tree Search Algorithms

* Basic idea: offline, simulated exploration of state space by generating successors of already-explored states (a.k.a. expanding states)

### Implementation states vs nodes

* A state is a (representaion of) a physical configuration
* A node is a data structure constituting part of a search tree
  * Includes parent, children, depth, path of cost g(x)
* States fo not have parents, children, depth, or path cost
* The expand function creates new nodes, filling in the various feilds and using the SuccessorFn of the problem to create the corresponding states  

### Properties of Breadth First search

* Complete?: Yes (if b is finite)
* Time? O(b^(d+1))
* Space?: O(b^(d+1)) -> bad!
* Optimal?: Yes (if cost = 1 per step); not optimal in general

### Properties of Uniform-Cost search (Djikstra's)

* Expand least-cost unexpanded node
* Implementation:
  * Fringe = queue ordered by path cost, lowest first
* Equivalent to breadth-first if step costs all equal

* Complete?: Yes, if step cost >= c
* Time? # of nodes with g ≤ cost of optimal solution, O(b fC∗/cl) where C∗ is the cost of the optimal solution
* Space? # of nodes with g ≤ cost of optimal solution, O(b fC∗/cl)
* Optimal? Yes—nodes expanded in increasing order of g(n)
  
### Properties of Depth-First search

* Complete?: No. Fails in infinite-depth spaces, or spaces with loops
* Time?: O(b^m), terrible if m is much larger than d
  * But if solutions are dense, may be much faster than breadth-first
* Space?: O(bm), linear space
* Optimal?: No

### Depth-Limited search

* Depth-first search with depth limit l,
* nodes at depth l have no successes

### A* Search

* Idea: Avoid expanding paths that are already expensive
* Evaluation function: _F(n) = g(n) + h(n)_

* g(n) = cost so far to reach n
* h(n) = estimated cost to goal from n
* f(n) estimated total cost of path through n to goal

* A* search uses an admissible heuristic
* Distance theorem: A* search is optimal
