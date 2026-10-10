# Mathematics Fundamentals
TAGS: #DSA #Mathematics 
BUILT-ON: - 
ENABLES: - 
PREREQUSITIES: - 

---
## Progressions and Sequences
~={purple}Numerical Sequences=~: A numerical sequence is an ordered list of numbers. The numbers are called terms. We usually represent them as: 
$$a_1,a_2,a_3,a_4,… a_n$$
~={purple}Progression=~: A progression is a sequence following a mathematical pattern

#### Arithmetic Progression
An **Arithmetic Progression** is a sequence in which the **difference between consecutive terms is constant**.
~={purple}General Form=~: a, a+d, a+2d, a+3d,…
Where:
- First Term = a
- Common difference = d
~={purple}n_th Term=~: $a_n = a + (n−1)d$ 
~={purple}Sum of n Terms=~: 
- $S_n = n/2 * [(2a + (n-1)d)]$
- $S_n = n/2*(a+l)$
  Where l is the last term
~={purple}Important Properties=~:
- $2a_2 = a_1 + a_3$
- $a_2 - a_1 = a_3 - a_2$

#### Geometric Progression
In a **Geometric Progression**, the **ratio between consecutive terms is constant**.
~={purple}General Form=~: $a + ar + ar^2 + ar^3 + ...$ 
Where:
- First Term = a
- Common Ratio = d
~={purple}n_th Term=~: $a_n = ar^{n-1}$  
~={purple}Sum of n Terms=~: 
- $S_n = \frac{a(1-r^n)}{1-r}$ 
- $S_\infty = \frac{a}{1-r}$
~={purple}Important Properties=~:
- $S_{\infty}$ exists as a finite value only when $|{r}| < 1$.
- $b^2 = ac$

#### Harmonic Progression
A sequence is in **Harmonic Progression** if the **reciprocals of its terms are in AP**.
~={purple}General Form=~: $h_n = \frac{1}{(A + (n-1)d)}$ 
Where:
- First Term = A
- Common Ratio = d
~={purple}n_th Term=~: $h_n = \frac{1}{(A + (n-1)d)}$ 
~={purple}Sum of n Terms=~: 
- $S_n = \sum_{k=0}^{n-1} \frac{1}{a+kd}$


## Exponentiation

## Logarithms
Logarithms are fundamentally the inverse operation of exponentiation.
A logarithm asks what exponent/power ``p`` must I put on `base b` to obtain `x`.
Where `a` is known as `base`, `p` is known as `logarithm/power` and `x` is known as `argument`.
So Mathematically, 
$$log_{b} x = p \longleftrightarrow b^p = x$$
Where the logarithm is only defined when,
- `b > 0` 
- `b ≠ 1`
- `x > 0`

![[Pasted image 20261005170234.png|280]]

Logarithms of numbers when base is not mentioned are interchangeably used with ***Natural Logarithms*** i.e. Logarithms with base e where $e≈2.718281828459…$
 
~={purple} ***Fundamental Logarithmic Values***=~
 - $log_a​1=0​$
 - $log_a​a=1​$
 - $log_a​(a^x)=x​$
 - $a^{(log_a​x)} = x​$

#### LOGARITHMIC LAWS
- ~={purple} ***Product Law***=~: $log_a{(xy)} = log_a x + log_a y$
- ~={purple} ***Quotient Law***=~: $log_a(\frac{x}{y}) = log_a x - log_a y$ 
- ~={purple} ***Power Law***=~: $log_a x^n = n \times log_a x$
- ~={purple} ***Root Formula***=~: $log_a \sqrt[n]{x^m} = \frac{m}{n} log_a x$ 
- ~={purple} ***Change of Base Formulae***=~: 