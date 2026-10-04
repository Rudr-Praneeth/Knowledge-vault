# Complexity Analysis Test
TAGS:  #DSA #DSA-PROBLEMS 

---

## Complexity Analysis Test
~={cyan}Problem=~: If `f(n) = 7n³ + 2n² + 100`,
- Is it true that `f(n) = O(n⁴)`? 
- Is it true that `f(n) = Θ(n⁴)`? Justify.
~={green}Solution=~: 
To Prove ``f(n) = O(g(n))``, we need to prove that:
There exists a pair (c, n₀) which satisfies the condition 
$$f(n) \le c \times g(n)$$$\text{for} \quad c > 0 \quad \text{and} \quad n \ge n_0$
**STEP 1: Decide the Bounding Strategy**:
- Restrict Attention to $n \ge 1$.
  Since for $n \ge 1$ we know that $n \le n^2 \le n^3 ...$
**STEP 2: Bound Each Term**:
$7n^3 + 2n^2 + 100 \le c \times n^4$
- $7n^3 \le 7n^4$
- $2n^2 \le 2n^4$
- $100 \le 100n^4$
**STEP 3: Combining all the Bounded Terms**:
$7n^3 + 2n^2 + 100 \le 7n^4 + 2n^4 + 100n^4 \le c \times n^4$
$7n^3 + 2n^2 + 100 \le 109n^4$
Therefore, a pair (c = 109, n₀ = 1) exists for which $f(n) \le c \times g(n)$.

To Prove `f(n) = Θ(n⁴)`, we need to prove that `Ω(n⁴) and O(n⁴)`. Since O(n⁴) is proved possible we will now attempt to prove Ω(n⁴) holds for the given f(n) and g(n).
To prove that `f(n) = Ω(n⁴)`, we need to prove that:
There exists a pair (c, n₀) which satisfies the condition:
$$f(n) \ge c \times g(n)$$
for $c > 0 \quad \text{and} \quad n \ge n_0$.
Since, 
	f(n) = $7n^3 + 2n^2 + 100$
	g(n) = $n^4$
$7n^3 + 2n^2 + 100 \ge c \times n^4$
Dividing by $n^4$ on Both Sides:
	$7/n + 2/n^2 + 100/n^4 \ge c$
For $n \rightarrow \infty$, 
$0 \ge c$.
But this contradicts the statement $c > 0$ and hence we can say that there exists no pair for f(n) = Ω($n^4$) and thereby it is proved that $f(n) \ne Ω(n^4)$ and $f(n) \ne Θ(n^4)$

---
