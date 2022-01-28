# Regression

## Simple Linear Regression

Given dependent variable $\large y_i$ and independent variable $\large x_i$, **simple linear regression** involves the computation of a linear model that predicts $\large y$:
$$
\Large \hat{y}_i = \beta_0 + \beta_1 x \\[15pt]
\Large y_i = \beta_0 + \beta_1 x_i + \epsilon_i \\[5pt]
\Large = \hat{y}_i + \epsilon_i
$$
where,
$$
\Large \begin{align*}
\beta_1 &= \frac{\sum{(x_i - \bar{x})(y_i - \bar{y})}}{\sum{(x_i - \bar{x})^2}} \\[10pt]
&= \frac{n\sum{x_i y_i} - \sum{x_i}\sum{y_i}}{n\sum{x_i^2} - (\sum{x_i})^2}
\end{align*} \\[25pt]
\Large \beta_0 = \bar{y} - \beta_1 \bar{x}
$$

### Goodness of Fit

$$
\Large \text{Sum of Squares Total (SST)} \\[5pt]
\huge = \sum\limits^n_{i = 1}{(y_i - \bar{y})^2} \\[15pt]
\Large \text{Sum of Squares Regression (SSR)} \\[5pt]
\huge = \sum\limits^n_{i = 1}{(\hat{y_i} - \bar{y})^2} \\[15pt]
\Large \text{Sum of Squares Error (SSE)} \\[5pt]
\huge = \sum\limits^n_{i = 1}{(y_i - \hat{y}_i)^2} \\[25pt]
\Large SST = SSR + SSE \\[15pt]
\Large R^2 = \frac{SSR}{SST}
$$

## Multiple Linear Regression

Given dependent variable $\large y_i$ and $\large k$ independent variables $\large x_i$, **multiple linear regression** involves the computation of a linear model that predicts $\large y$:
$$
\Large \hat{y}_i = \beta_0 + \beta_1 x_{i, 1} + \beta_2 x_{i, 2} + ... + \beta_k x_{i, k} \\[15pt]
\Large y_i = \beta_0 + \beta_1 x_{i, 1} + \beta_2 x_{i, 2} + ... + \beta_k x_{i, k} + \epsilon_i \\[5pt]
\Large = \hat{y}_i + \epsilon_i
$$

### Goodness of Fit

$$
\Large R^2 = \frac{SSR}{SST} \\[10pt]
\Large \bar{R}^2 = 1 - \frac{(1 - R^2)(n - 1)}{n - k - 1}
$$

where $\large \bar{R}^2$ is the adjusted $\large R^2$.
