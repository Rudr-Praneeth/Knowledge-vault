# Recursion and Recurrences
TAGS: #DSA 
BUILT-ON: [[Complexity Analysis]]

---
# DSA Mastery Assessment: Recursion & Recurrences
## Part A Recursion fundamentals and call stack
### Question 1: Trace every call
Consider:
```
def mystery(n):    
	if n <= 1:        
		return 1    
	return n + mystery(n - 2)
```
For the call `mystery(6)`, answer all parts:
1. List the arguments in the order calls are made.
2. List the return values in the order calls finish.
3. What is the final returned value?
4. How many function calls occur, including the base case?
5. What is the maximum number of simultaneously active calls?

***Solution***:
1. Arguments in order calls are made for ``mystery(6)`` are 6,4,2,0
2. Return values in order calls finish for `mystery(6)` are:
	- mystery(0) returns 1
	- mystery(2) returns 3
	- mystery(4) returns 7
	- mystery(6) returns 13
3. The final returned value is the sum of all the positive integer numbers less than or equal to n with same parity as n added to 1 if n is positive. 
	For `mystery(6)` its 6+4+2+1= 13.   
	For `mystery(5)` its 5+3+1 = 9
4. Total of 4 function calls occur including the base case for `mystery(6)`
5. The recursion is linear, so no call finishes until the base case is reached. At that moment mystery(6), mystery(4), mystery(2), and mystery(0) are all on the stack at once.

### Question 2: Find the defect
```
def broken(n):    
	if n == 0:        
		return 0    
	return n + broken(n + 1)
```
Explain precisely why this function fails for a positive integer input. Identify the termination condition, the direction of progress, and the change needed to make the recursion terminate for positive integers.
Do not merely say “infinite recursion.”
***Solution***:
For positive integer input the recursive algorithm given above fails as the recursive calls do not progress in the direction of the base case and the base case i.e. for positive integer input the recursive algorithm increments the input number by 1 for each recursive call leaving it no way to reach the base case where $n==0$. The termination condition is strictly when n becomes equal to zero even though this works for negative integer inputs this doesn't work for positive integer inputs.
The change needed to be made to make the program terminate for positive integers and return the sum of negative integers leading up to n for negative integer inputs is:
```py
def broken(n):    
	if n >= 0:        
		return 0    
	return n + broken(n + 1)
```
This way we can return 0 for all positive integer inputs. If we want to keep the positive inputs in and return 0 for all negative inputs we make the following change:
```py
def broken(n):    
	if n <= 0:        
		return 0    
	return n + broken(n - 1)
```

### Question 3: Recursive function correctness
A function is intended to return the sum of all integers from 1 through n, where $n\geq 0$.
```
def total(n):    
	if n == 0:        
		return 0    
	return n + total(n - 1)
```
Give a concise correctness argument covering:
- the base case,
- the assumption about the smaller recursive call,
- why the recursive result is correct,
- why the function terminates.
***Solution***:
- Base case of the above algorithm is when n becomes equal to 0 where on this condition satisfying we immediately return 0 but this would fail for negative integer inputs so the correction for the base case for intended working of the algorithm is using the base case condition as `n<=0`. Since the problem mentions that $n \ge 0$, changing base case condition to `n <= 0` is a defensive choice that makes negative inputs return 0 instead of recursing forever.
- **Assumption**: 
  Assume that for some k ≥ 1, 
  the smaller call `total(k - 1)` correctly returns 1 + 2 + ... + (k - 1). 
  This is valid because k - 1 ≥ 0, so it lies within the function’s domain.
- **Correctness Proof:** 
  For n = k, the function returns `k + total(k - 1)`. 
  By the hypothesis this equals k + (1 + 2 + ... + (k - 1)) = 1 + 2 + ... + k. 
  This is exactly the required sum, so correctness for k - 1 implies correctness for k. 
  By mathematical induction, `total(n)` is correct for all n ≥ 0.
- **Termination:** Each recursive call reduces n by exactly 1, so n is a strictly decreasing sequence of non-negative integers. Such a sequence cannot decrease forever, so it must reach 0, where the base case returns without recursing. Hence the function terminates after exactly n + 1 calls.
- **NOTE**: If you do use `n <= 0`, the argument above still holds for n ≥ 0, and the extra condition just defines the behavior for negative inputs (returning 0) as a design decision. Alternatively, you could keep `n == 0` and raise an error for n < 0, which is often better practice because it signals misuse instead of silently returning a value.

### Question 4: Call-stack space versus total work
For the function in Question 3:
```
def total(n):    
	if n == 0:        
		return 0    
	return n + total(n - 1)
```
1. State its tight time complexity.
2. State its auxiliary space complexity, including the call stack.
3. Explain why its total time is not the same thing as its maximum stack depth.
4. What changes in the stack-depth analysis if each call makes two recursive calls on \(n-1\), rather than one?

***Solution***:
1. Time complexity: $\Theta(n)$ 
   Recurrence Relation: T(n) = T(n-1) + c
   T(n) = T(n-1) + c
   T(n) = T(n-k) + kc
   T(n) = T(0) + nc
   T(n) = $\Theta(n)$ 
2. Auxiliary Space Complexity: $\Theta(n)$ 
   Auxiliary space complexity is given by the number of active calls at the deepest point. In the above case there are n+1 active calls at the deepest point and each frame uses constant space. Thus Auxiliary Space Complexity is $(n+1)\times\Theta(1)=\Theta(n)$.
3. Time counts the _total work done over the whole execution_, summed across every call that ever happens. Stack depth counts the _largest number of calls alive at the same instant_
   Stack space is reused: once a call returns, its frame is popped and the space can be reused by later calls. 
4. Say the function is `f(n) = f(n-1) + f(n-1)`
   **Stack depth stays Θ(n).** The first call `f(n-1)` runs to completion and returns before the second one starts. At any moment the active calls form a single path from the root to the current call, and the longest such path has length n + 1. So auxiliary space remains Θ(n).
   **Time changes drastically.** T(n) = 2T(n-1) + c, which gives Θ(2ⁿ) calls (the recursion tree has 2ⁿ⁺¹ - 1 nodes).

## Part B: Forming recurrence relations
For each question, write the recurrence first, identify the non-recursive work, and then derive the tight time complexity.
### Question 5: One call, decrement by one
```
def f(n):    
	if n <= 1:        
		return    
	f(n - 1)
```
Determine:
- the recurrence,
- the number of recursive levels,
 - tight time complexity,   
- auxiliary stack-space complexity.
***Solution***:
- Recurrence: $T(n) = T(n-1) + \Theta(1)$
- Number of Recursive Levels: n
- Time complexity: $\Theta(n)$
  T(n) = T(n-1) + c
  T(n) = T(n-2) + 2c
  T(n) = T(n-k) + kc
  T(n) = T(1) + (n-1)c
  $T(n) = \Theta(n)$
- Auxiliary Stack-space Complexity: $\Theta(n)$
  Number of Active calls at deepest point: n
  Space used by each Frame: $\Theta(1)$
  Space complexity: $n * \Theta(1) = \Theta(n)$

### Question 6: One call, halve the input
```
def g(n):    
	if n <= 1:        
		return    
	g(n // 2)
```
***Solution***:
- Recurrence: $T(n) = T(n/2) + \Theta(1)$
- Number of Recursive Levels: $log_2 n$
- Time complexity: $\Theta(log_2 n)$
  T(n) = T(n/2) + c
  T(n) = T(n/4) + 2c
  $T(n) = T(n/2^k) + kc$
  Base condition achieved when $n/2^k$ equals 1.
  Hence we can say that $k = log_2 n$
  $T(n) = \Theta(k) = \Theta(log_2 n)$
- Auxiliary Stack-space Complexity: $\Theta(log_2 n)$
  Number of Active calls at deepest point: $log_2 n$
  Space used by each Frame: $\Theta(1)$
  Space complexity: $log_2 n * \Theta(1) = \Theta(log_2 n)$

### Question 7: Recursive calls inside a loop
```
def h(n):    
	if n <= 1:        
		return    
	for _ in range(n):        
		do_constant_work()    
	h(n // 2)
```
Derive the recurrence and solve it. Then determine the maximum recursive stack depth.
Your reasoning must account for the loop's cost at each recursive level.
***Solution***:
- Recurrence: $T(n) = T(n/2) + \Theta(n)$ 
- Number of Recursive levels: $\Theta(log_2 n)$
- Time complexity: $\Theta(n)$
  $T(n) = T(n/2) + cn$
  $T(n) = T(n/4) + c*(n + \frac n 2)$
  $T(n) = T(n/8) + c*(n + \frac n 2 + \frac n 4)$
  $T(n) = T(n/2^k) + c*(n + \frac n 2 + \frac n 4 + \dots + 1)$
  $T(n) = T(n/2^k) + cn*(1 + \frac 1 2 + \frac 1 4 + \dots + \frac 1 n)$
  Since we know $(1 + \frac 1 2 + \frac 1 4 + \dots + \frac 1 {2^k})$ is a Geometric Progression sum is given by
  $\frac {a(1 - r^n)} {1-r} = \frac {1*(1 - {\frac 1 2}^k)} {1 - \frac 1 2} = 2(1 - \frac 1 {2^k})$ 
  For very large k we can say that the sum of GP is $=2-\frac1{2^k}<2$, and ≥1
  $cn\le T(n)-T(n/2^k)<2cn$, so $T(n)=\Theta(n)$
- Maximum Recursive Stack Depth: $\Theta(log_2 n)$

### Question 8: Two recursive calls
```
def p(n):    
	if n <= 1:        
		return    
	p(n // 2)    
	p(n // 2)
```
Determine:
1. The recurrence.
2. The number of leaves in the recursion tree, asymptotically.
3. The tight time complexity.
4. The maximum call-stack space.
5. Why “two recursive calls means exponential time” is not a valid general rule.

***Solution***:
1. Recurrence: $T(n) = 2T(n/2) + \Theta(1)$ 
   Here a = 2, b = 2
2. Number of leaves: $n^{log_ba} = n^{log_2 2} = n^1 = n$  
3. Time Complexity: $\Theta(n)$
   $T(n) = 2T(n/2) + c$
   $T(n) = 4T(n/4) + c + 2c$
   $T(n) = 8T(n/8) + c + 2c + 4c$
   $T(n) = 2^kT(n/2^k) + c + 2c + 4c + \dots + 2^{k-1}c$
   $T(n) = 2^kT(n/2^k) + c*(1 + 2 + 4 + \dots + 2^{k-1})$
   Since $(1 + 2 + 4 + \dots + 2^{k-1})$ is a GP, Its sum is given by
   $\frac {a(1-r^n)} {1-r} = \frac {(1 - 2^{k-1})} {1 - 2} = 2^{k-1} - 1$
   $T(n) = 2^kT(n/2^k) + c*2^{k-1}$
   At $k = log_2 n$: $2^k = n$, so T(n) = n·T(1) + c(n - 1) = Θ(n)
   $T(n) = \Theta(n)$ 
4. Maximum call-stack space: $log_2 n$
5. The statement two recursive calls means exponential time is false as the time complexity depends upon number of sub-problems, size of each sub-problem and the local work of an recursive algorithm instead of only depending on the number of recursive calls. The above problem solves as a valid contradiction for the statement.

### Question 9: A deceptive change
Compare the following implementations:
```
def a(n):    
	if n <= 1:        
		return    
	a(n // 2)    
	a(n // 2)
```

```
def b(n):    
	if n <= 1:        
		return    
	b(n - 1)    
	b(n - 1)
```
For each function, state the recurrence, tight time complexity, and auxiliary stack-space complexity. Explain which structural difference changes the time bound.
***Solution***:
For function `a(n)`:
- Recurrence Relation: $T(n) = 2T(n/2) + \Theta(1)$
- Time Complexity: $\Theta(n)$
   $T(n) = 2T(n/2) + c$
   $T(n) = 4T(n/4) + c + 2c$
   $T(n) = 8T(n/8) + c + 2c + 4c$
   $T(n) = 2^kT(n/2^k) + c + 2c + 4c + \dots + 2^{k-1}c$
   $T(n) = 2^kT(n/2^k) + c*(1 + 2 + 4 + \dots + 2^{k-1})$
   Since $(1 + 2 + 4 + \dots + 2^{k-1})$ is a GP, Its sum is given by
   $\frac {a(1-r^n)} {1-r} = \frac {(1 - 2^{k-1})} {1 - 2} = 2^{k-1} - 1$
   $T(n) = 2^kT(n/2^k) + c*2^{k-1}$
   At $k = log_2 n$: $2^k = n$, so T(n) = n·T(1) + c(n - 1) = Θ(n)
   $T(n) = \Theta(n)$ Since we can say that $k = log_2 n$
-  Maximum call-stack space: $log_2 n$

For function `b(n)`:
- Recurrence Relation: $T(n) = 2T(n - 1) + \Theta(1)$
- Time Complexity: $\Theta(2^n)$
   $T(n) = 2T(n - 1) + c$
   $T(n) = 4T(n - 2) + c + 2c$
   $T(n) = 8T(n - 3) + c * (1+2+4)$
   after $k=n-1$ expansions the argument reaches 1, so
   $T(n) = 2^{n-1}T(1) + c * (1+2+4+\dots+2^{n-2})$
   Since $(1+2+4+\dots+2^{n-2})$ is a GP its sum is given by
   $\frac {a(1-r^n)} {1-r} = 2^{n-2} - 1$
   $T(n) = \Theta(2^n)$
-  Maximum call-stack space: $\Theta(n)$

## Part C: Expansion method
For these questions, do not jump directly to a memorized result. Expand the recurrence until the pattern is visible, then justify the tight bound.
### Question 10: Linear expansion
Given
$T(n)=T(n-1)+3,\qquad T(1)=2$
1. Expand at least four times.
2. Give the general expression after \(k\) expansions.
3. Determine the number of expansions required to reach the base case.
4. Derive the tight time complexity.

***Solution***:
1. Expansion:
	1. $T(n) = T(n-1) + 3$
	2. $T(n) = T(n-2) + 6$
	3. $T(n) = T(n-3) + 9$
	4. $T(n) = T(n-4) + 12$
2. General Expression: $T(n) = T(n-k) + 3*k$
3. Number of expansions to reach base case: n-1 expansions 
4. Time complexity: 
	1. $T(n) = T(n-k) + 3*k$
	2. $T(n) = T(1) + 3*(n-1)$
	3. $T(n) = 2 + 3*(n-1)$
	4. $T(n) = \Theta(n)$

### Question 11: Triangular work
Given
$T(n)=T(n-1)+4n,\qquad T(1)=1$
Expand the recurrence into a summation. Evaluate or bound the summation tightly, and derive $\Theta(\cdot)$. Explain why counting only the number of recursive calls would produce an incomplete analysis.
***Solution***:
$T(n) = T(n-1) + 4n$
$T(n) = T(n-2) + 4n + 4(n-1)$
$T(n) = T(n-k) + 4n + 4(n-1) + 4(n-2)$
$T(n) = T(1) + 4*(n+ (n-1) + (n-2) + \dots + (2))$
$T(n) = 1 + 4(2 + \dots + n-1 + n)$
$T(n) = 1 + 4((n^2/2 + n/2)-1)$
$T(n) = 2n^2 + 2n - 3$ 
$T(n) = \Theta(n^2)$
There are $\Theta(n)$ recursive calls, but each call performs a different amount of work. The total work is $T(n) = \Theta(n^2)$.

### Question 12: Halving with constant work
Given
$T(n)=T(n/2)+5,\qquad T(1)=1$
Assume \(n\) is a power of two.
1. Expand the recurrence.
2. Solve for the number of levels.
3. Express \(T(n)\) in terms of \(\log_2 n\).
4. State the tight complexity.

***Solution***:
1. Expansion:
	1. $T(n) = T(n/2) + 5$
	2. $T(n) = T(n/4) + 5*2$
	3. $T(n) = T(n/8) + 5*3$
	4. $T(n) = T(n/2^k) + 5*k$
	5. $k=\log_2 n$ with $T(n)=T(1)+5\log_2 n=1+5\log_2 n=\Theta(\log n)$
	6. $T(n) = \Theta(log_2 n)$
2. Number of levels 
   Given by $n/2^k = 1$ i.e. $n = 2^k$
   Logging on both sides: $k = log_2 n$
3. Proved above in 1
4. $T(n) = \Theta(log_2 n)$

### Question 13: Halving with linear work
Given
$T(n)=T(n/2)+3n,\qquad T(1)=1$
1. Expand until the base case.
2. Write the resulting summation.
3. Establish an upper bound using a geometric series.
4. Establish why the total is also at least proportional to \(n\).
5. Conclude the tight complexity.
Your answer must explain why multiplying \(n\) by the number of levels gives the wrong bound.

***Solution***:
1. Expansion:
	1. $T(n)=T(n/2)+3n$
	2. $T(n)=T(n/4)+3(n + (n/2))$
	3. $T(n)=T(n/8) +3(n + (n/2) + (n/4))$
	4. $T(n)=T(n/2^k) + 3n*(1 + (1/2) + \dots + (1/2^{k-1}))$
	   Where $(1 + (1/2) + \dots + (1/2^{k-1}))$ is a GP whose sum is $<2$ (Proved in a previous sum)
	5. $T(n) < 1 + 6n$
	6. $T(n) = \Theta(n)$
2. Recursion Summation: $T(n) = T(n/2^k) + 3n*\sum_{i=0}^{i=k-1} 1/2^i$
3. We know the formulae for sum of GP: $\sum_{i=0}^{i=n}r^i = \frac {1-r^n} {1-r}$
   In the above case:  $\sum_{i=0}^{i=n}{\frac 1 2}^i = \frac {1-{\frac 1 2}^n} {1-{\frac 1 2}} = 2(1 - \frac 1 {2^k}) < 2$
   So we can say: T(n) < 1 + 6n
   So: T(n) = O(n)
4. $T(n)=T(n/2)+3n\geq 3n$
   Hence we can say $T(n) = \Omega(n)$
5. Tight Complexity: $T(n)=\Theta(n)$
   - Upper bound: $T(n)=O(n)$
   - Lower bound: $T(n)=\Omega(n)$


### Question 14: Two recursive halves plus combining work
Given
$T(n)=2T(n/2)+n,\qquad T(1)=1$
Assume \(n\) is a power of two.
1. Expand the recurrence for at least three levels.
2. At level \(j\), state the number of subproblems and the size of each.
3. Calculate the total nonrecursive work at a general level.
4. Count the number of levels.
5. Include the leaf work and derive the tight time complexity.
A statement such as “this is merge sort, so it is \(O(n\log n)\)” is not a derivation.

***Solution***:
1. Expansion:
	1.  $T(n)=2T(n/2)+n$
	2. $T(n)=4T(n/4)+2n$
	3. $T(n)=8T(n/8)+3n$
	4. $T(n)=2^kT(n/2^k)+(k)n$
2. At j level
	1. Number of sub-problems: $2^j$
	2. Size of sub-problem: $\frac n {2^j}$
3. Total non-recursive work at any given level k is $\Theta(n)$
4. Total number of levels: $log_2 n$
5. Since $k = log_2 n$, We can say that at $k=\log_2 n$,  
   $T(n)=n\,T(1)+n\log_2 n=\Theta(n)+\Theta(n\log n)=\Theta(n\log n)$
   Number of Leaves: $n^{log_b a} = n^{log_2 2} = n^1 = n$

## Part D: Recognizing common recurrence patterns

### Question 15: Classify and justify
For each recurrence, give its tight time complexity and a brief justification.

| Label | Recurrence               |
| ----- | ------------------------ |
| A     | $T(n)=T(n-1)+\Theta(1)$  |
| B     | $T(n)=T(n-1)+\Theta(n)$  |
| C     | $T(n)=T(n/2)+\Theta(1)$  |
| D     | $T(n)=T(n/2)+\Theta(n)$  |
| E     | $T(n)=2T(n/2)+\Theta(1)$ |
| F     | $T(n)=2T(n/2)+\Theta(n)$ |
| G     | $T(n)=2T(n-1)+\Theta(1)$ |
For each one, identify the decisive feature: number of calls, input-size reduction, local work, or total work per level.
***Solution***:
- A: \(\Theta(n)\) — One call per level, \(n-1\) reduction, constant work; \(n\) levels.
- B: \(\Theta(n^2)\) — One call per level, linear local work; sum \(n+(n-1)+\cdots+1\).
- C: \(\Theta(\log n)\) — One call per level, halving input, constant work; logarithmic levels.
- D: \(\Theta(n)\) — One call per level, halving input, linear local work; geometric sum \(n+n/2+n/4+\cdots\).
- E: \(\Theta(n)\) — Two calls per level, halving input, constant local work; total nodes in the recursion tree are \(\Theta(n)\).
- F: \(\Theta(n\log n)\) — Two calls per level, halving input, linear local work; each level costs \(\Theta(n)\) across \(\Theta(\log n)\) levels.
- G: \(\Theta(2^n)\) — Two calls per level, input decreases by one; the number of calls doubles, producing exponential growth.
Key distinction: Number of calls and input-size reduction determine the recursion-tree shape; local work determines the cost per call; total work per level determines how the costs accumulate.

### Question 16: Fibonacci-style recursion
Consider:
```
def fib(n):    
	if n <= 1:        
		return n    
	return fib(n - 1) + fib(n - 2)
```
Answer all parts:
1. Write a recurrence for its running time.
2. Explain why the same subproblems are solved repeatedly.
3. State its tight time complexity in terms of \(\varphi=(1+\sqrt5)/2\), under the usual constant-cost model.
4. State the auxiliary stack-space complexity.
5. If memoization is added so that each distinct `fib(k)` is computed once, what are the new time and auxiliary space complexities?
6. Why does memoization reduce the time without necessarily reducing the maximum recursion depth?

***Solution***:
1. Running-time recurrence:  $T(n)=T(n-1)+T(n-2)+\Theta(1)$ with $T(0),T(1)=\Theta(1)$.
2. Repeated subproblems: Both recursive branches overlap. For example, `fib(n-2)` is computed directly and again while evaluating `fib(n-1)`.
3. Tight time complexity:  $\boxed{\Theta(\varphi^n)},\qquad \varphi=\frac{1+\sqrt5}{2}$  
The recurrence follows Fibonacci growth, whose dominant exponential factor is $\varphi^n$.
4. Auxiliary stack space: $\boxed{\Theta(n)}$  
   The deepest recursive chain decreases the argument by one until reaching a base case.
5. With memoization: Time becomes $\boxed{\Theta(n)}$, and auxiliary space remains $\boxed{\Theta(n)}$. 
   Each of the n+1 distinct values is computed once and stored.
6. Why recursion depth remains unchanged: Memoization avoids recomputing results, but the initial recursive descent can still follow `fib(n) → fib(n-1) → … → fib(1)`. Therefore, maximum stack depth remains $\Theta(n)$, even though the total work decreases.

## Part E: Analyze code, not just equations
### Question 17: Mixed recursive work
Analyze the following code:
```
def r(n):    
	if n <= 1:        
		return    
	for _ in range(n):        
		do_constant_work()    
	r(n // 2)    
	r(n // 2)
```
Give:
- the recurrence,
- the total work per recursion-tree level,
- the number of levels,
- the tight time complexity,
- the maximum auxiliary stack-space complexity.
Pay close attention to how many subproblems exist at each level.
***Solution***:
1. Running-time recurrence:  $T(n)=2T(\lfloor n/2\rfloor)+\Theta(n)$, with $T(0),T(1)=\Theta(1)$.
2. Total work per recursion-tree level:  At level i, there are $2^i$ subproblems of size approximately $n/2^i$. Therefore, total work is $2^i\cdot\Theta(n/2^i)=\boxed{\Theta(n)}$  
3. Number of levels: $\boxed{\Theta(\log n)}$ 
   Each recursive call halves the input until it reaches the base case.
4. Tight time complexity: $\boxed{\Theta(n\log n)}$ 
   Each of the $\Theta(\log n)$ levels performs $\Theta(n)$ total work.
5. Maximum auxiliary stack-space complexity: $\boxed{\Theta(\log n)}$
   The deepest active recursive chain halves the input at every step. Although there are two recursive calls per function, they execute sequentially, so both subtrees are not simultaneously held on the call stack.

### Question 18: Recursive calls inside a loop
```
def s(n):    
	if n <= 1:        
		return    
	for _ in range(n):        
		s(n // 2)
```
1. Write the recurrence, including the number of recursive calls.
2. Explain why it differs from Question 6 and Question 8.
3. Derive the tight time complexity.
4. Determine the maximum recursive stack depth.
5. Explain why the number of calls made by one function invocation is not the same as the total number of calls in the entire execution.

***Solution***:
1. Running-time recurrence:  $T(n)=nT(\lfloor n/2\rfloor)+\Theta(n)$
   Each invocation makes n recursive calls, each with input size $\lfloor n/2\rfloor$.
2. Why it differs from Questions 6 and 8:
	- Question 6: One recursive call, halving the input: $T(n)=T(n/2)+\Theta(1)$.
	- Question 8: Two recursive calls, halving the input: $T(n)=2T(n/2)+\Theta(1)$.
	- Question 18: \(n\) recursive calls, halving the input: $T(n)=nT(n/2)+\Theta(n)$.
3. Tight time complexity:  $\boxed{T(n)=2^{\Theta((\log n)^2)}}$  
   At level i, there are approximately $n^{\,i}/2^{i(i-1)/2}$ calls. The recursion depth is $\Theta(\log n)$, and multiplying the branching factors across levels gives  $\prod_{i=0}^{\Theta(\log n)-1}\frac{n}{2^i}=2^{\Theta((\log n)^2)}$.
   The loop's total work is dominated by the recursive calls.
4. Maximum recursive stack depth:  $\boxed{\Theta(\log n)}$  
   Each recursive call halves the input. The calls execute sequentially, so the stack depth follows one active recursive path rather than the total number of calls.
5. Why one invocation's calls differ from total calls:  
   One invocation makes \(n\) direct recursive calls, but each of those calls makes further recursive calls. The total number of calls includes every invocation throughout the entire recursion tree, so it is much larger than \(n\).
The ratio of calls between consecutive levels is $n/2^i \ge 2$ for $i<\log_2 n$, so the sum over levels is dominated by the last level (within a factor of 2)

### Question 19: Diagnose the incorrect claim
A student analyses this function:
```
def t(n):    
	if n <= 1:        
		return    
	do_linear_work(n)    
	t(n // 2)
```
They say:
> “There are \(\log n\) recursive calls, and each does \(n\) work, so the complexity is \(\Theta(n\log n)\).”

Identify the exact flaw. Then derive the correct tight time complexity using an explicit summation. State the auxiliary stack-space complexity separately.
***Solution***:
- **Flaw:** it’s true that there are about log n calls, but the work per call is not n. Call i works on size n/2^i, so the per-level work is n, n/2, n/4, …
- **Recurrence:** $T(n)=T(n/2)+cn$
- **Summation:** $T(n)=T(1)+cn\sum_{i=0}^{k-1}\frac1{2^i}=T(1)+cn\,(2-2^{1-k})$ with $k=\log_2 n$
- **Bounds:** $cn \le T(n)-T(1) < 2cn$, so $T(n)=\Theta(n)$
- **Stack space:** $\Theta(\log n)$, because the depth is the number of halvings.

## Part F: Transfer and implementation
### Question 20: Write a recursive implementation
Implement a recursive Python function:
```
def count_down_sum(n):    
	...
```
It must return
$n+(n-1)+\cdots+1$
for integer $n\geq 0$, with `count_down_sum(0) == 0`.
Provide:
1. The code.
2. A correctness explanation.
3. The recurrence for running time.
4. Tight time complexity.
5. Auxiliary stack-space complexity.
6. Two edge cases and their expected outputs.

***Solution***:
```py
def count_down_sum(n):
	if n<=0:
		return 0
	return n + count_down_sum(n-1)
```
2. Correctness explanation: The base case returns 0 when n = 0. For n > 0, the function adds n to the sum from n − 1 down to 1. Therefore, it returns n + (n − 1) + ... + 1.
3. Running-time recurrence: T(n) = T(n − 1) + Θ(1), with T(0) = Θ(1). Each invocation performs constant work and makes one recursive call.
4. Tight time complexity: Θ(n). There are n + 1 recursive invocations, each doing constant work.
5. Auxiliary stack-space complexity: Θ(n). The recursion depth grows linearly with n, and each active call uses constant stack space.
6. Two edge cases:
	- ``count_down_sum(0) returns 0``.
	- ``count_down_sum(1) returns 1``.
### Question 21: Correct the implementation
The following function is intended to compute \(2^n\) for integer $n\geq 0$:
```
def power_two(n):    
	if n == 0:        
		return 0    
	return 2 * power_two(n - 1)
```
Identify the bug. Correct the function and explain why the corrected base case is necessary. State the time and auxiliary space complexities of the corrected implementation.
***Solution***:
the bug is that the base case returns 0, but \(2^0=1\). Returning 0 causes every recursive call to return 0.
```py
def power_two(n):
    if n == 0:
        return 1
    return 2 * power_two(n - 1)
```
The corrected base case must return 1 because it represents \(2^0\). Each recursive call multiplies the result by 2, producing \(2^n\).
Time complexity: $\Theta(n)$, because there are n+1 recursive calls, each doing constant work.
Auxiliary stack-space complexity: $\Theta(n)$, because the recursion depth increases linearly with n.
### Question 22: Novel transfer challenge
Analyze the following without running it:
```
def u(n):    
	if n <= 1:        
		return    
	u(n // 2)    
	for _ in range(n):        
		do_constant_work()    
	u(n // 4)
```
Answer in this order:
1. Write the recurrence, making sure to represent both recursive calls accurately.
2. Expand the recurrence at least twice.
3. Identify the work performed outside recursive calls at each level or subproblem.
4. Determine the tight time complexity and justify it.
5. Determine the maximum call-stack space.
6. Explain which part of your reasoning would fail if you incorrectly treated the two recursive calls as having equal subproblem sizes.
Do not infer the answer solely from the number of recursive calls.

***Solution***:
1. Running-time recurrence: 
   $T(n)=T(\lfloor n/2\rfloor)+T(\lfloor n/4\rfloor)+\Theta(n)$, with $T(n)=\Theta(1)$ for $n\leq1$.
   There are two recursive calls, with different input sizes, and the loop performs $\Theta(n)$ work.
2. Expand the recurrence twice:
   Ignoring floors for readability:
   $T(n)=T(n/2)+T(n/4)+cn$
   $T(n)=T(n/4)+T(n/8)+cn/2+T(n/8)+T(n/16)+cn/4+cn$
   $T(n)=T(n/4)+2T(n/8)+T(n/16)+c(n+n/2+n/4)$.
   $T(n)=T(n/8)+3T(n/16)+3T(n/32)+T(n/64)+cn(1 + 1/2 +3/4+1/16)$.
3. Work outside recursive calls:
   Each invocation performs $\Theta(n)$ work in its loop. A subproblem of size m generates subproblems of sizes m/2 and m/4. Their combined size is 3m/4. Thus, the total work across successive levels decreases geometrically, apart from constant-cost base cases.
4. Tight time complexity:  $\boxed{\Theta(n)}$
   The total work across non-base levels is bounded by a geometric sum proportional to n. The base-case calls also contribute at most O(n) total work. Since the initial invocation alone performs $\Theta(n)$ work, the tight bound is $\Theta(n)$.
5. Maximum auxiliary stack-space complexity: $\boxed{\Theta(\log n)}$
   The deepest path follows the n/2 recursive calls until reaching the base case, giving logarithmic depth. The two recursive calls execute sequentially, so their stack frames are not all active simultaneously.
6. Treating both calls as size n/2 would incorrectly produce $T(n)=2T(n/2)+\Theta(n)$, giving $\Theta(n\log n)$. That assumes the total subproblem size remains approximately n per level. In reality, the child sizes sum to only 3n/4, so the total work decreases geometrically and the correct complexity is $\Theta(n)$.