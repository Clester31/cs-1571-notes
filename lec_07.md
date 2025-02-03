# Lecture 7

## Defining Constraint Satisfaction Problems

* A constraint selection problem (CSP) consists of three components X, D, and C
  * X is a set of variables {x1... xn}
  * D is a set of domains {d1... dn}
  * C is a set of constrains that specify allowable combination of values
 
* CSPs deal with assignments of values to variables
  * A complete assignment is one in which every variables is assigned a vale, and a solution to a CSP is a consistent, complete assignment
  * A partial assignment is one that leaves some variables unassigned
  * Partial solution is a partial assignment that is consistent

### Constraint satisfaction problems (CSPs)

* Standard search problem:
  * State is a black-box - any old data structure that supports goal test, eval, successor
 
* CSP:
  * State is defined by variables X1, with values from domain D1
  * Goal test is a set of constraints specifying allowable combinations of values for subsets of variables
 
* Simple example of a formal representation language
* Allows useful general-purpose algorithms with more power than standard search algorithms

### Constraint Graph

* Binary CSP: Each constraint relates at most two variables
* Constraint Graph: nodes are variables, arcs show constraints

* General-purpose CSP algorithms use the graph structure
* To speed up search. E.g., Tasmania is an independent subproblem

### Varieties of CSPs

* Discrete variables
  * Finite domains; size d => O(d^n) complete assignments
  * Infinite domains:
* Continuous Variables

### Varieties of Constraints

* Unary constraints involve a single variable
* Binary constraints involve pairs of variables
* Hihger-order constraints onvolve 3 or more variables
* Preferences (soft constraints) e.g., red is better than green often represented by a cost for each variable assignment

## Standard Search Formulation

* Let's start with the straigntforward, dumb approach, then fix it
* States are defined by the values assigned so far
  * Inital state: The empty assignment, { }
  * Successor function: Assign a value to an unassigned variable that does not conflict with the current assignment
    * Fail if no legas assignments (not flexible)
   
* This is the same for all CSPs
* Every solution apears at depth n with n variables
* Path is irrelevant, so can also use complete-state formulation
* b = (n - e)d at depth e, hence n!d^n leaves

### Backtracking Search

* Variable assignments are commutative, i.e., {WA = red then NT = green} same as [NT = green then WA = red]
* Only need to consider assignments to a single variable at each node

* Depth-first search for CSPs with single-variable assignments is called backtracking search
* Backtracking search is the basic uniformed algorithm for CSPs
* Can solve n-queens for n ~ 25

* 
