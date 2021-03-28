# Analysis of Transistor Amplifiers

## Frequency Response Graph

![Frequency Response Graph](img/AnalysisOfTransistorAmplifiers/FrequencyResponse.png)

### Notes

- At low frequencies, parasitic, bypass and coupling capacitors are open circuited
- At the midband, bypass and coupling capacitors are short circuited, parasitic capacitors are open circuited
- At high frequencies, parasitic, bypass and coupling capacitors are short circuited

## DC Analysis

- Bypass, coupling and parasitic capacitors are open circuited
- AC voltage sources are short circuited
- AC current sources are open circuited

## Small Signal Analysis

- Bypass and coupling capacitors are short circuited, parasitic capacitors are open circuited
- DC voltage sources are short circuited
- DC current sources are open circuited

## Low Frequency Analysis

### Method of Open Circuit Time Constants

1. Set all parasitic capacitors to open circuit
2. Set input voltage $\Large v_{sig} = 0$.
3. Consider each capacitor individually in the small signal model; i.e. short circuit all other capacitors
4.  For each capacitor $\Large C_i$, find its input resistance $\Large R_i$. This can be done by setting test source $\Large V_x$ and evaluating current $\Large I_x$, so that $\Large R_i = \frac{V_x}{I_x}$.
5. $\Large f_L = \sum\limits_{i = 1}^{n}\frac{1}{2\pi C_iR_i}$.

## High Frequency Analysis

### Method of Open Circuit Time Constants

1. Set all bypass and coupling capacitors to capacitors to short circuit
2. Set input voltage $\Large v_{sig} = 0$.
3. Consider each capacitor individually in the small signal model; i.e. short circuit all other capacitors
4. For each capacitor $\Large C_i$, find its input resistance $\Large R_i$. This can be done by setting test source $\Large V_x$ and evaluating current $\Large I_x$, so that $\Large R_i = \frac{V_x}{I_x}$.
5. $\Large f_L = \sum\limits_{i = 1}^{n}\frac{1}{2\pi C_iR_i}$.

## Miller Theorem

![Miller Theorem](img/AnalysisOfTransistorAmplifiers/MillerTheorem.png)
$$
\Large R_{M1} = \frac{R}{1-K},\:\:\:R_{M2} = \frac{RK}{K-1} \\[15pt]
\Large K = \frac{V_2}{V_1}
$$