# Introduction to Game Theory

## Game Theory

**Game theory** is the study of mathematical models of strategic interactions among multiple rational agents. It involves modelling **cooperation** and **competition** between intelligent and rational decision-makers.

## Mechanism Design

**Mechanism design** involves the study of mechanisms by which a particular desirable outcome or result can be achieved.

## Preferences & Utilities

### Outcomes & Lotteries

Let $\large O =\{o_1, ..., o_K\}$ be a set of $\large K$ mutually exclusive outcomes. A **lottery** $\large A$ describes a probability distribution over outcomes $\large O$. We write $\large A = \sum\limits_k p_k o_k$ to indicate that $\large o_k \in O$ happens with probability $\large p_k$.

For e.g. $\large A = 0.75 o_1 + 0.25 o_2$ means $\large P(o_1) = 0.75$ and $\large P(o_1) = 0.25$.

A **compound lottery** is a lottery defined based on other lotters.

For e.g., suppose $\large O = \{o_1, o_2, o_3\}$, and lotteries $\large A$ and $\large B$ are defined as follows:

- $\large A = 0.2 o_1 + 0.8 o_2$
- $\large B = 0.4 o_1 + 0.6 o_2$

Then, lottery $\large C$, defined by $\large C = 0.5 A + 0.5 B$, is a compound lottery.
$$
\large C = 0.5 (0.2 o_1 + 0.8 o_2) + 0.5 (0.4 o_1 + 0.6 o_3) = 0.1 o_1 + 0.6 o_2 + 0.3 o_3
$$

### Ordinal Preferences

A **preference relation** over lotteries can be defined as follows:

- $\large A \succ B$ means an agent **strictly prefers** $\large A$ to $\large B$
- $\large A \succeq B$ means an agent **weakly prefers** $\large A$ to $\large B$
- $\large A \sim B$ means an agent is **indifferent** between $\large A$ and $\large B$ (i.e. $\large A \succeq B$ and $\large B \succeq A$)

#### Completeness

$\large \forall$ lotteries $\large A, B$, either $\large A \succ B$ or $\large B \succ A$ or $\large A \sim B$

#### Transitivity

$\large \forall$ lotteries $\large A, B, C$, $\large A \succeq B$ and $\large B \succeq C \implies \large A \succeq C$

#### Independence of Irrelevant Alternative

$\large \forall$ lotteries $\large A, B, C$, $\large \forall p \in [0, 1]$, $\large A \succeq B \iff pA + (1 - p) C \succeq pB + (1 - p) C$

#### Continuity

$\large \forall$ lotteries $\large A, B, C$, $\large A \succeq B \succeq C \implies \exist p \in [0, 1]$ such that $\large B \sim pA + (1 - p)C$

### Utilities

For any von Neumann-Morgenstern-rational agent, there exists a function $\large u$ (known as the von Neumann-Morgenstern utility) that maps each lottery $\large A$ to a real number $\large u(A)$, such that:

- $\large u(A) = u(\sum\limits_k p_k o_k) = \sum\limits_k p_k u(o_k)$
- $\large u(A) \ge u(B) \iff A \succ B$
