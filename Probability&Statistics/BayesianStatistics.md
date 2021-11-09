# Bayesian Statistics

## Bayesian Update Table

### Discrete Probability

A **Bayesian Update Table** can be constructed for events with discrete probability as follows:

Hypothesis | Prior | Likelihood | Bayes numerator  | Posterior
--- | --- | --- | --- | ---
$\Large \mathcal{H}_i$ | $\Large P(\mathcal{H}_i)$ | $\Large P(\mathcal{D} \textbar \mathcal{H}_i)$ | $\Large P(\mathcal{D} \textbar \mathcal{H}_i) P(\mathcal{H}_i)$ | $\Large P(\mathcal{H}_i \textbar \mathcal{D}) = \frac{P(\mathcal{D} \textbar \mathcal{H}_i) P(\mathcal{H}_i)}{P(\mathcal{D})}$ 
... | ... | ... | ... | ...
Total | | | $\Large P(\mathcal{D}) = \sum\limits_i P(\mathcal{D} \textbar \mathcal{H}_i) P(\mathcal{H}_i)$ |

where $\Large \mathcal{H}_i$ are the hypotheses and $\Large \mathcal{D}$ is the data.

### Continuous Probability

A Bayesian Update Table can be constructed for events with continuous probability as follows:

Hypothesis | Prior | Likelihood | Bayes numerator  | Posterior
--- | --- | --- | --- | ---
$\Large \theta$ | $\Large f(\theta) d\theta$ | $\Large f(x \textbar \theta)$ | $\Large f(x \textbar \theta) f(\theta) d\theta$ | $\Large f(\theta \textbar x) = \frac{f(x \textbar \theta) f(\theta) d\theta}{f(x)}$ 
Total | | | $\Large f(x) = \int f(x \textbar \theta) f(\theta) d\theta$ |

where $\Large \theta$ is the probability of the hypothesis.

### Beta Distribution Priors

A Bayesian Update Table can be constructed for events with **Beta distribution** priors as follows:

Distribution Types (Prior/Likelihood) | Hypothesis | Prior | Likelihood | Bayes numerator  | Posterior
--- | --- | --- | --- | --- | ---
Beta/Bernoulli (on success) | $\Large \theta \in [0, 1]$ | $\Large Beta(a, b) d\theta$ | $\Large \theta$ | $\Large \theta \times Beta(a, b) d\theta$ | $\Large Beta(a + 1, b)$
Beta/Bernoulli (on failure) | $\Large \theta \in [0, 1]$ | $\Large Beta(a, b) d\theta$ | $\Large (1 - \theta)$ | $\Large (1 - \theta) \times Beta(a, b) d\theta$ | $\Large Beta(a, b + 1)$
Beta/Binomial | $\Large \theta \in [0, 1]$ | $\Large Beta(a, b) d\theta$ | $\Large \binom{n}{x} \theta^n (1 - \theta)^{n - x}$ | $\Large \binom{n}{x} \theta^n (1 - \theta)^{n - x} \times Beta(a, b) d\theta$ | $\Large Beta(a + x, b + n - x)$ 
Beta/Geometric | $\Large \theta \in [0, 1]$ | $\Large Beta(a, b) d\theta$ | $\Large \theta^x(1 - \theta)$ | $\Large \theta^x(1 - \theta) \times Beta(a, b) d\theta$ | $\Large Beta(a + x, b + 1)$

where the Beta distribution is given as follows:
$$
\Large Beta(a, b) = \frac{(a + b - 1)!}{(a - 1)! (b - 1)!} \theta^{a - 1} (1 - \theta)^{b - 1}
$$

#### Properties

- $\large E[X] = \frac{a}{a + b}$
- $\large Var[X] = \frac{ab}{(a + b + 1)(a + b)^2}$
- $\large SD[X] = \frac{\sqrt{ab}}{(a + b)\sqrt{(a + b + 1)}}$

### Normal Distribution Priors & Likelihoods

A Bayesian Update Table can be constructed for events with normal distribution priors and likelihoods as follows:

Distribution Types (Prior/Likelihood) | Hypothesis | Prior | Likelihood | Bayes numerator  | Posterior
--- | --- | --- | --- | --- | ---
Normal/Normal | $\Large \theta \in (-\infty, \infty)$ | $\Large N(\mu_{prior}, \sigma^2_{prior}) d\theta$ | $\Large N(\theta, \sigma^2)$ | $\Large  N(a, b) \times N(\theta, \sigma^2) d\theta$ | $\Large N(\mu_{post}, \sigma^2_{post})$

where $\Large \bar{x}$ is the mean of the data points, $\Large n$ is the number of data points, and:
$$
\Large a = \frac{1}{\sigma^2_{prior}}, \:\: b = \frac{n}{\sigma^2} \\[20pt]
\Large \mu_{post} = \frac{a \mu_{prior} + b \bar{x}}{a + b}, \:\:\: \sigma^2_{post} = \frac{1}{a + b}
$$