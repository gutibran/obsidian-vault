Algorithms and techniques used in artificial intelligence.

Search for solutions for some kind of problem.
Knowledge for knowing information, how to represent information, and how to draw inference to use information it knows to make conclusions.
Uncertainty is for how a computer is not sure about a fact only sure with a certain probability.
Optimization for choosing the best way or better way to achieve a goal.
Learning from data and experience. This is machine learning.
Neural networks are inspired by human brains
Languages spoken by humans, natural language processing.

Look for a solution to a problem.

Agent is an entity that perceives its environment and acts upon that environment.
State is some configuration of the agent in its environment. Different sequence of actions is needed to reach
Initial state is the state where the agent begins.
Actions are choices that can be made in a state. Defined as a function $Actions(s)$ returns the set of actions that can be executed in state $s$.

Encoding of the state, actions, and relations between state and actions are usually some numerical format.
Transition model is a description of what state results from performing any applicable action in any state. $Result(s, a)$ returns the state resulting from performing action $a$ in state $s$.

State space is the set of all states that we can from the current state via any sequence of actions. Complicated diagram. Abstract representation as a graph with nodes. 

Goal test is way to determine whether the state is where you want to go. Needs a way to encode to check if a state is goal . What if there are multiple goal state. Finding a goal well.

Path cost is the numerical cost to reach the goal state. Each option will be labeled with a cost.

Search problem
- initial state
- actions
- transition model
- goal test
- path cost function

Solution is a sequence of actions that take us from initial state to goal state
optimal solution, lowest path cost, no way to do better, there may be multiple solutions


Node is a data structure taht keeps track of state, parent node (state before), an action (action took to get from parent to current node state), path cost (how long it took to get to current node).

explore options, new options
frontier is the data structure that holds all the options,

start with frontier with the initial state, only state that exists
loop and repeat some process
if frontier is empty there is no solution
remove a node from the frontier, multiple states
if node is goal then return the solution by applying the goal state
expand the node means to look at all the neighbors, consider all possible actions and ahat nodes i can get to from there, add resulting nodes to the frontier

problems with this approach
if actions are bidirectional can go back and forth between states, this would cause a loop
- keep track of what has already been explored, do not going bad to state if there is no need to

1. frontier that contains initial state
2. explored set
3. repeat
	1. if frontier is empty no solution
	2. remove node from frontier
	3. if node is goal stte return the soluiton
	4. add node to the xplorer state
	5. expand nodes and add resulting nodes to the frontier if they arent alreeayd in the frontier or explored set -> prevents the inifinite loops bnetween states

this depth first search -> always explore the deepest node, hit a dead end then go back and repeat

use a stack (LIFO) as the frontier.

breadth first search -> always explore the shallowest node, uses the queue (FIFO), first node added.

infiniute state space, there may never be a solution


bfs will check sequentially (kind of at the same time), explore shallower paths too


dfs -> may have memory savings
bfs -> explore alot of states

```python
def Node:
	
```