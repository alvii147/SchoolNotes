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

### Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu$ is unknown, $\Large \sigma^2$ is known

### Null Hypothesis

$$
\Large H_0: \mu = \mu_0
$$

### Alternative Hypothesis

$$
\Large H_A: \mu \gt \mu_0, \: \mu \lt \mu_0, \: \text{or} \: \mu \neq \mu_0
$$

### Test Statistic

$$
\Large z = \frac{\bar{x} - \mu_0}{\sigma / \sqrt{n}}
$$

## $z$-Test: Two Samples

### Assumptions

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

## $t$-Test

### Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu, \sigma^2$ are unknown

### Null Hypothesis

$$
\Large H_0: \mu = \mu_0
$$

### Alternative Hypothesis

$$
\Large  H_A: \mu \gt \mu_0, \: \mu \lt \mu_0, \: \text{or} \: \mu \neq \mu_0
$$

### Test Statistic

$$
\Large t = \frac{\bar{x} - \mu_0}{s / \sqrt{n}}
$$

## $t$-Test: Two Samples with Equal Variances

### Assumptions

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
\Large t = \frac{\bar{x} - \bar{y} - \mu_0}{s_p}
$$

where $\large s_p^2$ is the pooled sample variance:
$$
\Large s_p^2 = \frac{(n - 1)s^2_x + (m - 1)s^2_y}{n + m - 2} \times \Big(\frac{1}{n} + \frac{1}{m}\Big)
$$

## $t$-Test: Two Samples with Unequal Variances

### Assumptions

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
\Large t = \frac{\bar{x} - \bar{y} - \mu_0}{s_p}
$$

where $\large s_p^2$ is the pooled sample variance:
$$
\Large s_p^2 = \frac{s^2_x}{n} + \frac{s^2_y}{m}
$$
