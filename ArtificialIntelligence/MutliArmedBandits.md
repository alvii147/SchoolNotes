# Multi-Armed Bandits

A **Multi-Armed Bandit** problem is a hypothetical experiment where an agent must choose between multiple actions, each with an unknown payout.

A **$\large k$-armed bandit** provides $\large k$ actions, each with expected or mean rewards.
$$
\Large q_*(a) = \mathbb{E}[R_t | A_t = a]
$$
where $\large q_*(a)$ is the expected reward (also referred to as the *value*) when action $\large a$ is selected, $\large A_t$ is the action selected at time step $\large t$, and $\large R_t$ is the corresponding reward. $\large Q_t$ is the estimated value of $\large q_*(a)$ at time step $\large t$.