# Hypothesis Testing

In **null hypothesis significant testing**, we are testing the validity of a claim  about a population against a counter claim using sample data.

**Null Hypothesis, $\large H_0$:** A hypothesis claiming no difference between sample and population

**Alternative Hypothesis, $\large H_A$:** A hypothesis contradicting $\large H_0$, which is usually what we're trying to prove.

&nbsp; | Do Not Reject $\large H_0$ | Reject $\large H_0$
--- | --- | ---
$\large H_0$ is True | Correct Decision (True Negative) | Type I Error (False Positive)
$\large H_0$ is False | Type II Error (False Negative) | Correct Decision (True Positive) 

**Test Statistic, $\large T$:** A statistic used to test our hypothesis.

**Significance Level, $\large \alpha$:** Probability threshold of rejection of $\large H_0$. This is the probability of getting a type I error.

**$\large p$-value:** The probability of observing a statistic as extreme or more extreme than the one observed under the assumption that $\large H_0$ is true.

**Power of the Test:** Probability of rejecting $\large H_0$ when $\large H_A$ is true.
$$
\Large \begin{align*}
\alpha &= p(\text{reject} \: H_0 | H_0) \\[5pt]
&= p(\text{Type I Error}) \\[5pt]
&= p(\text{False Positive})
\end{align*}
$$

$$
\Large \begin{align*}
1 - \alpha &= p(\text{do not reject} \: H_0 | H_A) \\[5pt]
&= p(\text{True Negative})
\end{align*}
$$

$$
\Large \begin{align*}
\beta &= p(\text{do not reject} \: H_0 | H_A) \\[5pt]
&= p(\text{Type II Error}) \\[5pt]
&= p(\text{False Negative})
\end{align*}
$$

$$
\Large \begin{align*}
1 - \beta &= p(\text{reject} \: H_0 | H_A) \\[5pt]
&= p(\text{True Positive}) \\[5pt]
&= \text{Power of the Test}
\end{align*}
$$

## $z$-Test

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu$ is unknown, $\Large \sigma^2$ is known

### Null Hypothesis

$$
\Large H_0 : \mu = \mu_0
$$

### Alternative Hypothesis

$$
\Large H_A : \mu \gt \mu_0, \: \mu \lt \mu_0, \: \text{or} \: \mu \neq \mu_0
$$

### Test Statistic

$$
\Large z = \frac{\bar{x} - \mu_0}{\sigma / \sqrt{n}}
$$

### Null Distribution

$$
\Large \text{Standard Normal Distribution:} \\
\Large Z \sim N(0, 1)
$$

### p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Left-tailed | $\Large P\{Z \le z\}$ | $\large \texttt{scipy.stats.norm.cdf(z, 0, 1)}$ | $\large \texttt{pnorm(z, 0, 1)}$
Right-tailed | $\Large P\{Z \ge z\}$ | $\large \texttt{1 - scipy.stats.norm.cdf(z, 0, 1)}$ | $\large \texttt{1 - pnorm(z, 0, 1)}$
Two-tailed | $\Large P\{\abs{Z} \ge \abs{z}\}$ | $\large \texttt{2 * (1 - scipy.stats.norm.cdf(abs(z), 0, 1))}$ | $\large \texttt{2 * (1 - pnorm(abs(z), 0, 1))}$

## $z$-Test: Two Samples

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$ and $\Large y_1, y_2, ..., y_m$
- $\Large x_i \sim N(\mu_x, \sigma_x^2)$, $\Large y_i \sim N(\mu_y, \sigma_y^2)$
- $\Large \mu_x, \mu_y$ are unknown, $\Large \sigma_x^2, \sigma_y^2$ are known

### Null Hypothesis

$$
\Large H_0 : \mu_x - \mu_y = \mu_0
$$

### Alternative Hypothesis

$$
\Large H_A : \mu_x - \mu_y \gt \mu_0, \: \mu_x - \mu_y \lt \mu_0, \: \text{or} \: \mu_x - \mu_y \neq \mu_0
$$

### Test Statistic

$$
\Large z = \frac{\bar{x} - \bar{y} - \mu_0}{\sigma_p}
$$

where $\large \sigma_p^2$ is the pooled population variance:
$$
\Large \sigma_p^2 = \frac{\sigma_x^2}{n} + \frac{\sigma_y^2}{m}
$$

### Null Distribution

$$
\Large \text{Standard Normal Distribution:} \\
\Large Z \sim N(0, 1)
$$

### p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Left-tailed | $\Large P\{Z \le z\}$ | $\large \texttt{scipy.stats.norm.cdf(z, 0, 1)}$ | $\large \texttt{pnorm(z, 0, 1)}$
Right-tailed | $\Large P\{Z \ge z\}$ | $\large \texttt{1 - scipy.stats.norm.cdf(z, 0, 1)}$ | $\large \texttt{1 - pnorm(z, 0, 1)}$
Two-tailed | $\Large P\{\abs{Z} \ge \abs{z}\}$ | $\large \texttt{2 * (1 - scipy.stats.norm.cdf(abs(z), 0, 1))}$ | $\large \texttt{2 * (1 - pnorm(abs(z), 0, 1))}$

## $t$-Test

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu, \sigma^2$ are unknown

### Null Hypothesis

$$
\Large H_0 : \mu = \mu_0
$$

### Alternative Hypothesis

$$
\Large  H_A : \mu \gt \mu_0, \: \mu \lt \mu_0, \: \text{or} \: \mu \neq \mu_0
$$

### Test Statistic

$$
\Large t = \frac{\bar{x} - \mu_0}{s / \sqrt{n}}
$$

### Null Distribution

$$
\Large \text{t-Distribution}: \\
\Large T \sim t(n - 1)
$$

###  p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Left-tailed | $\Large P\{T \le t\}$ | $\large \texttt{scipy.stats.t.cdf(t, n - 1)}$ | $\large \texttt{pt(t, n - 1)}$
Right-tailed | $\Large P\{T \ge t\}$ | $\large \texttt{1 - scipy.stats.t.cdf(t, n - 1)}$ | $\large \texttt{1 - pt(t, n - 1)}$
Two-tailed | $\Large P\{\abs{T} \ge \abs{t}\}$ | $\large \texttt{2 * (1 - scipy.stats.t.cdf(abs(t), n - 1))}$ | $\large \texttt{2 * (1 - pt(abs(t), n - 1))}$

## $t$-Test: Two Samples with Equal Variances

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$ and $\Large y_1, y_2, ..., y_m$
- $\Large x_i \sim N(\mu_x, \sigma^2)$, $\Large y_i \sim N(\mu_y, \sigma^2)$
- $\Large \mu_x, \mu_y, \sigma^2$ are unknown

### Null Hypothesis

$$
\Large H_0 : \mu_x - \mu_y = \mu_0
$$

### Alternative Hypothesis

$$
\Large H_A : \mu_x - \mu_y \gt \mu_0, \: \mu_x - \mu_y \lt \mu_0, \: \text{or} \: \mu_x - \mu_y \neq \mu_0
$$

### Test Statistic

$$
\Large t = \frac{\bar{x} - \bar{y} - \mu_0}{s_p \sqrt{\frac{1}{n} + \frac{1}{m}}}
$$

where $\large s_p^2$ is the pooled sample variance:
$$
\Large s_p^2 = \frac{(n - 1)s^2_x + (m - 1)s^2_y}{n + m - 2}
$$

### Null Distribution

$$
\Large \text{t-Distribution}: \\
\Large T \sim t(n + m - 2)
$$

###  p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Left-tailed | $\Large P\{T \le t\}$ | $\large \texttt{scipy.stats.t.cdf(t, n + m - 2)}$ | $\large \texttt{pt(t, n + m - 2)}$
Right-tailed | $\Large P\{T \ge t\}$ | $\large \texttt{1 - scipy.stats.t.cdf(t, n + m - 2)}$ | $\large \texttt{1 - pt(t, n + m - 2)}$
Two-tailed | $\Large P\{\abs{T} \ge \abs{t}\}$ | $\large \texttt{2 * (1 - scipy.stats.t.cdf(abs(t), n + m - 2))}$ | $\large \texttt{2 * (1 - pt(abs(t), n + m - 2))}$

## $t$-Test: Two Samples with Unequal Variances

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$ and $\Large y_1, y_2, ..., y_m$
- $\Large x_i \sim N(\mu_x, \sigma_x^2)$, $\Large y_i \sim N(\mu_y, \sigma_y^2)$
- $\Large \mu_x, \mu_y, \sigma_x^2, \sigma_y^2$ are unknown

### Null Hypothesis

$$
\Large H_0 : \mu_x - \mu_y = \mu_0
$$

### Alternative Hypothesis

$$
\Large H_A : \mu_x - \mu_y \gt \mu_0, \: \mu_x - \mu_y \lt \mu_0, \: \text{or} \: \mu_x - \mu_y \neq \mu_0
$$

### Test Statistic

$$
\Large t = \frac{\bar{x} - \bar{y} - \mu_0}{s_p \sqrt{\frac{1}{n} + \frac{1}{m}}}
$$

where $\large s_p^2$ is the pooled sample variance:
$$
\Large s_p^2 = s^2_x + s^2_y
$$

### Null Distribution

$$
\Large t\text{-Distribution}: \\
\Large T \sim t(df)
$$

where $\large df$ is the degrees of freedom, defined by,
$$
\Large df = \Bigg\lfloor \frac{(s_x^2 / n + s_y^2 / m)^2}{(s_x^2 / n)^2 / (n - 1) + (s_y^2 / m)^2 / (m - 1)} \Bigg\rceil
$$
where $\large \lfloor a \rceil$ is the nearest integer of $\large a$.

Test Type | p-value | Python | R
--- | --- | --- | ---
Left-tailed | $\Large P\{T \le t\}$ | $\large \texttt{scipy.stats.t.cdf(t, df)}$ | $\large \texttt{pt(t, df)}$
Right-tailed | $\Large P\{T \ge t\}$ | $\large \texttt{1 - scipy.stats.t.cdf(t, df)}$ | $\large \texttt{1 - pt(t, df)}$
Two-tailed | $\Large P\{\abs{T} \ge \abs{t}\}$ | $\large \texttt{2 * (1 - scipy.stats.t.cdf(abs(t), df))}$ | $\large \texttt{2 * (1 - pt(abs(t), df))}$

## $F$-Test for Equal Means (One Way ANOVA)

### Setup & Assumptions

- Samples: $\large n$ sets of $\large m$ samples, $\Large x_{ij}; \: i = 1, 2, ..., n; \: j = 1, 2, ..., m$
- $\Large x_{ij} \sim N(\mu_i, \sigma^2)$
- $\Large \mu_i, \sigma^2$ are unknown

### Null Hypothesis

$$
\Large H_0 : \mu_1 = \mu_2 = \: ... = \mu_n
$$

### Alternative Hypothesis

$$
\Large H_A : \mu_i \neq \mu_j \: \text{for some} \: i, j
$$

### Test Statistic

$$
\Large v = \frac{MS_b}{MS_w}
$$

where,
$$
\Large \text{Mean Squared Sum Within Sets}, \: MS_w \\[5pt]
\Large = \frac{SS_w}{n(m - 1)} \\[15pt]
\Large \text{Mean Squared Sum Between Sets}, \: MS_b \\[5pt]
\Large = \frac{SS_b}{n - 1} \\[15pt]
\Large \text{Squared Sum Within Sets}, \: SS_w \\[5pt]
\Large = \sum\limits^n_{i = 1} \sum\limits^m_{j = 1} (x_{ij} - \bar{x_i})^2 = \sum\limits^n_{i = 1}(m - 1) s_i^2 \\[15pt]
\Large \text{Squared Sum Between Sets}, \: SS_b \\[5pt]
\Large = \sum\limits^n_{i = 1} m(\bar{x_i} - \bar{x})^2
$$

### Null Distribution

$$
\Large F\text{-Distribution}: \\
\Large V \sim F(n - 1, \: n(m - 1))
$$

Test Type | p-value | Python | R
--- | --- | --- | ---
Right-tailed | $\Large P\{V \ge v\}$ | $\large \texttt{1 - scipy.stats.f.cdf(v, n - 1, n * (m - 1))}$ | $\large \texttt{1 - pf(v, n - 1, n * (m - 1))}$

## $F$-Test for Equal Variances

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$ and $\Large y_1, y_2, ..., y_m$
- $\Large x_i \sim N(\mu_x, \sigma_x^2)$, $\Large y_i \sim N(\mu_y, \sigma_y^2)$
- $\Large \mu_x, \mu_y, \sigma_x^2, \sigma_y^2$ are unknown

### Null Hypothesis

$$
\Large H_0 : \sigma_x =  \sigma_y
$$

### Alternative Hypothesis

$$
\Large H_A : \sigma_x \gt \sigma_y, \: \sigma_x \lt \sigma_y \: \text{or} \: \sigma_x \neq \sigma_y
$$

### Test Statistic

$$
\Large v = \frac{s_x^2}{s_y^2}
$$

### Null Distribution

$$
\Large F\text{-Distribution}: \\
\Large V \sim F(n - 1, m - 1)
$$

### p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Left-tailed | $\Large P\{V \le v\}$ | $\large \texttt{scipy.stats.f.cdf(v, n - 1, m - 1)}$ | $\large \texttt{pf(v, n - 1, m - 1)}$
Right-tailed | $\Large P\{V \ge v\}$ | $\large \texttt{1 - scipy.stats.f.cdf(v, n - 1, m - 1)}$ | $\large \texttt{1 - pf(v, n - 1, m - 1)}$
Two-tailed | $\Large P\{\abs{V} \ge \abs{v}\}$ | $\large \texttt{2 * min(1 - scipy.stats.f.cdf(v, n - 1, m - 1), scipy.stats.f.cdf(v, n - 1, m - 1))}$ | $\large \texttt{2 * min(1 - pf(v, n - 1, m - 1), pf(v, n - 1, m - 1))}$

## $\chi^2$-Test for Variance

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu, \sigma^2$ are unknown

### Null Hypothesis

$$
\Large H_0 : \sigma =  \sigma_0
$$

### Alternative Hypothesis

$$
\Large H_A : \sigma \gt \sigma_0, \: \sigma \lt \sigma_0 \: \text{or} \: \sigma \neq \sigma_0
$$

### Test Statistic

$$
\Large u = \frac{(n - 1) s^2}{\sigma_0^2}
$$

### Null Distribution

$$
\Large \chi^2\text{-Distribution}: \\
\Large U \sim \chi^2(n - 1)
$$

### p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Left-tailed | $\Large P\{U \le u\}$ | $\large \texttt{scipy.stats.chi2.cdf(u, n - 1)}$ | $\large \texttt{pchisq(u, n - 1)}$
Right-tailed | $\Large P\{U \ge u\}$ | $\large \texttt{1 - scipy.stats.chi2.cdf(u, n - 1)}$ | $\large \texttt{1 - pchisq(u, n - 1)}$
Two-tailed | $\Large P\{\abs{U} \ge \abs{u}\}$ | $\large \texttt{2 * min(1 - scipy.stats.chi2.cdf(u, n - 1), scipy.stats.chi2.cdf(u, n - 1))}$ | $\large \texttt{2 * min(1 - pchisq(u, n - 1), pchisq(u, n - 1))}$

## $\chi^2$-Test for Goodness of Fit: Single Specific Distribution

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$, where $\Large x_i \in \{\omega_1, \omega_2, ..., \omega_K\}$
- Distribution: $\Large \{p_i\}^K_{i = 1}$
- Frequency: $\Large O_1, O_2, ..., O_K$, where $\Large O_i$ is the number of occurrences of $\Large \omega_i$ in the sample $\Large x_1, x_2, ..., x_n$, which means $\Large O_1 + O_2 + ... + O_K = n$

### Null Hypothesis

$$
\Large H_0 : x_i \: \text{follows distribution} \: \{p_i\}^K_{i = 1}
$$

### Alternative Hypothesis

$$
\Large H_A : x_i \: \text{does not follow distribution} \: \{p_i\}^K_{i = 1}
$$

### Test Statistic

$$
\Large u = \sum\limits^K_{i = 1} \frac{(O_i - n p_i)^2}{n p_i}
$$

### Null Distribution

$$
\Large \chi^2\text{-Distribution}: \\
\Large U \sim \chi^2(K - 1)
$$

### p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Right-tailed | $\Large P\{U \ge u\}$ | $\large \texttt{1 - scipy.stats.chi2.cdf(u, K - 1)}$ | $\large \texttt{1 - pchisq(u, K - 1)}$

## $\chi^2$-Test for Goodness of Fit: Statistical Model

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$, where $\Large x_i \in \{\omega_1, \omega_2, ..., \omega_K\}$
- Statistical Model: $\Large \{(p_1(\theta), p_2(\theta), ..., p_K(\theta)) : \theta \in \Theta\}$
- Frequency: $\Large O_1, O_2, ..., O_K$, where $\Large O_i$ is the number of occurrences of $\Large \omega_i$ in the sample $\Large x_1, x_2, ..., x_n$, which means $\Large O_1 + O_2 + ... + O_K = n$

### Null Hypothesis

$$
\Large H_0 : x_i \: \text{follows model} \: \{(p_1(\theta), p_2(\theta), ..., p_K(\theta)) : \theta \in \Theta\}
$$

### Alternative Hypothesis

$$
\Large H_A : x_i \: \text{does not follow model} \: \{(p_1(\theta), p_2(\theta), ..., p_K(\theta)) : \theta \in \Theta\}
$$

### Test Statistic

$$
\Large u = \sum\limits^K_{i = 1} \frac{(O_i - n p_i(\hat{\theta}))^2}{n p_i(\hat{\theta})}
$$

where $\large \hat{\theta}$ is the maximum likelihood estimate of $\large \theta$ under $\large H_0$.

### Null Distribution

$$
\Large \chi^2\text{-Distribution}: \\
\Large U \sim \chi^2(K - 1 - dim(\Theta))
$$

where $\large dim(\Theta)$ is the dimension of the parameter space $\large \Theta$.

### p-Value

Test Type | p-value | Python | R
--- | --- | --- | ---
Right-tailed | $\Large P\{U \ge u\}$ | $\large \texttt{1 - scipy.stats.chi2.cdf(u, K - 1 - dim)}$ | $\large \texttt{1 - pchisq(u, K - 1 - dim)}$