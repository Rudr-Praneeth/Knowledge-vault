# Complexity Analysis
TAGS: #DSA 
BUILT-ON:  - 
ENABLES: - 
PREREQUSITIES: - 

---
# Complexity Analysis
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

## Asymptotic Analysis
Asymptotic analysis is a mathematical analysis of growth of an algorithm's resource usage (Typically space and time) as the input size tends towards infinity, ignoring machine dependent constants and lower-order terms. It study of growth of time or space.
It characterizes the algorithm using asymptotic bounds such as O(g(n)), Ω(g(n)) and Θ(g(n))
Where g(n) is a reference growth function[^1].
#### Big-O (Upper-Bound)
`f(n) = O(g(n))` means there exist positive constants `c` and `n₀` 
Such that for all `n ≥ n₀`
	$f(n) ≤ c . g(n)$
This means, _f(n) does not grow faster than g(n)_, beyond some point `n₀`, up to a constant factor
- ~={purple}c=~: a positive constant multiplier.
- ~={purple}n_0=~: the point after which the bound must hold.
- ~={purple}f(n)=~: actual growth being analysed.
- ~={purple}g(n)=~: proposed asymptotic upper-bound function.
#### Big-Ω (Lower-Bound)
`f(n) = Ω(g(n))` means there exist positive constants `c` and `n₀` 
Such that for all `n ≥ n₀`:  
	`f(n) ≥ c · g(n)`
This means, _f(n) grows at least as fast as g(n)_. 
- ~={purple}c=~: a positive constant multiplier.
- ~={purple}n_0=~: the point after which the bound must hold.
- ~={purple}f(n)=~: actual growth being analysed.
- ~={purple}g(n)=~: proposed asymptotic lower-bound function.
#### Big-Θ (Tight-Bound)
`f(n) = Θ(g(n))` means `f(n) = O(g(n))` **and** `f(n) = Ω(g(n))` simultaneously. 
There exist constants `c₁, c₂, n₀` such that for all `n ≥ n₀`:  
	`c₁ · g(n) ≤ f(n) ≤ c₂ · g(n)`
This means, _f(n) grows at exactly the same rate as g(n)_, sandwiched between two constant multiples of it.

## Case Analysis
Case analysis describes an algorithm's performance based on the input/arrangement of the input/input classes.
#### Best-case
The input scenario for which the algorithm performs the least amount of computational work is known as the Best-case of an algorithm.
#### Average-case
The expected amount of computational work performed by an algorithm over all possible inputs, considering their likelihood of occurrence.
#### Worst-case
The input scenario for which the algorithm performs the maximum amount of computational work is known as the worst-case of an algorithm.

>**~={purple}IMPORTANT NOTE=~**:
>Case analysis describes the input scenario; asymptotic notation describes mathematical bounds on growth.

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
%%**IMPORTANT ORDER RULES**%%
- Any constant power of log n grows slower than any positive power of n. 
  For example, $(log n)^3 < n^{1.1}$ 
- Any exponential function grows faster than any polynomial function.
  For example, $n^{100} < 2^n$

---
# Calculating Complexity Analysis
## Analysing Loops
~={purple}***Stepping Linear Loops***=~: Stepping Linear Loops are single loops which run for `n` or $\frac {n} {c}$ steps where c is the constant for step. The asymptotic tight bound for this is usually Θ(n).
```py
for ITERATION in range(START, STOP, STEP):
	WORK()
```

~={purple}***Nested Loops***=~: Nested loop's complexity is calculated by multiplying the individual time complexity of independent loops and expressing the iteration counts appropriately for dependent loops. 
***Case 1*** ~={cyan}***Independent Bounds***=~: Independent Bound Nested loops can have same bounds[^2] or different bounds[^3] the time complexity of algorithms with independent bound nested loops is calculated by multiplying the bounds of the loops.  
```py
for i in range(N, STEP_1):
	for j in range(M, STEP_2)
		WORK()
		
TIME COMPLEXITY = Θ(n * m)
```
**Case 2*** ~={cyan}***Dependent Bounds***=~: Nested loop whose inner loops number of iterations are dependent upon the outer loop. The time complexity of algorithms dependent bound nested loops is calculated by expressing the iteration counts appropriately. 
```py
for i in range(N):
	for j in range(i):
		WORK()
```
[[Complexity Analysis - Loops]]

## Recursion and Recurrence Relations
A recursive function is a function which calls itself to solve a complex problem by reducing it into simpler smaller problems by delegating a part of work to a recursive call. 
Every recursive function contains two things:
- ~={purple}Base Case=~: The base case is a condition for which the function returns an answer directly, without making another recursive call.
- ~={purple}Recursive Case=~: The recursive case reduces the current problem and delegates part of the work to a recursive call.
A call frame conceptually stores the information needed for one active function call: its parameters, local variables, and where execution should resume. Each recursive call adds a frame. When that call returns, its frame is removed.
The stack is last in, first out (LIFO): the most recent call must finish before the earlier call can continue.
A recursive algorithm's time complexity is calculated by representing it as a recurrence relation. 
~={purple}Recurrence Relation=~: A recurrence relation describes the running time of a recursive algorithm in terms of the running time of smaller inputs.
Every recursive function does two kinds of work per call:
- Some amount of local work (before/after/between the recursive calls) - f(n).
- One or more recursive calls on smaller subproblems.
So the general shape is:
$$T(n) = a^j\times T(\frac n {b^j}) + f(n)$$
Where:
$a^j$: Number of recursive calls
$\frac n {b^j}$: Size of subproblem 
`n`: Input size
`f(n)`: Non-recursive work
Total non-recursive work at that level: $a^j f\left(\frac{n}{b^j}\right)$

> The auxiliary call-stack space complexity is given by the number of active calls at the deepest point.
> The depth is approximately $\log_b n$. The number of leaves is approximately $a^{\log_b n}=n^{\log_b a}$.

#### Python Specific Recursion Notes
- Python uses a recursion limit, commonly around 1,000 calls by default, though the actual setting and environment can vary. Deep recursion can raise `RecursionError`, even when the algorithm is logically correct. This can be set using the `sys` standard library in Python but Setting it too high can cause a stack overflow or crash Python.
  ```python
  import sys
  
  sys.getrecursionlimit()
  sys.setrecursionlimit(INTEGER)
  ```
- Each active call consumes stack-related memory. Memoization can remove repeated computation, but it does not necessarily reduce recursion depth. An iterative implementation may avoid recursion-stack costs.

## Space Complexity
Space complexity measures how memory consumption grows as the input size grows.
~={purple}**Total Space**=~: Total space considers the memory occupied by the input, the output, and the additional memory required while the algorithm executes.
Memory used by an algorithm:
1. ***Input space***
   Memory occupied by the data supplied to the algorithm.
2. ***Auxiliary space***
   Additional working memory created or used by the algorithm, excluding the input and usually excluding the returned output.
3. ***Output space***
   Memory required to store the result produced by the algorithm.
$\boxed{ \text{Total Space} = \text{Input Space} + \text{Auxiliary Space} + \text{Output Space} }$

This is the space-time tradeoff:
- Sometimes we use more memory to improve speed.
- Sometimes we use more computation to reduce memory.
- The right decision depends on constraints.
A call frame (also called a stack frame) is a block of memory associated with an individual function call.
It typically stores information such as:
- Function arguments and parameters.
- Local variables
- Return address or information about where execution should resume
- Saved execution state and other bookkeeping information
Call frames are stored on a memory structure called the call stack.
When a function is called, a new call frame is pushed onto the stack. When that function returns, its call frame is popped from the stack. Each recursive call creates a new call frame because the program must preserve the information needed to resume the previous function call after the recursive call returns.
Therefore, recursion consumes stack memory.
Sequential recursive calls made by the same function generally do not coexist as active child calls on the stack if the first call must return before the second call begins. However, the parent function's call frame remains active while waiting for each recursive call to complete. Therefore, although two sequential child calls do not overlap, their parent call and the currently executing child call do coexist on the stack. In branching recursion, multiple recursive calls are generally executed sequentially, but the parent call remains active until all required recursive calls have returned.

## Amortised Analysis
Amortized analysis is a method of analysing the average cost per operation over a sequence of operations in the worst-case sequence of operations. It guarantees that the total cost of a sequence of `m` operations is bounded, even if some individual operations are expensive.
More precisely, if a sequence of \(m\) operations has total cost \(T(m)\), then its amortized cost per operation is bounded by: $\frac{T(m)}{m}$. 
**Worst-case**; Maximum time a single operation can take.
**Average-case**: Expected time for an operation across possible inputs, based on an assumed input distribution.
**Amortized**: Average cost per operation over a sequence of operations, including occasional expensive operations.


---
# Time Complexity Estimation b/o Constraints 
A modern CPU executes roughly **10⁸ to 10⁹ simple operations per second**.
Let's assume $C_1 \le n \le C_2$, where $C_1$ and $C_2$ are constant constraints. 
We know that $$f(n) = O(g(n)) = C_2 \times g(n)$$
We check g(n) for $n= C_2$ , i.e. $g(C_2)$.
- If $g(C_2)$ is less than $10^8$, the algorithm is considered to be working without a TLE Error.
- If $g(C_2)$ is greater than $10^8$, the algorithm is considered slow and may generally hit a TLE Error.











# END
---
#### FOOTNOTES
[^1]: A **growth function** is a mathematical function g(n) that describes how the amount of computational resource used by an algorithm grows as a function of input size n.

[^2]: Same Bounds: Outer and inner loop same number of iterations i.e. n and n iterations

[^3]: Different Bounds loops are loops whose outer and inner loops have different number of iterations i.e. n and m iterations 
