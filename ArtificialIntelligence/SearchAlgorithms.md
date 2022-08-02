# Search Algorithms

## Properties of Search Algorithms

### Completeness

**Completeness** is whether or not the algorithm is guaranteed to find a goal (provided at least one goal exists).

### Optimality

**Optimality** is whether or not the algorithm is guaranteed to find the shallowest goal (i.e. the goal with the lowest cost).

### Time Complexity

**Time Complexity** refers to the degree of time consumed by the algorithm.

### Space Complexity

**Space Complexity** refers to the degree of memory space consumed by the algorithm.

## Search Tree Terminology

**Node:** a state in the search problem

**Edge:** an action or a transition between states in the search problem

**Branching Factor, $\large b$:** the maximum number of child nodes extending from a parent node

**Shallowest Goal Depth, $\large d$:** the number of edges to the shallowest goal node

**Maximum Depth, $\large m$:** the number of edges to the further node

## Heuristics

**Heuristics** are solution strategies by trial and error used to produce acceptable (optimal or sub-optimal) solutions to complex problems in a reasonably practical time. Heuristics aim to efficiently generate good solutions, but does not guarantee optimality. Heuristics:

- have short running times
- are easy to implement
- are flexible
- are simple

A heuristic function $\large h(n)$ is one that uses domain knowledge and estimates the *goodness* of node $\large n$. It is the estimated cost of the minimal cost path from node $\large n$ to a goal node.

### Admissible Heuristic

An **admissible heuristic** function is one that never overestimates the cost of reaching a goal:
$$
\Large h(n) \le h^*(n), \:\:\:\: \forall n
$$
where $\large h^*(n)$ is the true cost of the minimal cost path from node $\large n$ to a goal node.

## Breadth-First Search

Property | Remarks
--- | ---
**Complete** | Yes, if $\large b$ is finite
**Optimal** | Yes, if path cost is equal to depth
**Time Complexity** | $\large O(b^{d + 1})$
**Space Complexity** | $\large O(b^{d + 1})$

## Depth-First Search

Property | Remarks
--- | ---
**Complete** | Yes, if $\large m$ is finite
**Optimal** | No
**Time Complexity** | $\large O(b^m)$
**Space Complexity** | $\large O(bm)$

## Uniform-Cost Search

Property | Remarks
--- | ---
**Complete** | Yes
**Optimal** | Yes
**Time Complexity** | $\Large O(b^{\frac{C^*}{\epsilon} + 1})$
**Space Complexity** | $\Large O(b^{\frac{C^*}{\epsilon} + 1})$

$\large C^*$ and $\large \epsilon$ are costs of the goal path and the minimum cost of all the other edges respectively in the worst case scenario.

## Depth-Limited Search

Property | Remarks
--- | ---
**Complete** | Yes, if $\large l \ge d$
**Optimal** | No
**Time Complexity** | $\large O(b^l)$
**Space Complexity** | $\large O(bl)$

## Iterative-Deepening Search

Property | Remarks
--- | ---
**Complete** | Yes, if $\large b$ is finite
**Optimal** | Yes, if path cost is equal to depth
**Time Complexity** | $\large O(b^d)$
**Space Complexity** | $\large O(bd)$

## Greedy Search

Property | Remarks
--- | ---
**Complete** | No
**Optimal** | No
**Time Complexity** | $\large O(b^m)$
**Space Complexity** | $\large O(b^m)$

## Beam Search

Property | Remarks
--- | ---
**Complete** | No
**Optimal** | No
**Time Complexity** | $\large O(\beta m)$
**Space Complexity** | $\large O(\beta m)$

$\large \beta$ is the beam width.

## A* Search

Property | Remarks
--- | ---
**Complete** | Yes, if $\large h(n)$ is admissible
**Optimal** | Yes, if $\large h(n)$ is admissible

## Hill-Climbing Search

Property | Remarks
--- | ---
**Complete** | No
**Optimal** | No

## Max-Min Strategy

Property | Remarks
--- | ---
**Complete** | Yes, if tree is finite
**Optimal** | Yes, if opponent is optimal opponent
**Time Complexity** | $\large O(b^d)$
**Space Complexity** | $\large O(bd)$

## Simulated Annealing

**Simulated Annealing** is the simulation of physical annealing used as a search algorithm. The acceptance probability $\large p$ of a given solution is given by:
$$
\Large p = \begin{cases}
1 & \text{if } \Delta c \le 0 \\
e^\frac{\Delta c}{T} & \text{if } \Delta c \gt 0
\end{cases}
$$
where $\large \Delta c$ is the change in the cost, and $\large T$ is the current temperature.

### Annealing Schedule

The **annealing schedule** is the mapping between temperature $\large T$ and iteration $\large t$.

**Linear Annealing Schedule:**
$$
\Large T_{t + 1} = T_t - \alpha
$$
**Geometric Annealing Schedule:**
$$
\Large T_{t + 1} = T_t \times \alpha
$$
**Asymptotic Annealing Schedule:**
$$
\Large T_{t + 1} = \frac{1}{1 + \alpha T_t}
$$

### Cooperative Simulated Annealing

**Cooperative Simulated Annealing** consists of $\large n$ solutions being searched simultaneously. Thus, the problem state population $\large Pop_{t}$ at iteration $\large t$ consists of $\large n$ states $\large S_i$:
$$
\Large Pop_t = [S_1, S_2, ..., S_n]
$$
At every iteration, the search algorithm generates a new population $\large Pop_{t + 1}$:
$$
\Large Pop_{t + 1} = [S_{1\:new}, S_{2\:new}, ..., S_{n\:new}]
$$
$\large S_{i\:new}$ is selected randomly from the **closer set** of $\large S_i$ and another randomly selected state $\large S_j$:
$$
\Large \text{CLOSER}(S_i, S_j) = \{s \in N(S_i) \: | \: d(s, S_j) \lt d(s, S_j) \}
$$
where $\large N(S_i)$ is the neighborhood of state $\large S_i$. If the closer set $\large \text{CLOSER}(S_i, S_j)$ is empty, $\large S_{i\:new}$ is randomly selected from $\large N(S_i)$.

The temperature is updated based on the different of the mean fitness of the new and old populations:
$$
\Large \Delta E = E(Pop_{t + 1}) - E(Pop_t)\\
\Large T = \begin{cases}
T & \text{if } \Delta E \lt 0 \\
\alpha T & \text{if } \Delta E \ge 0
\end{cases}
$$

## Tabu Search

**Tabu Search** is a meta-heuristic algorithm that uses a combination of local search strategy and memory structures to escape local minima and implement an explorative strategy. It entails forbidding or penalizing moves which take the solution to previously visited states.

### Short-Term Memory

Tabu Search uses short-term memory based on the **recency of occurrence** of solution components to prevent the search from revisiting previously visited solutions, and to keep track of good components to return to in order to intensify the search.

### Long-Term Memory

Tabu Search uses long-term memory based on the **frequency of occurrence** of solution components from the start of the iterations, using it to diversify the search and explore unvisited areas of the solution space by avoiding frequently visited components.

### Tabu List

**Tabu List** is the short-term memory used in Tabu Search that holds a fixed and limited amount of information. Recently performed actions are saved in the Tabu List in order to prevent reverse moves.

### Tabu Tenure

**Tabu Tenure $\large T$** is the number of iterations for which a certain action is stored in the Tabu List.

If the Tabu Tenure is static, rule of thumb is to set:
$$
\Large T = \sqrt{n}
$$
Dynamic Tabu Tenure involves randomly varying between values $\large T_{min}$ and $\large T_{max}$.

### Aspiration List

**Aspiration List** is a list of promising actions that are saved according to the aspiration criteria. Actions in the Aspiration List can override actions in the Tabu List.

The next state in Tabu Search is selected randomly from the following set:
$$
\Large \{ N(s) - T(s) \} + A(s)
$$
where $\large N(s)$ is the neighborhood, $\large T(s)$ is the Tabu List, and $\large A(s)$ is the Aspiration List.