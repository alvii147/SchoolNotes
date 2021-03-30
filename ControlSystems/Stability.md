# Stability

Consider a system with transfer function $H(s)$ such that,
$$
\Large H(s) = \frac{N(s)}{D(s)}
$$
where
$$
\Large \begin{align*}
D(s) &= s^n + a_{n-1}s^{n-1} +\:...\:+ a_1s + a_0 \\[5pt]
&=(s + p_1)(s + p_2)\:...\:(s + p_n)
\end{align*}
$$
The system is stable if and only if all roots of $D(s)$, $(p_1,p_2\:...\:p_n)$ are in the open left half plane. In order words,
$$
\Large Re(p_i) < 0, \:\: \text{for all} \:\: 0 \lt i \le n
$$

## Necessary Condition for Stability

A system defined by transfer function $H(s)$ is stable only if all coefficients of $D(s)$, $(a_0,a_1\:...\:a_{n-1})$ are positive. In other words, if
$$
\Large H(s) = \frac{N(s)}{D(s)}
$$
and
$$
\Large \begin{align*}
D(s) &= s^n + a_{n-1}s^{n-1} +\:...\:+ a_1s + a_0 \\[5pt]
&=(s + p_1)(s + p_2)\:...\:(s + p_n)
\end{align*}
$$
Then,
$$
\Large a_i > 0 \:\: \text{for all} \:\: 0 \lt i \le n \implies \text{the system is stable}
$$

## Routh-Hurwitz Test

For a system with $D(s)$ such that,
$$
\Large D(s) = s^n + a_{n-1}s^{n-1} +\:...\:+ a_1s + a_0
$$
We can construct a Routh array:

$\Large s^n$ | $\Large a^n$ | $\Large a^{n - 2}$ | $\Large a^{n - 4}$
--- | --- | --- | ---
$\Large s_{n - 1}$ | $\Large a_{n - 1}$ | $\Large a_{n - 3}$ | $\Large a_{n - 5}$
$\Large s_{n - 2}$ | $\Large b_1$ | $\Large b_2$ | $\Large b_3$
$\Large s_{n - 3}$ | $\Large c_1$ | $\Large c_2$ | $\Large c_3$
... | ... | ... | ...
$\Large s^2$ | ... | ... | ... | ...
$\Large s$ | ... | ... | ... | ...
$\Large 1$ | ... | ... | ... | ...

where

$$
\Large b_i = \frac{1}{a_{n - 1}}(a_{n - 1}a_{n - i - 1} - a_na_{n - 2i - 1}) \\[20pt]
\Large c_i = \frac{1}{b_1}(b_1a_{n - i - 2} - a_{n - 1}b_{i + 1})
$$