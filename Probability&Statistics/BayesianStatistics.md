# Bayesian Statistics

## Bayesian Update Table

### Discrete Probability

The **Bayesian Update Table** can be constructed for events with discrete probability as follows:

Hypothesis | Prior | Likelihood | Bayes numerator  | Posterior
--- | --- | --- | --- | ---
$\Large \mathcal{H}_i$ | $\Large P(\mathcal{H}_i)$ | $\Large P(\mathcal{D} \textbar \mathcal{H}_i)$ | $\Large P(\mathcal{D} \textbar \mathcal{H}_i) P(\mathcal{H}_i)$ | $\Large P(\mathcal{H}_i \textbar \mathcal{D}) \\[5pt] \Large = \frac{P(\mathcal{D} \textbar \mathcal{H}_i) P(\mathcal{H}_i)}{P(\mathcal{D})}$ 
... | ... | ... | ... | ...
Total | | | $\Large P(\mathcal{D}) \\[5pt] \Large = \sum\limits_i P(\mathcal{D} \textbar \mathcal{H}_i) P(\mathcal{H}_i)$ |

where $\large \mathcal{H}_i$ are the hypotheses and $\large \mathcal{D}$ is the data.

### Continuous Probability

The **Bayesian Update Table** can be constructed for events with continuous probability as follows:

Hypothesis | Prior | Likelihood | Bayes numerator  | Posterior
--- | --- | --- | --- | ---
$\Large \theta$ | $\Large f(\theta) d\theta$ | $\Large f(x \textbar \theta)$ | $\Large f(x \textbar \theta) f(\theta) d\theta$ | $\Large f(x \textbar \theta) d\theta \\[5pt] = \Large \frac{f(x \textbar \theta) f(\theta) d\theta}{f(x)}$ 
Total | | | $\Large f(x) \\[5pt] \Large = \int f(x \textbar \theta) f(\theta) d\theta$ |

where $\large \theta$ is the probability of the hypothesis.