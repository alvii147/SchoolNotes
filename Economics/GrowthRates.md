# Growth Rates

## Growth Rate

The growth rate $\large g_t$ of a variable $\large X$ at time $\large t$ is given by,
$$
\Large g_t = \frac{X_t - X_{t - 1}}{X_{t - 1}}
$$
This means the ratio of consecutive terms is given by,
$$
\Large 1 + g_t = \frac{X_t}{X_{t - 1}}
$$

## Growth Rate of Product

The growth rate $\large g_t$ of the product of variables $\large X$ and $\large Y$ at time $\large t$ is given by,
$$
\Large g_t = \frac{X_t Y_t - X_{t - 1} Y_{t - 1}}{X_{t - 1} Y_{t - 1}} = (1 + g_x)(1 + g_y) - 1 \approx g_x + g_y
$$

## Annualized Growth Rate

The annualized growth rate $\large g_t$ of a variable $\large X$ at time $\large t$ is given by,
$$
\Large g_t = \Bigg(1 + \frac{X_t - X_{t - 1}}{X_{t - 1}}\Bigg)^{n} - 1 \approx n\Bigg(1 + \frac{X_t - X_{t - 1}}{X_{t - 1}}\Bigg)
$$
where $\large n$ is the number of samples per year.

For monthly data, $\large n = 12$.

For quarterly data, $\large n = 4$.

## Logarithm & Growth Rate

The growth rate $\large g_t$ of a variable $\large X$ at time $\large t$ is related to the natural logarithm of the variable:
$$
\Large \text{log}(X_t) - \text{log}(X_{t - 1}) = \text{log}(1 + g_t) \approx g_t
$$
The growth rate $\large g_t$ of the product of variables $\large X$ and $\large Y$ at time $\large t$ is related to the natural logarithm of the variable:
$$
\Large \text{log}(X_t Y_t) - \text{log}(X_{t - 1} Y_{t - 1}) = \text{log}(1 + g_x) + \text{log}(1 + g_y) \approx g_x + g_y
$$
