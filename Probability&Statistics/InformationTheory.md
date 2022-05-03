# Information Theory

## Shannon Entropy

**Shannon Entropy** $\large H(X)$ of a distribution is the expected amount of information in an event drawn from that distribution. It gives a lower bound on the number of bits needed on average to encode symbols drawn from a distribution P.
$$
\Large H(X) = -\sum\limits_{x \in X} p(x) \log_2[p(x)]
$$
The Shannon Entropy measures:

- the degree of uncertainty in a value
- the amount of "surprise" in seeing this observation
- how much information is represented by this distribution

## Kullback-Liebler Divergence

**Kullback-Liebler Divergence** $\large KI$ is a method for measuring the dissimilarity between two probability distributions $\large P$ and $\large Q$. It can also be seen as the **Relative Entropy** measure between the two distributions.
$$
\Large KL(P||Q) = \sum^N_{i = 1} P(i) \log \Big[\frac{P(i)}{Q(i)}\Big]
$$

- $\large KL(P||Q) \ge 0$ and $\large KL(P||Q) = 0$ iff $\large P = Q$
- $\large KL(P||Q)$ represents the amount of information lost on approximating $\large Q$ with $\large P$
- In general, $\large KL(P||Q) \ne KL(Q||P)$

## Mutual Information

**Mutual Information** $\large MI$ between two vectors $\large X$ and $\large Y$ measures the dissimilarity between joint distribution $\large p(X, Y)$ and factored distribution $\large p(X) \: p(Y)$. Mutual Information also measures the reduction in uncertainty for one variable given a known value of the other variable.
$$
\Large MI(X, Y) = \sum\limits_{x \in X} \sum\limits_{y \in Y} p(X, Y) \log \Big[\frac{p(X, Y)}{p(X) \: p(Y)}\Big]
$$

- $\large MI(X, Y) \ge 0$
- $\large MI(X, Y) = 0$ iff $\large X$ and $\large Y$ are independent
- $\large MI(X, Y) = H(X) + H(X) - H(X, Y)$
- $\large MI(X, Y) = KL(p(X, Y), p(X) \: p(Y))$

## Information Gain

**Information Gain** $\large IG$ measures the reduction in entropy or surprise by splitting a dataset according to a given value of a random variable.
$$
\Large IG(Y, X) = H(Y) - H(Y|X)
$$
