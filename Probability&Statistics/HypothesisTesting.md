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

