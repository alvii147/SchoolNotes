# Simulated Annealing

**Simulated Annealing** is the simulation of physical annealing used as a search algorithm. The acceptance probability $\large p$ of a given solution is given by:
$$
\Large p = \begin{cases}
1 & \text{if } \Delta c \le 0 \\
e^\frac{\Delta c}{T} & \text{if } \Delta c \gt 0
\end{cases}
$$
where $\large \Delta c$ is the change in the cost, and $\large T$ is the current temperature.

## Annealing Schedule

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

## Cooperative Simulated Annealing

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