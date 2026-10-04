# Complexity Analysis
TAGS: #DSA 
BUILT-ON:  - 
ENABLES: - 
PREREQUSITIES: - 

---
## Complexity Analysis
Runtime depends on things such as:
- CPU
- Memory
- Programming Language
- Compiler/Interpreter
- System Load
- Implementation Details
A measure of efficiency for algorithms that is:
- A function of size of the input (n).
- Independent of the Hardware, Language and Constant Factors
- Dependent upon the size of the input (n) and is concerned with the trend $n \to \infty$.  

## Order of Growth
Let f(n) and g(n) be the time taken by two algorithms where n >= 0 and f(n) and g(n) are also greater than equal to 0. A function f(n) is said to be growing faster than g(n) if g(n)/f(n) for n tends to infinity is 0 (or f(n)/g(n) for n tends to infinity is infinity).
#### Finding Order of Growth
When n >= 0, f(n) >= 0 and g(n) >= 0, we can use the below steps.
- Ignore the order terms.
- Ignore the constants
%%ORDER OF COMPARISION%%
$$
c < \log(\log(n)) < \log(n) < n^{1/3} < n^{1/2} < n < n\log(n) < n^2....
$$
## Case Analysis
Case analysis describes an algorithm's performance based on the input/arrangement of the input/input classes.
#### Best-case
#### Average-case
#### Worst-case

## Asymptotic Analysis
Asymptotic analysis is a mathematical analysis of growth of an algorithm's resource usage (Typically space and time) as the input size tends towards infinity, ignoring machine dependent constants and lower-order terms. It study of growth of time or space.
It characterizes the algorithm using asymptotic bounds such as:
- O(g(n))
- Ω(g(n))
- Θ(g(n))
Where g(n) is a reference growth function.
Let `f(n)` be the actual running time (or operation count) of an algorithm, and `g(n)` be some reference function (like `n`, `n²`, `log n`).

#### Big-O (Upper-Bound)
`f(n) = O(g(n))` means there exist positive constants `c` and `n₀` 
Such that for all `n ≥ n₀`
	$f(n) ≤ c . g(n)$
This means, _f(n) does not grow faster than g(n)_, beyond some point `n₀`, up to a constant factor.

#### Big-Ω (Lower-Bound)
`f(n) = Ω(g(n))` means there exist positive constants `c` and `n₀` 
Such that for all `n ≥ n₀`:  
	`f(n) ≥ c · g(n)`
This means, _f(n) grows at least as fast as g(n)_. 

#### Big-Θ (Tight-Bound)
`f(n) = Θ(g(n))` means `f(n) = O(g(n))` **and** `f(n) = Ω(g(n))` simultaneously. 
There exist constants `c₁, c₂, n₀` such that for all `n ≥ n₀`:  
	`c₁ · g(n) ≤ f(n) ≤ c₂ · g(n)`
This means, _f(n) grows at exactly the same rate as g(n)_, sandwiched between two constant multiples of it.

>**~={purple}IMPORTANT NOTE=~**:
>Case analysis describes the input scenario; asymptotic notation describes mathematical bounds on growth.

## Time Complexity Estimation b/o Constraints 
A modern CPU executes roughly **10⁸ to 10⁹ simple operations per second**.
Let's assume $C_1 \le n \le C_2$, where $C_1$ and $C_2$ are constant constraints. 
We know that $$f(n) = O(g(n)) = C_2 \times g(n)$$
We check g(n) for $n= C_2$ , i.e. $g(C_2)$.
- If $g(C_2)$ is less than $10^8$, the algorithm is considered to be working without a TLE Error.
- If $g(C_2)$ is greater than $10^8$, the algorithm is considered slow and may generally hit a TLE Error.

## Calculating Time Complexity 
#### Functions & Non-recursive Algorithms
The time complexity of simple non-recursive functions and algorithms is calculated using the following formulae:
$\text{Time Complexity} = O(1)_{(\text{One Constant Work})} \times \text{Number of Iterations}$.
>Whenever a loop variable multiplies (or divides) by a constant factor each iteration, the iteration count is O(log n). Whenever it adds/subtracts a constant, iteration count is O(n).

#### Recursion and Recurrence Relations
A recursive algorithm's time complexity is calculated by representing it as a recurrence relation. 
~={purple}Recurrence Relation=~: An equation for T(n) (time for input size n) in terms of T smaller inputs, then solve that recurrence to get a closed form.
Every recursive function does two kinds of work per call:
- Some amount of local work (before/after/between the recursive calls) - f(n).
- One or more recursive calls on smaller subproblems.
So the general shape is:
$$T(n) = (\text{number of recursive calls})\times T(\text{size of subproblem}) + f(n)$$














---
## Complexity Analysis Test
[[Complexity Analysis - Test]]

## Time Complexity Analysis Test
[[Time Complexity Analysis - Test]]