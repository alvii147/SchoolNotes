# Perceptron

## Binary Classification

Given $\large n$ points $\large (\textbf{x}_1, y_1), (\textbf{x}_2, y_2), ..., (\textbf{x}_n, y_n)$ learning a function $\large h$ such that,
$$
\Large h(x) = y
$$
where $\large \textbf{x}_i \in \R^d$ is a vector of length $\large d$ and $\large y \in \{-1, 1\}$ is a binary label, is known as **Binary Classification**.

## Statistical Learning

Given $\large n$ points $\large (\textbf{x}_1, y_1), (\textbf{x}_2, y_2), ..., (\textbf{x}_n, y_n) \sim {}_{i.i.d} \: P$ learn a function $\large h: \R^d \rarr \{-1, 1\}$ such that,
$$
\Large Pr_{(\textbf{x}, y) \sim P}[h(\textbf{x}) = y] >\!\!> 0
$$
where $\large \textbf{x}_i \in \R^d$ is a vector of length $\large d$,  $\large y \in \{-1, 1\}$ is a binary label, and $\large P$ is an unknown distribution.

A collection of random variables is **independent and identically distributed** if each random variable has the same probability distribution as the others and all are mutually independent.

## Online Learning

``**Online learning** involves learning the function using one data observation at a time. At each step $\large i = 1, 2, ...$:

1. Receive feature vector $\large \textbf{x}_i$
2. Choose prediction function $\large h_i$, predict label $\large \hat{y}_i = h_i(\textbf{x}_i)$
3. View true label $\large y_i$, suffer mistake if $\large y_i \ne \hat{y}_i$

## Perceptron Algorithm

**Input**

- Dataset, $\large (\textbf{x}_1, y_1), (\textbf{x}_2, y_2), ..., (\textbf{x}_n, y_n) \in \R^d \times \{-1, 1\}$
- Initial weights, $\large \textbf{w} \in \R^d$ (typically $\large \vec{0}$)
- Initial bias, $\large b \in \R$ (typically $\large 0$)
- Threshold, $\large \delta \ge 0$ (typically $\large 0$)

**Output**

- Trained weights, $\large \textbf{w} \in \R^d$
- Trained bias, $\large b \in \R$

$$
\large \begin{align*}
& \texttt{for } t = 1, 2, ..., \texttt{do} \\
& \:\:\:\:\:\:\:\: \texttt{select training example index } I_t \in \{1, ..., n\} \:\:\:\:\: \\
& \:\:\:\:\:\:\:\: \texttt{if } y_{I_t} (\textbf{w}^\text{T} \textbf{x}_{I_t} + b) \le \delta \texttt{ then} \\
& \:\:\:\:\:\:\:\:\:\:\:\:\:\:\:\: \texttt{\textbf{w}} \larr \texttt{\textbf{w}} + y_{I_t} \textbf{x}_{I_t} \\
& \:\:\:\:\:\:\:\:\:\:\:\:\:\:\:\: b \larr b + y_{I_t}
\end{align*}
$$

### Uniqueness

The perceptron algorithm only guarantees (given the right convergence condition) finding some solution, which may not necessarily be the best one.

### Termination

The perceptron algorithm can terminate when one of the following is true:

- all points are classified correctly
- validation error stops decreasing (validation dataset is not used for training, but to avoid overfitting)
- some iteration budget is exhausted
- weights and bias are not changing much

## Padding & Pre-Multiplication

Goal: Find $\large \textbf{w}, b$ such that, for all $\large i \in 1, 2, ..., n$
$$
\Large \begin{align*}
y_i &= \text{sign}((\textbf{w} \times \textbf{x}_i) + b) \\
&= \text{sign}(\langle \textbf{w}, \textbf{x}_i \rangle + b)
\end{align*}
$$
where $\large \langle \textbf{A}, \textbf{B}\rangle$ represents the dot product of vectors $\large \textbf{A}$ and $\large \textbf{B}$.

Thus,
$$
\Large \begin{align*}
y_i &= \text{sign}(\langle \textbf{w}, \textbf{x}_i \rangle + b) \\
&= \text{sign}(\langle (\textbf{w}, b), (\textbf{x}_i, 1) \rangle)
\end{align*}
$$
where $\large (\textbf{A}, b)$ represents the vector $\large \textbf{A}$ padded with scalar $\large b$.
$$
\Large (\textbf{w}, b) =
\begin{bmatrix}
w_1 \\ w_2 \\ w_3 \\ ... \\ w_d \\ b
\end{bmatrix}, \:\:\:\:\:\:\:\:
\Large (\textbf{x}_i, 1) =
\begin{bmatrix}
x_{i,1} \\ x_{i,2} \\ x_{i,3} \\ ... \\ x_{i,d} \\ 1
\end{bmatrix} \\[15pt]
\Large \implies \text{sign}(\langle (\textbf{w}, b), (\textbf{x}_i, 1) \rangle) = w_1 x_{i,1} + w_2 x_{i,2} + ... + w_d x_{i,d} + b
$$
Thus,
$$
\Large \begin{align*}
y_i &= \text{sign}(\langle (\textbf{w}, b), (\textbf{x}_i, 1) \rangle) \\
&= \text{sign}(\langle \textbf{z}, (\textbf{x}_i, 1) \rangle)
\end{align*}
$$
where $\large \textbf{z} = (\textbf{w}, b)$,

Thus,
$$
\Large \begin{align*}
y_i &= \text{sign}(\langle \textbf{z}, (\textbf{x}_i, 1) \rangle) \\
&\implies y_i \langle \textbf{z}, (\textbf{x}_i, 1) \rangle > 0 \\
&\implies \langle \textbf{z}, y_i (\textbf{x}_i, 1) \rangle > 0 \\
&\implies \langle \textbf{z}, \textbf{a}_i \rangle > 0 \\
\end{align*}
$$
where $\large \textbf{a}_i = y_i (\textbf{x}_i, 1)$.

Thus, our goal is,
$$
\Large \textbf{A} \textbf{z} > \vec{0}
$$
where $\large \textbf{A}$ is the matrix with rows $\large a_i$:
$$
\Large \textbf{A} =
\begin{bmatrix}
\textbf{a}_1 \\
\textbf{a}_2 \\
... \\
\textbf{a}_n
\end{bmatrix} =
\begin{bmatrix}
y_1 x_{1,1} & y_1 x_{1,2} & ... & y_1 x_{1,d} & y_1 \\
y_2 x_{2,1} & y_2 x_{2,2} & ... & y_2 x_{2,d} & y_2 \\
... & ... & ... & ... & ... \\
y_n x_{n,1} & y_n x_{n,2} & ... & y_n x_{n,d} & y_n
\end{bmatrix}
$$

## Linear Separability

A dataset has **linear separability** if and only if there exists,
$$
\Large \: \textbf{z} = (\textbf{w}, b)
$$
such that,
$$
\Large \langle \textbf{z}, \textbf{a}_i \rangle \ge s > 0
$$
for all $\large i \in {1, 2, ..., n}$, for some constant $\large s \in \R^+$.

Equivalently,
$$
\Large \textbf{A} \textbf{z} \ge s \vec{1}
$$

## Error Bound & Margin

For a linearly separable dataset, a perceptron will converge in a number of steps (or mistakes) given by,
$$
\Large R^2 \bigg(\frac{||\textbf{z}||_2^2}{s^2}\bigg)
$$
where $\Large ||.||_2$ is the L2 norm operator and $\large R = \max\limits_i ||\textbf{a}_i||$.

Given our goal is to minimize the number of steps,
$$
\Large \begin{align*}
&\min\limits_{(\textbf{z}, s): \: \textbf{A} \textbf{z} \ge s \vec{1}} \bigg(\frac{||\textbf{z}||_2^2}{s^2}\bigg) \\[10pt]
&= \min\limits_{(\textbf{z}, s): \: ||\textbf{z}||_2 = 1, \: \textbf{A} \textbf{z} \ge s \vec{1}} \bigg(\frac{1}{s^2}\bigg) \\[10pt]
&= \frac{1}{\bigg(\max\limits_{(\textbf{z}, s): \: ||\textbf{z}||_2 = 1, \: \textbf{A} \textbf{z} \ge s \vec{1}} s\bigg)^2} \\[10pt]
&= \Bigg(\frac{1}{\underbrace{\max\limits_{||\textbf{z}||_2 = 1} \: \min\limits_i \: \langle \textbf{z}, \textbf{a}_i \rangle}_{\text{margin } \gamma}}\Bigg)^2
\end{align*}
$$

## Multiclass Classification

**Multiclass Classification** is the process of classifying data when there are more than 2 classes of labels. There are two approaches taken in that case.

### One vs All

- Train $\large k$ binary classifiers, each predicting whether the data is of a certain label or not
- Output prediction label based on $\large \arg \max\limits_i \langle \textbf{z}, \textbf{a}_i \rangle$

### One vs One

- Train $\large k \choose 2$ binary classifiers, one for each combination of labels
- Run all $\large k \choose 2$ classifiers and output the majority vote