# Descriptive Statistics

## Mean

The **population mean** $\large \mu$ or **sample mean** $\large \bar{x}$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge \mu = \bar{x} = \frac{\sum{x_i}}{N}
$$

**Note:** $\large \sum$ represents $\large \sum\limits^N_{i = 1}$.

## Median

The **median** of a dataset is the middle value of the sorted dataset.

- If $\large N$ is odd, the median is the middle value
- If $\large N$ is even, the median is the mean of the middle two values

## Mode

The **mode** of a dataset is the value that occurs most frequently.

- If there are multiple values that occur most frequently, they are all modes
- If all values occur at equal frequency, there is no mode

## Variance & Standard Deviation

The **variance** and **standard deviation** of a dataset are measures of the degree of variation of the data from the mean value.

### Population Variance

The **population variance** $\large \sigma^2$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge \begin{align*}
\sigma^2 &= \frac{\sum{(x_i - \mu)^2}}{N} \\[10pt]
&= \frac{\sum{x_i^2}}{N} - \mu^2
\end{align*}
$$

### Sample Variance

The **sample variance** $\large s^2$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge \begin{align*}
s^2 &= \frac{\sum{(x_i - \bar{x})^2}}{N - 1} \\[10pt]
&= \frac{\sum{x_i^2} - \frac{\Big(\sum{x_i}\Big)^2}{N}}{N - 1}
\end{align*}
$$

### Population Standard Deviation

The **population standard deviation** $\large \sigma$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge \begin{align*}
\sigma &= \sqrt{\frac{\sum{(x_i - \mu)^2}}{N}} \\[10pt]
&= \sqrt{\frac{\sum{x_i^2}}{N} - \mu^2}
\end{align*}
$$

### Sample Standard Deviation

The **sample standard deviation** $\large s$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge \begin{align*}
s &= \sqrt{\frac{\sum{(x_i - \bar{x})^2}}{N - 1}} \\[10pt]
&= \sqrt{\frac{\sum{x_i^2} - \frac{\Big(\sum{x_i}\Big)^2}{N}}{N - 1}}
\end{align*}
$$

## Skewness

The **skewness** of a dataset is a measure of its asymmetry.

### Fisher-Pearson Population Skewness

The **Fisher-Pearson population skewness** $\large \tilde{\mu}_3$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge \tilde{\mu}_3 = \frac{\frac{\sum{(x_i - \mu)^3}}{N}}{\sigma^3}
$$

### Fisher-Pearson Sample Skewness

The **Fisher-Pearson sample skewness** $\large g_1$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge g_1 = \frac{\frac{\sum{(x_i - \bar{x})^3}}{N}}{s^3}
$$

### Adjusted Fisher-Pearson Sample Skewness

The **adjusted Fisher-Pearson sample skewness** $\large G_1$ of a dataset $\large x_1, x_2, ..., x_N$ is given by:
$$
\huge G_1 = \frac{\sqrt{N(N - 1)}}{N - 2} \times \frac{\frac{\sum{(x_i - \bar{x})^3}}{N}}{s^3}
$$

## Covariance & Correlation

The **covariance** and **correlation coefficient** of two datasets are measures of linear relationship between the datasets.

### Population Covariance

The **population covariance** $\large \sigma_{xy}$ of datasets $\large x_1, x_2, ..., x_N$ and $\large y_1, y_2, ..., y_N$ is given by:
$$
\huge \sigma_{xy} \frac{\sum{(x_i - \mu_x)(y_i - \mu_y)}}{N}
$$

### Sample Covariance

The **sample covariance** $\large s_{xy}$ of datasets $\large x_1, x_2, ..., x_N$ and $\large y_1, y_2, ..., y_N$ is given by:
$$
\huge s_{xy} \frac{\sum{(x_i - \bar{x})(y_i - \bar{y})}}{N - 1}
$$

### Pearson Correlation Coefficient

The **Pearson correlation coefficient** $\large r_{xy}$ of datasets $\large x_1, x_2, ..., x_N$ and $\large y_1, y_2, ..., y_N$ is given by:
$$
\huge r_{xy} = \frac{\sigma_{xy}}{\sigma_x \sigma_x} = \frac{s_{xy}}{s_x s_x}
$$
