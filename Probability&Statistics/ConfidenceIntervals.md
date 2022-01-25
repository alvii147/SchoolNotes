# Confidence Intervals

## Definition

Given a statistical model $\large \{p(x | \theta): \theta \in \Theta\}$ and $\large 0 \ge \alpha \ge 1$, an interval statistic $\large T(x) = [l(x), u(x)]$, where $\large l(x)$ and $\large  u(x)$ are lower and upper in is a $\large (1 - \alpha)$ confidence interval for $\large \theta_i$, where $\large \theta_i$ is a component of $\large \theta$,
$$
\Large P\{\theta_i \in T(x) | \theta\} \ge 1 - \alpha
$$

## $z$-Confidence Interval

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu$ is unknown, $\Large \sigma^2$ is known

### Objective

$$
\Large \text{Estimate} \: \mu \: \text{with a} \: (1 - \alpha) \: \text{confidence interval}
$$

### Interval

$$
\huge \Big[\bar{x} - z_{\alpha / 2}\frac{\sigma}{\sqrt{n}}, \bar{x} + z_{\alpha / 2}\frac{\sigma}{\sqrt{n}}\Big]
$$

where $\large z_{\alpha / 2}$ is the right critical value such that,
$$
\Large P\{Z \ge z_{\alpha / 2}\} = \alpha / 2
$$

Parameter | Python | R
--- | --- | ---
$\Large z_{\alpha / 2}$ | $\large \texttt{scipy.stats.norm.ppf(1 - (abs(a) / 2), 0, 1)}$ | $\large \texttt{qnorm(1 - (abs(a) / 2), 0, 1)}$

## $z$-Confidence Interval with Two Independent Samples

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$ and $\Large y_1, y_2, ..., y_m$
- $\Large x_i \sim N(\mu_x, \sigma_x^2)$ amd $\Large y_i \sim N(\mu_y, \sigma_y^2)$
- $\Large \mu_x, \mu_y$ are unknown, $\Large \sigma_x^2, \sigma_y^2$ are known

### Objective

$$
\Large \text{Estimate} \: \mu_x - \mu_y \: \text{with a} \: (1 - \alpha) \: \text{confidence interval}
$$

### Interval

$$
\huge \Bigg[\bar{x} - z_{\alpha / 2} \sqrt{\frac{\sigma_x^2}{n} + \frac{\sigma_y^2}{m}}, \bar{x} + z_{\alpha / 2} \sqrt{\frac{\sigma_x^2}{n} + \frac{\sigma_y^2}{m}}\Bigg]
$$

where $\large z_{\alpha / 2}$ is the right critical value such that,
$$
\Large P\{Z \ge z_{\alpha / 2}\} = \alpha / 2
$$

Parameter | Python | R
--- | --- | ---
$\Large z_{\alpha / 2}$ | $\large \texttt{scipy.stats.norm.ppf(1 - (abs(a) / 2), 0, 1)}$ | $\large \texttt{qnorm(1 - (abs(a) / 2), 0, 1)}$

## $t$-Confidence Interval

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu, \sigma^2$ are unknown

### Objective

$$
\Large \text{Estimate} \: \mu \: \text{with a} \: (1 - \alpha) \: \text{confidence interval}
$$

### Interval

$$
\huge \Big[\bar{x} - t_{\alpha / 2}\frac{s}{\sqrt{n}}, \bar{x} + t_{\alpha / 2}\frac{s}{\sqrt{n}}\Big]
$$

where $\large t_{\alpha / 2}$ is the right critical value such that,
$$
\Large P\{T \ge t_{\alpha / 2}\} = \alpha / 2
$$

Parameter | Python | R
--- | --- | ---
$\Large t_{\alpha / 2}$ | $\large \texttt{scipy.stats.t.ppf(1 - (abs(a) / 2), n - 1)}$ | $\large \texttt{qt(1 -  (abs(a) / 2), n - 1)}$

## $t$-Confidence Interval with Two Independent Samples

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$ and $\Large y_1, y_2, ..., y_m$
- $\Large x_i \sim N(\mu_x, \sigma_x^2)$ amd $\Large y_i \sim N(\mu_y, \sigma_y^2)$
- $\Large \mu_x, \mu_y, \sigma_x^2, \sigma_y^2$ are unknown

### Objective

$$
\Large \text{Estimate} \: \mu_x - \mu_y \: \text{with a} \: (1 - \alpha) \: \text{confidence interval}
$$

### Interval

$$
\huge \Bigg[\bar{x} - t_{\alpha / 2} \sqrt{\frac{s_x^2}{n} + \frac{s_y^2}{m}}, \bar{x} + t_{\alpha / 2} \sqrt{\frac{s_x^2}{n} + \frac{s_y^2}{m}}\Bigg]
$$

where $\large t_{\alpha / 2}$ is the right critical value such that,
$$
\Large P\{T \ge t_{\alpha / 2}\} = \alpha / 2
$$

Parameter | Python | R
--- | --- | ---
$\Large t_{\alpha / 2}$ | $\large \texttt{scipy.stats.t.ppf(1 - (abs(a) / 2), n - 1)}$ | $\large \texttt{qt(1 -  (abs(a) / 2), n - 1)}$

## $\chi^2$-Confidence Interval

### Setup & Assumptions

- Samples: $\Large x_1, x_2, ..., x_n$
- $\Large x_i \sim N(\mu, \sigma^2)$
- $\Large \mu, \sigma^2$ are unknown

### Objective

$$
\Large \text{Estimate} \: \sigma^2 \: \text{with a} \: (1 - \alpha) \: \text{confidence interval}
$$

### Interval

$$
\huge \Big[\frac{(n - 1)s^2}{c_{\alpha / 2}}, \frac{(n - 1)s^2}{c_{1 - \alpha / 2}}\Big]
$$

where $\large c_{\alpha / 2}$ and $\large c_{1 - \alpha / 2}$ are the right critical values such that,
$$
\Large P\{\chi^2 \ge c_{\alpha / 2}\} = \alpha / 2 \\[5pt]
\Large \text{and} \\[5pt]
\Large P\{\chi^2 \ge c_{1 -\alpha / 2}\} = 1 - \alpha / 2
$$

respectively.

Parameter | Python | R
--- | --- | ---
$\Large c_{\alpha / 2}$ | $\large \texttt{scipy.stats.t.chi2(1 - (abs(a) / 2), n - 1)}$ | $\large \texttt{qchisq(1 - (abs(a) / 2), n - 1)}$
$\Large c_{1 - \alpha / 2}$ | $\large \texttt{scipy.stats.t.chi2(abs(a), n - 1)}$ | $\large \texttt{qchisq(abs(a), n - 1)}$