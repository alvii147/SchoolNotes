# Multi-Armed Bandits

A **Multi-Armed Bandit** problem is a hypothetical experiment where an agent must choose between multiple actions, each with an unknown payout.

A **$\large k$-armed bandit** provides $\large k$ actions, each with expected or mean rewards.
$$
\Large q_*(a) = \mathbb{E}[R_t | A_t = a]
$$
where $\large q_*(a)$ is the expected reward (also referred to as the *value*) when action $\large a$ is selected, $\large A_t$ is the action selected at time step $\large t$, and $\large R_t$ is the corresponding reward. $\large Q_t$ is the estimated value of $\large q_*(a)$ at time step $\large t$.

## Exploration vs Exploitation

**Exploration** is the task of trying out new actions to learn their rewards.

**Exploitation** is the task of preferring actions that appear to have the best rewards.

A good solution to the multi-armed bandit problem should have a good balance of exploration and exploitation.

## $\epsilon$-Greedy Algorithm

The **$\large \epsilon$-Greedy Algorithm** involves choosing random exploration with probability $\large \epsilon$ and choosing exploitation with probability $\large 1 - \epsilon$.

### Incremental Implementation

We can use the average value of $\large R_i$ as an estimate for $\large Q_n$:
$$
\Large \begin{align*}
Q_{n + 1} &= \frac{R_0 + R_1 + ... + R_{n}}{n} \\[10pt]
&= Q_n + \frac{1}{n} [R_n - Q_n]
\end{align*}
$$

#### Pseudocode

$$
\Large \begin{align*}
& \text{Initialize, for } a = 0 \text{ to } k - 1 \text{:} \\
& Q = \text{zeros}(k) \: \larr \small \text{Estimated reward for each action} \\
& N = \text{zeros}(k) \: \larr \small \text{Number of times each action was chosen} \\ \\
& \text{Loop:} \\
& \:\:\:\:\:\:\:\: A =
\begin{cases}
\text{argmax}(Q) & \text{with probability } 1 - \epsilon \\
\text{rand\_index(Q)} & \text{with probability } \epsilon \\
\end{cases} \\ \\
& \:\:\:\:\:\:\:\: R = \text{bandit}(A) \\
& \:\:\:\:\:\:\:\: N[A] = N[A] + 1 \\
& \:\:\:\:\:\:\:\: Q[A] = Q[A] + \frac{1}{N[A]} (R - Q[A])
\end{align*}
$$

### Nonstationary Problems

For bandits that are nonstationary (i.e. they change over time), it makes sense to assign higher weight to more recently recorded rewards than to old ones. Thus, we can use a weighted average estimation method by using a defined step size $\large \alpha$:
$$
\Large \begin{align*}
Q_{n + 1} &= Q_n + \alpha [R_n - Q_n] \\[10pt]
&= (1 - \alpha)^n Q_1 + \sum\limits^n_{i = 1} \alpha(1 - \alpha)^{n - i} R_i
\end{align*}
$$

If $\large \alpha$ is varying in each step, the variation must conform to the following conditions in order to ensure $\large Q(a)$ converges to $\large q_*(a)$:
$$
\Large \sum\limits^\infty_{n = 1} \alpha_n = \infty \:\:\: \text{and} \:\:\: \sum\limits^\infty_{n = 1} \alpha_n^2 \lt \infty
$$

#### Pseudocode

$$
\Large \begin{align*}
& \text{Initialize, for } a = 0 \text{ to } k - 1 \text{:} \\
& Q = \text{zeros}(k) \: \larr \small \text{Estimated reward for each action} \\
& N = \text{zeros}(k) \: \larr \small \text{Number of times each action was chosen} \\ \\
& \text{Loop:} \\
& \:\:\:\:\:\:\:\: A =
\begin{cases}
\text{argmax}(Q) & \text{with probability } 1 - \epsilon \\
\text{rand\_index(Q)} & \text{with probability } \epsilon \\
\end{cases} \\ \\
& \:\:\:\:\:\:\:\: R = \text{bandit}(A) \\
& \:\:\:\:\:\:\:\: N[A] = N[A] + 1 \\
& \:\:\:\:\:\:\:\: Q[A] = Q[A] + \alpha (R - Q[A])
\end{align*}
$$

## Upper-Confidence-Bound Action Selection

Instead of selecting exploration or exploitation based on probability, it makes sense to explore more at the beginning and reduce exploration over time. **Upper-Confidence-Bound Action Selection** involves using an additional term that accounts for the uncertainty in the value of $\large Q(a)$:
$$
\Large A_t = \text{argmax}\Bigg[Q_t(a) + c\sqrt{\frac{\ln{t}}{N_t(a)}}\:\Bigg]
$$
where $\large N_t(a)$ denotes the number of times action $\large a$ has been selected and $\large c$ controls the degree of exploration.

#### Pseudocode

$$
\Large \begin{align*}
& \text{Initialize, for } a = 0 \text{ to } k - 1 \text{:} \\
& Q = \text{zeros}(k) \: \larr \small \text{Estimated reward for each action} \\
& N = \text{zeros}(k) \: \larr \small \text{Number of times each action was chosen} \\ \\
& \text{Loop:} \\
& \:\:\:\:\:\:\:\: A = \text{argmax}\Bigg[Q(a) + c\sqrt{\frac{\ln{i}}{N(a)}}\:\Bigg] \\ \\
& \:\:\:\:\:\:\:\: R = \text{bandit}(A) \\
& \:\:\:\:\:\:\:\: N[A] = N[A] + 1 \\
& \:\:\:\:\:\:\:\: Q[A] = Q[A] + \alpha(R - Q[A])
\end{align*}
$$

## Gradient Bandit Algorithm

The **Gradient Bandit Algorithm** involves learning a *numerical preference* $\large H_t(a) \in \mathbb{R}$ for each action $\large a$ and using that to determine the current action.

We define $\large \pi_t(a)$ as the probability of taking action $\large a$ at time $\large t$:
$$
\Large \begin{align*}
\pi_t(a) &= \text{Pr}\{A_t = a\} \\[15pt]
&= \frac{e^{H_t(a)}}{\sum^k_{i = 1}e^{H_t(i)}}
\end{align*}
$$
The learning algorithm for $\large H_t(a)$ is based on stochastic gradient ascent:
$$
\Large \begin{align*} H_{t + 1}(a) = H_t(a) + \alpha(R_t - \bar{R}_t)(1 - \pi_t(a)), \:\:\:\:\:\:\:\: &\text{where } a = A_t \\
H_{t + 1}(a) = H_t(a) - \alpha(R_t - \bar{R}_t)\pi_t(a), \:\:\:\:\:\:\:\: &\forall a \ne A_t
\end{align*}
$$
or equivalently:
$$
\Large H_{t + 1}(a) = H_t(a) + \alpha(R_t - \bar{R}_t)(1_{a=A_t} - \pi_t(a)), \:\:\:\:\:\:\:\: \forall a
$$
where $\large 1_{a=A_t}$ is an indicator function:
$$
\Large 1_{a=A_t} \begin{cases}
1 &\text{if} \:\: a = A_t \\
0 &\text{if} \:\: a \ne A_t
\end{cases}
$$
