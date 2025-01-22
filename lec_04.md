# Lecture 4

## More Searching algos

* Best first search = evaluation-function driven search
* Greedy search = look for the shortest path, ignore any other options along the way
  * Not complete, we can loop forever
  * However, elimination of state repeats can solve the problem
  * So technically it is complete?
  * Not optimal
 
* A* search -> f(n) = g(n) + h(n)
  * g(n) = cost of reaching the state
  * h(n) = estimate of the cost of the path length
  * f(n) = estimate of the path length
 
* A* properties
  * Complete: Yes. Can't get stuck in an infinite loop
  * Can overestimate or underestimate in certain conditions, making it admissible
 
### Iterative Depth Algorithm (IDA)

* Complete: Yes
* Optimal: Yes
* Time Complexity: O(b^d)
* Memory (space) complexity: O(db)

#### IDA*

* progressively increase the evaluation function limit (instead of the depth limit)
* Performs limited cost depth first search for the current evaluation function limit
