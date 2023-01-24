# Introduction to Cryptology

## Cryptology

**Cryptology** is the practice and study of constructing and analyzing codes for secure communication

## Cryptography

**Cryptography** is the study of the design of mathematical systems that allowing secure communication that aims to protect privacy and authenticity.

## Cryptanalysis

**Cryptanalysis**, the reverse function of cryptography, is the study of breaking encrypted codes without access to secret information (i.e. the key) required for decryption.

## NIST Standards for Security Categorization of Federal Information and Information Systems

The NIST standard FIPS 199 (Standards for Security Categorization of Federal Information and Information Systems ) lists **confidentiality**, **integrity**, and **availability** as the three security objectives for information and for information systems.

### Confidentiality

Confidentiality involves preserving authorized restrictions on information access and disclosure, including means for protecting personal privacy and proprietary information. A loss of confidentiality is the unauthorized disclosure of information.

### Integrity

Integrity involves guarding against improper information modification or destruction, including ensuring information nonrepudiation and authenticity. A loss of integrity is the unauthorized modification or destruction of information.

### Availability

Availability involves ensuring timely and reliable access to and use of information. A loss of availability is the disruption of access to or use of information or an information system.

## Block & Stream Ciphers

A **block cipher** breaks down plaintext messages into fixed-size blocks before converting them into ciphertext using a key. This is usually a permutation algorithm that maps $n$ bits to $n$ bits.

A **stream cipher** breaks a plaintext message down into single bits, which then are converted individually into ciphertext using key bits.

## Symmetric & Asymmetric Key Encryptions

**Symmetric encryption** is a widely used data encryption technique whereby data is encrypted and decrypted using a single, secret cryptographic key.

**Asymmetric encryption**, also known as public-key cryptography or public-key encryption, uses mathematically linked public-key and private-key pairs to encrypt and decrypt senders' and recipients' sensitive data.

## Kerckhoffs' Principle

- Algorithms in a cipher system must be public, with the only exception to public information being a pre-shared key
- The cipher method must not be required to be secret, and it must be able to fall into the hands of the enemy without inconvenience
- An attacker can intercept communications among entities, thus they have ciphertext at hand
- An attack can make queries to the system by inputing either plaintext or ciphertext as many times as they wish

## Perfect Secrecy

An encryption scheme over message space $\large \mathcal{M}$ is **perfectly secret** if for every probability distribution over $\large \mathcal{M}$, every message $\large m \in \mathcal{M}$, and every ciphertext $\large c \in \mathcal{C}$ for which $\large \text{Pr}[M = m] > 0$ and $\large \text{Pr}[C = c] > 0$,
$$
\Large \text{Pr}[M = m | C = c] \: = \: \text{Pr}[M = m]
$$
or equivalently,
$$
\Large \text{Pr}[C = c | M = m] \: = \: \text{Pr}[C = c]
$$
Perfect secrecy implies that there must be, for any message and cipher pair, at least one key that connects them. Hence,
$$
\Large |\mathcal{K}| \ge |\mathcal{C}| \ge |\mathcal{M}|
$$

## Negligible Functions

A function $\large \mu$ is **negligible** if for every polynomial $\large p(x)$ there exists an integer $\large N$ such that, for all integers $\large n > N$,
$$
\Large \mu(n) < \frac{1}{p(n)}
$$

### Properties

Given two negligible functions $\large \mu_1$ and $\large \mu_2$,

- $\large \mu_1 + \mu_2$ is negligible
- $\large \mu_1 \times \mu_2$ is negligible

## One-way Functions

A function $\large f : \{0, 1\}^* \rarr \{0, 1\}^*$ is a **one-way** function if the following conditions hold:

### Ease of Computation

There exists a (deterministic) polynomial-time algorithm $\large A$ such that on input $\large x$, algorithm $\large A$ outputs $\large f(x)$

### Difficulty of Inversion

The probability of successfully inverting $\large f$ is negligible. Specifically, for every probabilistic polynomial-time algorithm $\large A'$, every polynomial $\large p(x)$, and all sufficiently large $\large n$,
$$
\Large \text{Pr}[A'(f(X_n), 1^n) \in f^{-1}(f(X_n))] < \frac{1}{p(n)}
$$
where $\large X_n$ is a random variable uniformly distributed over $\large \{0, 1\}^n$ and $\large 1^n$ is called the auxiliary input which is used to specify the length of the output of $\large A$.

## Semantic Security

A symmetric key encryption scheme is **semantically secure** in the presence of an eavesdropper if the probability that it distinguishes the ciphertext from a random string using any probabilistic polynomial time algorithms is negligible.