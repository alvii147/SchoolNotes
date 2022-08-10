# Tabu Search

**Tabu Search** is a meta-heuristic algorithm that uses a combination of local search strategy and memory structures to escape local minima and implement an explorative strategy. It entails forbidding or penalizing moves which take the solution to previously visited states.

## Short-Term Memory

Tabu Search uses short-term memory based on the **recency of occurrence** of solution components to prevent the search from revisiting previously visited solutions, and to keep track of good components to return to in order to intensify the search.

## Long-Term Memory

Tabu Search uses long-term memory based on the **frequency of occurrence** of solution components from the start of the iterations, using it to diversify the search and explore unvisited areas of the solution space by avoiding frequently visited components.

## Tabu List

**Tabu List** is the short-term memory used in Tabu Search that holds a fixed and limited amount of information. Recently performed actions are saved in the Tabu List in order to prevent reverse moves.

## Tabu Tenure

**Tabu Tenure $\large T$** is the number of iterations for which a certain action is stored in the Tabu List.

If the Tabu Tenure is static, rule of thumb is to set:
$$
\Large T = \sqrt{n}
$$
Dynamic Tabu Tenure involves randomly varying between values $\large T_{min}$ and $\large T_{max}$.

## Aspiration List

**Aspiration List** is a list of promising actions that are saved according to the aspiration criteria. Actions in the Aspiration List can override actions in the Tabu List.

The next state in Tabu Search is selected randomly from the following set:
$$
\Large \{ N(s) - T(s) \} + A(s)
$$
where $\large N(s)$ is the neighborhood, $\large T(s)$ is the Tabu List, and $\large A(s)$ is the Aspiration List.