# Combinations & Permutations

## Permutations without Repetition

**Permutations without repetition** refers to the number of arrangements formed by ordering $\large r$ elements from a pool of $\large n$ elements such that there are no repetitions.

### Formula

$$
\Large {}^nP_r = \frac{n!}{(n - r)!}
$$

### Example

There are 12, 3-letter words that can be generated from the letters of the word **FART**:

FA, AF, FR, RF, FT, TF, AR, RA, AT, TA, RT, TR
$$
\Large {}^4P_2 = \frac{4!}{(4 - 2)!} = 12
$$

## Permutations with Repetition

**Permutations with repetition** refers to the number of arrangements formed by ordering $\large r$ elements from a pool of $\large n$ elements such that there may be repetitions.

### Formula

$$
\Large n^r
$$

### Example

There are 8 possible arrangements of 1s and 0s in a 3-digit binary number:

000, 001, 010, 011, 100, 101, 110, 111.
$$
\Large 2^3 = 8
$$

## Combinations without Repetition

**Combinations without repetition** refers to the number of ways to choose $\large r$ elements from a pool of $\large n$ elements such that there are no repetitions.

### Formula

$$
\Large {}^nC_r = \binom{n}{r} = \frac{n!}{r!\:(n - r)!}
$$

### Example

There are 4, 3-letter combinations that can be generated from the letters of the word **FART**:

FAR, FRT, FAT, ART.
$$
\Large {}^4C_3 = \frac{4!}{3!\:(4 - 3)!} = 4
$$

### Additional Identities

$$
\Large \binom{n}{r} = \binom{n - 1}{r - 1} + \binom{n - 1}{r} \\[15pt]
\Large \binom{n}{r} = \binom{n}{n - r}
$$

## Combinations with Repetition

**Combinations with repetition** refers to the number of ways to choose $\large r$ elements from a pool of $\large n$ elements such that there may be repetitions.

### Formula

$$
\Large \bigg(\!\!\!\binom{n}{r}\!\!\!\bigg) = \binom{n + r - 1}{r} = \frac{(n + r - 1)!}{r!\:(n - 1)!}
$$

### Example

There are 10 ways to place 2 balls into 4 different boxes:

4 ways where both balls are in the same box, 6 other ways to choose 2 different boxes from 4.
$$
\Large \bigg(\!\!\!\binom{4}{2}\!\!\!\bigg) = \frac{5!}{2!\:3!} = 10
$$

## Binomial Theorem

**Binomial theorem** describes the algebraic expansion of powers of a binomial of the form $\large (x + y)^n$.

### Formula

$$
\Large (x + y)^n = \sum\limits^n_{k = 0} \binom{n}{k} x^k y^{n - k}
$$

## Multinomial Coefficients

**Multinomial coefficients** are the coefficients in the terms of expansion of a power of a multinomial. It is the number of different divisions possible if $\large n$ distinct items are to be divided into $\large r$ distinct groups of respective sizes $\large n_1, n_2, n_3, ..., n_r$, where $\large \sum\limits^r_{k = 1} n_k = n$.

### Formula

$$
\Large \binom{n}{n_1, n_2, n_3, ..., n_r} = \frac{n!}{n_1!n_2!n_3! ... n_r!}
$$

## Multinomial Theorem

**Multinomial theorem** describes the algebraic expansion of powers of a multinomial of the form $\large (x_1 + x_2 + x_3 + ... + x_r)^n$.

### Formula

$$
\Large (x_1 + x_2 + x_3 + ... + x_r)^n = \sum\limits_{n_1 + n_2 + ... + n_r = n} \binom{n}{n_1, n_2, n_3, ..., n_r} \prod\limits^r_{k = 1}x_k^{n_k}
$$
