# Continuous Random Variables

Let $\large S$ be the sample space associated with some experiment $\large E$. A **random variable** $\large X$ is a function that assigns a real number $\large X(s)$ to each elementary event $\large s \in S$. In this case, as the outcome of the experiment, i.e. the specific $\large s$, is not predetermined, then the value of $\large X(s)$ is not fixed. This means that the value of the random variable is determined by the specific outcome of the experiment.

A **continuous random variable** can take an uncountably infinite number of values.

## Probability Density Function

For a continuous random variable $\large X$, the **probability density function** $\large f$ is a non-negative function defined for all real $\large x \in (-\infty, \infty)$, such that, for any set $\large A$:
$$
\Large P\{X \in A\} = \int\limits_A f(x) dx
$$

### Properties

- $\large P\{X \in (-\infty, \infty)\} = \int\limits_{-\infty}^{\infty}f(x)dx = 1$

## Cumulative Distribution Function

For a continuous random variable $\large X$, the **cumulative distribution function** $\large F(a)$ is defined as:
$$
\Large F(a) = P\{X \lt a\} = P\{X \le a\} = \int\limits_{-\infty}^{a}f(x)dx
$$

### Properties

- $\large a \lt b \implies \Large F(a) \le F(b)$
- $\large \lim\limits_{a \to \infty} F(a) = 1$
- $\large \lim\limits_{a \to -\infty} F(a) = 0$
- $\large \lim\limits_{n \to \infty} F(a_n) = F(a)$ for any decreasing sequence $\Large a_n$ that converges to $\large a$
- $\large P\{a \lt X \le b\} = F(b) - F(a)$

## Expected Value

For a continuous random variable $\large X$, the **expected value** $\large E[X]$ is defined as:
$$
\Large E[X] = \int\limits_{-\infty}^{\infty} x f(x) dx
$$

### Expected Value of a Function of a Continuous Random Variable

For a real-valued function $\large Y = g(X)$ of a random variable $\large X$, the expected value $\large E[Y]$ is defined as:
$$
\Large E[X] = \int\limits_{-\infty}^{\infty} g(x) f(x) dx
$$
Thus we can show:
$$
\Large E[aX + b] = aE[X] + b
$$
where $\large a$ and $\large b$ are constants.

## Variance

For a continuous random variable $\large X$, the **variance** $\large Var(X)$ is defined as:
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

For a continuous random variable $\large X$, the **standard deviation** $\large SD(X)$ is defined as:
$$
\Large SD(X) = \sqrt{Var(X)}
$$

## Uniform Random Variable

A **uniform random variable** $\large X$ is a continuous random variable that is uniform in the interval $\large (\alpha, \beta)$, and its probability density function is given by:
$$
\Large f(x) = \begin{cases}
\frac{1}{\beta - \alpha} & \text{if} \: \alpha \lt x \le \beta \\[5pt]
0 & \text{otherwise}
\end{cases}
$$
The cumulative density function $\large F(a)$ is defined as:
$$
\Large F(a) = \begin{cases}
0 & \text{if} \: a \le \alpha \\[5pt]
\frac{a - \alpha}{\beta - \alpha} & \text{if} \: \alpha \lt x \le \beta \\[5pt]
1 & a \ge \beta
\end{cases}
$$

### Properties

- $\large E[X] = \frac{\alpha + \beta}{2}$
- $\large Var(X) = \frac{(\beta - \alpha)^2}{12}$
- $\large SD(X) = \frac{\beta - \alpha}{2\sqrt{3}}$

## Normal Random Variable

A **normal random variable** $\large X$ is a continuous random variable that is **normally distributed** with parameters $\large \mu$ (mean) and $\large \sigma$ (standard deviation), denoted by $\large N(\mu, \sigma^2),$ with its probability density function is given by:
$$
\Large f(x) = \frac{1}{\sigma\sqrt{2\pi}} e^{\frac{-(x - \mu)^2}{2\sigma^2}}
$$

### Properties

- $\large E[X] = \mu$
- $\large Var(X) = \sigma^2$
- $\large SD(X) = \sigma$
- $\large X: N(\mu, \sigma^2) \: \text{and} \: Y = aX + b \implies Y : N(a\mu + b, a^2\sigma^2)$

## Standard Normal Random Variable

A **standard normal random variable** $\large X$ is a normal random variable with parameters $\large \mu = 0$ and $\large \sigma = 1$, and its probability density function is defined as:
$$
\Large f_Z(z) = \frac{1}{\sqrt{2\pi}} e^{\frac{z^2}{2}}
$$
The cumulative distribution function $\large \Phi(x)$ of a standard normal random variable is defined by:
$$
\Large \Phi(x) = \frac{1}{\sqrt{2\pi}}\int\limits^x_{-\infty}e^{\frac{-y^2}{2}}dy
$$

### Properties

- $\large X : N(\mu, \sigma^2) \implies F_X(a) = \Phi(\frac{a - \mu}{\sigma})$

## Student's t-Distribution

The **T-statistic** $\large T$ is a random variable with parameters $\large \mu$ (population mean), $\large \bar{x}$ (sample mean), $\large \sigma$ (population standard deviation), $\large S$ (sample standard deviation) and $\large n$ (degrees of freedom + 1), and is defined as:
$$
\Large T = \frac{\bar{x} - \mu}{S / \sqrt{n}}
$$
The probability distribution function of the $\large t$ distribution is given by:
$$
\Large f(t) = \frac{\Gamma(\frac{\nu + 1}{2})}{\sqrt{\nu \pi} \: \Gamma(\frac{\nu}{2})} \Big(1 + \frac{t^2}{\nu}\Big)^{-\frac{\nu + 1}{2}}
$$

### Properties

- $\large E[T] = 0$, for $\large \nu \gt 1$
- $\large Var(T) = \frac{\nu}{\nu - 2}$, for $\large \nu \gt 2$
- $\large SD(T) = \sqrt{\frac{\nu}{\nu - 2}}$, for $\large \nu \gt 2$

## Exponential Random Variable

An **exponential random variable** $\large X$ is a continuous random variable with parameter $\large \lambda$ with its probability density function defined as:
$$
\Large f(x) = \begin{cases}
\lambda e^{-\lambda x} & \text{if} \: x \ge 0 \\
0 & \text{if} \: x \lt 0 \\
\end{cases}
$$
The cumulative distribution function $\large F(a)$ is defined by:
$$
\Large F(a) = P\{X \le a \} = 1 - e^{-\lambda a}
$$

### Properties

- $\large E[X] = \frac{1}{\lambda}$
- $\large Var(X) = \frac{1}{\lambda^2}$
- $\large SD(X) = \frac{1}{\lambda}$

## Memoryless Random Variable

A **memoryless random variable** $\large X$ is one that satisfies the followings condition:
$$
\Large P\{X \gt a + b \: | \: X \gt b\} = P\{X \gt a\} \:\:\: \text{for all} \: a, b \ge 0
$$
An exponential random variable is memoryless.

## Gamma Random Variable

A **gamma random variable** $\large X$ is a continuous random variable with parameters $\large \lambda \gt 0$ and $\large \alpha \gt 0$, with the **gamma distribution** as the probability density function, defined as:
$$
\Large f(x) = \begin{cases}
\frac{\lambda e^{-\lambda x} (\lambda x)^{\alpha - 1}}{\Gamma(\alpha)} & \text{if} \: x \ge 0 \\
0 & \text{if} \: x \lt 0
\end{cases}
$$
where $\large \Gamma(\alpha)$ is the gamma function and is defined as:
$$
\Large \Gamma(\alpha) = \int\limits^\infty_0 e^{-y} y^{\alpha - 1}dy
$$

### Properties

- $\large E[X] = \frac{\alpha}{\lambda}$
- $\large Var(X) = \frac{\alpha}{\lambda^2}$
- $\large SD(X) = \frac{\sqrt{\alpha}}{\lambda}$

