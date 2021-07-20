# Probability

## Set Notation

- $\large S$: sample space, set of all possible outcomes of an experiment
- $\large E$: event, a subset of the sample space
- $\large E_1 \cup E_2$: the union of $\large E_1$ and $\large E_2$
- $\large E_1 E_2 = E_1 \cap E_2$: the intersection of $\large E_1$ and $\large E_2$
- $\large \bigcup\limits^\infty_{n = 1}E_n = E_1 \cup E_2 \cup E_3 ...$
- $\large \bigcap\limits^\infty_{n = 1}E_n = E_1 \cap E_2 \cap E_3 ...$
- $\large E^C$: all outcomes not in $\large E$
- $\large E_1 \subset E_2$: implies all elements in $\large E_1$ are contained by $\large E_2$
- $\large E_1 \subset E_2$ and $\large E_2 \subset E_1 \implies E_1 = E_2$

## De Morgan's Laws

$$
\Large \Bigg(\bigcup^n_{i = 1} E_i\Bigg)^C = \bigcap^n_{i = 1} E_i^C \\[15pt]
\Large \Bigg(\bigcap^n_{i = 1} E_i\Bigg)^C = \bigcup^n_{i = 1} E_i^C \\[15pt]
$$

## Independent Events

**Independent events** are events such that their outcomes are independent of one another.
$$
\Large E_1 \text{ & } E_2 \text{ are independent } \implies P(E_1 \cap E_2) = P(E_1) \times P(E_2)
$$

## Mutually Exclusive Events

**Mutually exclusive events** are events that cannot occur at the same time.
$$
\Large E_1 \text{ & } E_2 \text{ are mutually exclusive } \implies P(E_1 \cup E_2) = P(E_1) + P(E_2)
$$

## Probability Axioms

### Axiom 1

The probability of an event must be a real-valued number between 0 and 1 inclusive.
$$
\Large 0 \le P(E) \le 1
$$

### Axiom 2

The probability of the entire sample space is 1.
$$
\Large P(S) = 1
$$

### Axiom 3

For any sequence of mutually exclusive events $\large E_1, E_2, ..., E_n$, the probability of the union of these events is the sum of the probability of these events.
$$
\Large P\Bigg(\bigcup\limits^n_{i = 1}E_i\Bigg) = \sum\limits^n_{i = 1}P(E_i)
$$

### Other Propositions

- $\Large P(E^c) = 1 - P(E)$
- $\Large E_1 \subset E_2 \implies P(E) \le P(F)$

## Inclusion-Exclusion Principle

$$
\Large \begin{align*}
P\Bigg(\bigcup\limits^n_{i = 1}E_i\Bigg) = &\sum\limits^n_{i = 1} P(E_i) - \sum\limits_{1 \le i \le j \le n} P(E_i \cap E_j) \\[15pt]
& + \sum\limits_{1 \le i \le j \le k \le n} P(E_i \cap E_j \cap E_k) \\[15pt]
& - ... + (-1)^{n - 1} P\Bigg(\bigcap\limits^n_{i = 1} E_i\Bigg)
\end{align*}
$$

## Conditional Probability

**Conditional probability** refers to the probability of an event occurring given the fact that another event has occurred.
$$
\Large \text{Probability of } E_1 \text{ given } E_2 = P(E_1 | E_2) = \frac{P(E_1 \cap E_2)}{P(E_2)}
$$

## Bayes' Theorem

Consider mutually exclusive events $\large E_1, E_2, E_3, ..., E_n$, such that $\large \bigcup\limits^n_{i = 1} E_i = S$. Then,
$$
\Large P(E_j | E) = \frac{P(E_j \cap E)}{P(E)} = \frac{P(E_j)P(E | E_j)}{\sum\limits^n_{i = 1} P(E_i)P(E | E_i)}
$$
