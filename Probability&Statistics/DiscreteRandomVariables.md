# Discrete Random Variables

Let $\large S$ be the sample space associated with some experiment $\large E$. A **random variable** $\large X$ is a function that assigns a real number $\large X(s)$ to each elementary event $\large s \in S$. In this case, as the outcome of the experiment, i.e. the specific $\large s$, is not predetermined, then the value of $\large X(s)$ is not fixed. This means that the value of the random variable is determined by the specific outcome of the experiment.

A **discrete random variable** is one that can take on at most a countable number of possible values.

## Probability Mass Function

For a discrete random variable $\large X$, the **probability mass function** $\large p(a)$ of $\large X$ is defined as:
$$
\Large p(a) = P\{X = a\}
$$
### Properties

- $\large \sum\limits_i p(x_i) = \sum\limits_i p\{X = x_i\} = 1$

## Cumulative Distribution Function

For a discrete random variable $\large X$, the **cumulative distribution function** $\large F(x)$ is defined as:
$$
\Large F(x) = P\{X \le x\}
$$
### Properties

- $\large F(a) = \sum\limits_{all \: x \le a} p(x)$
- $\large a \lt b \implies \Large F(a) \le F(b)$
- $\large \lim\limits_{a \to \infty} F(a) = 1$
- $\large \lim\limits_{a \to -\infty} F(a) = 0$
- $\large \lim\limits_{n \to \infty} F(a_n) = F(a)$ for any decreasing sequence $\Large a_n$ that converges to $\large a$
- $\large P\{a \lt X \le b\} = F(b) - F(a)$

## Expected Value

For a discrete random variable $\large X$, the **expected value** $\large E[X]$ is defined as:
$$
\Large E[X] = \sum\limits_i x_i p(x_i)
$$

### Expected Value of a Function of a Random Variable

For a real-valued function $\large Y = g(X)$ of a random variable $\large X$, the expected value $\large E[Y]$ is defined as:
$$
\Large E[Y] = E[g(X)] = \sum\limits_i g(x_i) p(x_i)
$$
Thus we can show:
$$
\Large E[aX + b] = aE[X] + b
$$
where $\large a$ and $\large b$ are constants.

## Variance

For a discrete random variable $\large X$, the **variance** $\large Var(X)$ is defined as:
$$
\Large \begin{align*}
Var(X) &= E[(X - \mu)^2] \\
&= E[X^2] - \mu^2
\end{align*}
$$
where $\large \mu = E[X]$.

Thus we can show:
$$
\Large Var(aX + b) = a^2 Var(X)
$$
where $\large a$ and $\large b$ are constants.

## Standard Deviation

For a discrete random variable $\large X$, the **standard deviation** $\large SD(X)$ is defined as:
$$
\Large SD(X) = \sqrt{Var(X)}
$$

## Bernoulli Random Variable

The **Bernoulli random variable** $\large X$, corresponds to an event $\large E$ which have two possible outcomes, $\large X = 0$ and $\large X = 1$, and its probability mass function is defined as:
$$
\Large p(0) = P\{X = 0\} = 1 - p \\
\Large p(1) = P\{X = 1\} = p \\
$$
where $\large 0 \le p \le 1$.

### Properties

- $\large E[X] = p$
- $\large Var(X) = p(1 - p)$
- $\large SD(X) = \sqrt{p(1 - p)}$

## Binomial Random Variable

The **Binomial random variable** $\large X$, denotes the total number of times that event $\large E$ occurs when we repeat the Bernoulli experiment $\large n$ independent times, and its probability mass function is defined as:
$$
\Large p(i) = \binom{n}{i} p^i (1 - p)^{n - i}
$$
where $\large  i = 0,\:1,\:...,\: n$.

### Properties

- $\large E[X] = np$
- $\large Var(X) = np(1 - p)$
- $\large SD(X) = \sqrt{np(1 - p)}$

## Poisson Random Variable

The **Poisson random variable** $\large X$, denotes the total number of times that event $\large E$ occurs when we repeat the Bernoulli experiment continuously during a period of time, and its probability mass function is defined as:
$$
\Large p(i) = e^{-\lambda} \frac{\lambda ^ i}{i!}
$$
where $\large \lambda$ is the expected value of the outcome in the given period of time.

### Properties

- $\large E[X] = \lambda$
- $\large Var(X) = \lambda$
- $\large SD(X) = \sqrt{\lambda}$

## Geometric Random Variable

**Geometric distribution** is the probability distribution of the **geometric random variable** $\large X$ that denotes the total number of times we have to repeat the Bernoulli experiment until event $\large E$ occurs, and its probability mass function is defined as:
$$
\Large p(n) = P\{X = n\} = (1 - p)^{n - 1}p
$$

### Properties

- $\large E[X] = \frac{1}{p}$
- $\large Var(X) = \frac{1 - p}{p^2}$
- $\large SD(X) = \frac{\sqrt{1 - p}}{p}$

## Negative Binomial Random Variable

**Negative binomial distribution** is the probability distribution of the **negative binomial random variable** $\large X$ that denotes the total number of times we have to repeat the Bernoulli experiment until event $\large E$ occurs $\large r$ times, and its probability mass function is defined as:
$$
\Large p(n) = P\{X = n\} = \binom{n - 1}{r - 1} p^r (1 - p)^{n - r}
$$

### Properties

- $\large E[X] = \frac{r}{p}$
- $\large Var(X) = \frac{r(1 - p)}{p^2}$
- $\large SD(X) = \frac{\sqrt{r(1 - p)}}{p}$

## Hypergeometric Random Variable

Consider $\large N$ items numbered $\large 1,\:2\:...,\:N$ and that $\large n$ items where chosen at random from the $\large N$ items. Then, **hypergeometric distribution** is the probability distribution of the **hypergeometric random variable** $\large X$ that denotes the total number of times we choose chose items that are numbered $\large 1,\:2\:...,\:m$, where $\large m < n$, and its probability mass function is defined as:

$$
\Large p(n) = P\{X = i\} = \frac{\binom{m}{i} \binom{N - m}{n - i}}{\binom{N}{n}}
$$

### Properties

- $\large E[X] = \frac{nm}{N}$
- $\large Var(X) = \frac{N - n}{N - 1} np(1 - p)$
- $\large SD(X) = \sqrt{\frac{N - n}{N - 1} np(1 - p)}$