# Foundations - Complexity Analysis
TAGS: #DSA #TEST
BUILT-ON: [[DSA Fundamentals]] [[Complexity Analysis]]
ENABLES: - 
PREREQUSITIES: - 

---
## PROBLEMS
#### ~={purple}***PROBLEM 1***=~: Bound Classification
For each statement, determine whether it is **true or false**.
1. $n^2 = O(n^3)$
2. $n^3 = O(n^2)$
3. $n^2 = \Omega(n)$
4. $n^2 = \Theta(n^3)$
5. $3n^2+7n+20=\Theta(n^2)$
6. $\log n = O(\sqrt n)$

***SOLUTION***:
1.  True, $O(n^3)$ is a valid loose upper bound for $f(n) = n^2$. 
	   **PROOF**:
	   - We can represent the f(n) and g(n) beyond a point $n_0 = 1$ as $n^2 \le n^3$ 
	   - For a valid pair $(n_0 = 1, c = 1)$ and hence we can say that g(n) is a valid upper bound of the growth function f(n).
2.  False, $O(n^2)$ is not a valid upper bound for $f(n) = n^3$. 
	   **PROOF**:
	   - There exists no valid pair $(n_0, c)$ such that both $n_0, c$ are greater than 0 and for which we can represent the f(n) and g(n) as $n^2 \le c*n^3$
	   - Thus we can say that the g(n) i.e. the proposed upper bound is not a valid upper bound for the growth in analysis.
3.  True, $\Omega(n)$ is a valid loose lower bound for $f(n) = n^2$. 
	   **PROOF**: 
	   - We can represent the f(n) and g(n) beyond a point $n_0 = 1$ as $n^2 \ge n$
	   - For a valid pair $(n_0 = 1, c = 1)$ and hence we can say that g(n) is a valid lower bound of the growth function f(n).
4.  False, $\Theta(n^3)$ is an invalid tight bound for $f(n) = n^2$. 
	   **PROOF**:
	   - For a proposed tight bound to be valid it should be a valid upper bound and a valid lower bound of the growth function in analysis. i.e. can be represented as $c_1\times g(n) \le f(n) \le c_2 \times g(n)$.
	   - UPPER BOUND CHECK: A valid pair $(n_0 = 1, c_2 = 1)$ exists such that beyond the point $n_0$ we can represent the f(n) and g(n) such that: $n^2 \le n^3 * 1$. Hence we say say that the g(n) is a valid upper bound
	   - LOWER BOUND CHECK: No valid pair exists such that beyond the point $n_0$ we can represent the f(n) and g(n) such that: $n^2 \ge c_1 * n^3$. Hence we can say that g(n) is not a valid upper bound for f(n).
	   - Hence g(n) is not a valid tight bound for the growth function under analysis and hence $n^2 = \Theta(n^3)$ is false.
5.  True, $\Theta(n^2)$ is a valid tight bound for $f(n) = 3n^2+7n+20$. 
	   **PROOF**:
	   - For g(n) to be a valid tight bound for the f(n) growth under analysis it should be a valid loose bound and a valid upper bound of the growth function in analysis i.e. can be represented as $c_1\times g(n) \le f(n) \le c_2\times g(n)$.
	   - A valid pair $(n_0 = 1, c_1 = 3, c_2 = 30)$ exists such that we can represent f(n) sandwiched between constant multiples of g(n) i.e. $3 \times n^2 \le 3n^2+7n+20 \le 30 \times n^2$. 
6.  True, $O(\sqrt n)$ is a valid loose upper bound for $f(n) = \log n$. 
	   **PROOF**:
	   - Since we know that for sufficiently large n, a power of logarithm of input size grows slower than a power of input size we can represent the above as $\log n \le \sqrt n$ 
	   - And hence we can say that a valid pair $(n_0 = 1, c = 1)$ and thus g(n) is a valid upper bound of f(n)

---
#### ~={purple}***PROBLEM 2***=~: Prove formally that:
$5n^2+3n+17=O(n^2)$ 
***SOLUTION***:
To prove the above equation, we need to show that beyond a point $n_0$ we can represent f(n) i.e. the growth function in analysis and g(n) i.e. the proposed upper bound as follows: $f(n) \le c \times g(n)$, this proves that f(n) grows slower than g(n) and g(n) is a valid upper bound of f(n).
Let's consider $n_0 = 1$ i.e. for all n beyond **n>1** we can say that
1. $5n^2 \le 5n^2$
2. $3n \le 3n^2$
3. $17 \le 17n^2$
Combining the above equations we get,
$5n^2 + 3n + 17 \le 5n^2 + 3n^2 + 17n^2$
$5n^2 + 3n + 17 \le 25n^2$
Therefore there exists a valid pair $(n_0 = 1, c = 25)$ for which we can show that f(n) grows slower than g(n) as n tends to infinity.
Hence Proved.

---
#### ~={purple}***PROBLEM 3***=~: Is the following statement true?
$2n^2+100n+500=\Theta(n^3)$
***SOLUTION***:
To prove the above equation, we need to show that beyond a point $n_0$ we can represent f(n) i.e. the growth function in analysis and g(n) i.e. the proposed tight bound as follows: $c_1 \times g(n) \le f(n) \le c_2 \times g(n)$, this proves that f(n) sandwiched between constant multiples of g(n).
We can prove a proposed tight bound is a valid tight bound for the growth function in analysis if it is both a valid upper bound and a valid lower bound for the growth function in analysis.
Let's prove that g(n) is a valid upper bound first.
Let's consider $n_0 = 1$ i.e. for all n beyond **n>1** we can say that
1. $2n^2 \le 2n^3$
2. $100n \le 100n^3$
3. $500 \le 500n^3$
Combining the above equations we get,
$2n^2 + 100n + 500 \le 2n^3 + 100n^3 + 500n^3$
$2n^2 + 100n + 500 \le 602n^3$
Therefore there exists a valid pair $(n_0 = 1, c_2 = 602)$ for which we can show that f(n) grows slower than g(n) as n tends to infinity.

Let's now prove that g(n) is a valid lower bound.
$2n^2 + 100n + 500 \ge c_1 \times n^3$                                       Dividing both sides by $n^3$
$\frac 2 n + \frac {100} {n^2} + \frac {500} {n^3} \ge c_1$                                                     As $n \rightarrow \infty$, we can say that,
$0 \ge c_1$
But this contradicts the condition that $c_1, c_2 > 0$. Hence we can say that $n^3$ is not a valid lower bound for the growth function in analysis.
Hence we can say that the above statement is **FALSE**.

---
#### ~={purple}***PROBLEM 4***=~: Suppose:
$T(n)=f(n)+O(n^3)$ and $f(n)=2n^2+2$
Determine the tightest asymptotic characterization of \(T(n)\).
Then explain **why** the $O(n^3)$ term determines the final upper-order growth.
If instead $f(n)=7n^4+2$, what would happen?
***SOLUTION***:
 - DERIVATION OF TIGHTEST ASYMTOTIC CHARACTERIZATION WHEN $f(n) = 2n^2 + 2$
	   It is not possible to determine the tightest asymptotic characterization of T(n), which for $f(n) = 2n^2 + 2$ comes out to be $T(n) = O(n^3) + 2n^2 + 2 \implies (c\times n^3) + 2n^2 + 2$. Since $O(n^3)$ simply tells us about the upper bound of the algorithm not whether the proposed upper bound is tight upper bound or loose upper bound. 
	   Thus determining the tightest asymptotic bound is not possible in this case 
	   For example, both of these are consistent with the statement:
	   $T_1(n)=2n^2+2+0=\Theta(n^2)$
	   and
	   $T_2(n)=2n^2+2+n^3=\Theta(n^3)$.
	   Therefore, the tight bound cannot be determined from the information provided. We can conclude $T(n)=O(n^3)$, but we cannot conclude $T(n)=\Theta(n^3)$.
 - DERIVATION OF TIGHTEST ASYMTOTIC CHARACTERIZATION WHEN $f(n) = 7n^4 + 2$
	   In the case of $f(n) = 7n^4 + 2$ the term $n^4$ dominates enabling the derivation of the tightest asymptotic bound which in the current case is $n^4$. Therefore we can say that $T(n) = \Theta(n^4)$
	   By the definition of Big-O, the additional term has magnitude at most $cn^3$ for some constant c>0and sufficiently large n. Since $n^3$ grows more slowly than $n^4$, that additional term cannot cancel the dominant $7n^4$ term for sufficiently large n.

---
#### ~={purple}***PROBLEM 5***=~:An algorithm performs three phases sequentially:
- Phase A takes $\Theta(n)$
- Phase B takes $\Theta(n^2)$
- Phase C takes $\Theta(\log n)$
What is the total complexity?
Then consider:
- Phase A: $\Theta(n^3)$
- Phase B: $\Theta(n^2\log n)$
- Phase C: $\Theta(2^n)$
What is the total complexity?
***SOLUTION***:
Since the three phases are sequentially ran we can say that the total complexity of these algorithms is the sum of works done by each phase, with the highest order term dominating the expression.
For **Case 1**, 
Total Time complexity = $\Theta(n) + \Theta(n^2) + \Theta(log n) = \Theta(n^2)$. Since $n^2$ term dominates the expression and can be considered as the final tightest bound of the entire algorithm.
For **Case 2**,
Total Time complexity = $\Theta(n^3) + \Theta(n^2 logn) + \Theta(2^n) = \Theta(2^n)$. Since $2^n$ being a exponential term grows faster when compared to $n^3 \: \& \:n^2logn$ which are polynomial terms. 

---
#### ~={purple}***PROBLEM 6***=~: Rank the following from **slowest-growing to fastest-growing**:
$n!,\quad 2^n,\quad n^3,\quad n\log n,\quad \sqrt n,\quad n^2,\quad \log n,\quad n^{1.5},\quad 1$
***SOLUTION***:
$1 < log n < \sqrt n < n < nlogn < n^{1.5} < n^2 < n^3< 2^n < n!$
Since $\log n = O(\sqrt n)$, multiplying both sides by $n$ gives $n\log n = O(n^{1.5})$.

---
#### ~={purple}***PROBLEM 7***=~: Determine the asymptotic relationship between each pair.
1. $n\log n \quad\text{vs}\quad n^{1.1}$
2. $(\log n)^3 \quad\text{vs}\quad \sqrt n$
3. $n^2 \quad\text{vs}\quad 2^n$

***SOLUTION***:
1. $n logn < n^{1.1}$. Since we know that logarithms grow slower than positive powers i.e. $log n = O(n^{0.1})$, Multiplying both sides by n we get: $n logn = O(n^{1.1})$
2. $(log n)^3 < \sqrt n$. Since we know that any constant power of logn grows slower than any positive power of n.
3. $n^2 < 2^n$. Since we know that polynomial terms grow slower than exponential terms .

---
#### ~={purple}***PROBLEM 8***=~: Analyse the time complexity:
```py
i = 1

while i <= n:
    j = i
    while j <= n:
        work()
        j *= 2
    i *= 2
```
***SOLUTION***:
Let's assume the outer loop runs for k iterations.
Inner loop: Starts at i i.e. $2^a$ and increases as a multiple of 2 until value is greater than n.
Since we know that Outer loop runs for k iterations we can say that $2^k > n$.
The inner loop initially starts at $2^a$ and runs for $k - a$ Iterations. 
Thus the total work is given by: $\sum_{a=0}^{a=k} (k-a)$ = k + (k-1) + ... + 2 + 1 = $\frac {k(k+1)} {2} \rightarrow \frac {k^2} 2 + \frac k 2$ 
Ignoring the constants and lower order terms we get, 
$T(n) = \Theta(k^2)$
$T(n) = \Theta((log n)^2)$

---
#### ~={purple}***PROBLEM 9***=~: Analyze the time complexity:
```py
j = 0

for i in range(n):
    while j < n and condition(i, j):
        work()
        j += 1
```
Determine the worst case time complexity
***SOLUTION***:
*Key Note*: The Inner loop variable j doesn't reset after each iteration of the outer loop and hence runs only once assuming for the worst case `condition(i,j)` always returns `True`. 
Since the inner loop runs only once till `j = n` and the Outer loop runs for n iterations we can conclude that the total work done by the program is `n (ITERATIONS OF OUTER LOOP) + n (ITERATIONS OF INNER LOOP)`.
Thus
$T(n) = \Theta(n)$

---
#### ~={purple}***PROBLEM 10***=~: Analyze:
```
for i in range(1, n + 1):
    j = i
    while j <= n:
        work()       
        j += i
```
Determine the tightest asymptotic complexity.
***SOLUTION***:
Outer Loop: $\Theta(n)$
Inner Loop for a fixed i increments j by i i.e. i, 2i, 3i, ...
The inner loop executes $\frac n i$ times.
Total Work: $\sum_{i=1}^{i=n} \frac n i \rightarrow n\times\sum_{i=1}^{i=n} \frac 1 i = n\times log n$
Therefore, time complexity is $\Theta(n logn)$

---
#### ~={purple}***PROBLEM 11***=~: Consider:
```
def search(arr, x):    
	for i in range(len(arr)):        
		if arr[i] == x:            
			return i    
	return -1
```
Give:
1. Best-case time complexity.
2. Worst-case time complexity.
3. Average-case time complexity **under the assumption that \(x\) is guaranteed to occur and every position is equally likely**.
Then explain why the average case cannot be specified without some assumption about the input distribution.

***SOLUTION***:
1. Best-case time complexity is $\Theta(1)$ for the input scenario where the first element of the array `arr` is equal to the element `x`
2. Worst-case time complexity is $\Theta(n)$ for the input scenario where either the element x present at the very end of the array or absent in the array.
3. Average-case time complexity under the assumption that x exists in the array and every position has an equal probability is $\frac {n+1} 2$. So the time complexity is $\Theta(n)$.
An assumption about the input distribution is essential to measure the average-case time complexity as average-case time complexity of a solution is given my a measure of computational resources required for an algorithm over all possible inputs, considering the likelihood of their occurrences. If the target may be absent, or positions are not equally likely, the expected cost depends on that model.

---
#### ~={purple}***PROBLEM 12***=~: Analyze the **worst-case** complexity:
```
for i in range(n):    
	for j in range(n):        
		if A[i] + B[j] > X:            
			break        
		work()
```
Is the worst case:
- \(O(n)\)?
- \(O(n\log n)\)?
- \(O(n^2)\)?
Or something else?
***SOLUTION***:
The worst-case complexity inputs for the algorithms is two arrays and a large X such that sum of no two elements of array are equal or greater than X. For example,
```py
A = [1,2,3,4,5]
B = [5,4,3,2,1]
X = 100
```
The worst-case time complexity of the algorithm is $\Theta(n^2)$ which is obtained by multiplying the bounds of the loops since the loops are independent bound loops.

---
#### ~={purple}***PROBLEM 13***=~:Compare these two programs.
**Program A**
```
j = 0
for i in range(n):    
	while j < n:        
		work()        
		j += 1
```
**Program B**
```
for i in range(n):    
	j = 0    
	while j < n:        
		work()        
		j += 1
```
Give the complexity of each.
Then explain **the exact reason** they differ.
***SOLUTION***:
**Program A**
They key note in program A is that the value of j is not reset for every iteration of the outer loop. Thus the inner loop runs only one time. Thus total time complexity of the program A is $\Theta(n)$
**Program B**
The value of j resets to 0 at the start of every iteration of the outer loop. Thus the total time complexity of this program is given by $\Theta(n) \text{(Outer Loop) }\times \Theta(n) \text{(Inner Loop)} = \Theta(n^2)$. 

---
#### ~={purple}***PROBLEM 14***=~: Analyze:
```
i = 1
while i <= n:    
	for j in range(i):        
		work()    
	i *= 2
```
Give the tight complexity.
***SOLUTION***:
The above problem has a dependent bound loops. Hence the total work is calculated using deriving a sum. 
The Inner loop does i number of iterations. Hence we can say that the work done by the Inner loop is $\Theta(i)$. 
Total work: $\sum_{\{1,2,4,8,....2^k\}} i = 1 + 2 + 4 + 8 + ... + 2^k$
This is a sum of Geometric Progression which is $2^{k+1} - 1$
where $2^k\le n<2^{k+1}$. Since $2^k=\Theta(n)$, total work is $\Theta(n)$.

---
#### ~={purple}***PROBLEM 15***=~: Analyze:
```
for i in range(1, n + 1):    
	j = 1    
	while j <= i:        
		work()        
		j *= 2
```
Give the tight complexity.
***SOLUTION***:
Inner Loop: $\Theta(log_2i)$
Total Work: 
$\sum_{i=1}^{i=n} log_2 i = log_2 1 + log_2 2 + log_2 3 + ... log_2 n$
$log(1\times2\times3\times...\times n) = log(n!)$
Therefore, $T(n) = \Theta(log(n!))$
A rigorous bound is obtained by comparing the sum with an integral, or by using Stirling's formula:
$\log(n!)=\Theta(n\log n)$.

---
#### ~={purple}***PROBLEM 16***=~: Consider:
```
def mystery(arr):    
	n = len(arr)    
	for i in range(n):        
		for j in range(i):            
			if arr[j] > arr[i]:                
				return True    
	return False
```
Determine:
1. Best-case complexity.
2. Worst-case complexity.
3. Is the worst-case complexity $\Theta(n^2)$? Prove your answer by identifying the number of comparisons in the relevant case.
4. Give a qualitative description of an input that produces the best case.

***SOLUTION***:
1. The best-case complexity is for the input scenario where the array's elements are all arranged in descending order. A best-case input has `arr[0] > arr[1]`, so the function returns at the first comparison. Hence the time complexity is $\Theta(1)$
2. The worst-case complexity is for the input scenario where the array's elements are all arranged in ascending order or are all equal. 
   Inner Loop: $\Theta(i)$ 
   Total work: $\sum_{i=0}^{i=n} i = \frac {n^2} 2 - \frac n 2$
   Hence the time complexity is $\Theta(n^2)$
3. Yes and proved above
4. The input that produces the best case is the elements of an array arranged such that element at position 1 is greater than element at position 0. Or simply the 2nd element of the array should be lesser than the first element of the array

---
#### ~={purple}***PROBLEM 17***=~: Analyze this code from first principles:
```
i = n
while i > 1:    
	j = 1    
	while j < i:        
		k = j        
		while k < i:            
			work()            
			k *= 2        
		j *= 2    
	i //= 2
```
Determine the tight asymptotic complexity.
***SOLUTION***:
Step 1: Fix one outer-loop iteration
Suppose the current value of `i` is mmm.
The `j` loop visits powers of two:
$1,2,4,8,\ldots <m$.
There are $\Theta(\log m)$ such values.

Step 2: Count the `k` loop for a fixed `j`
For a particular value $j=2^b$, `k` takes the values
$2^b,2^{b+1},2^{b+2},\ldots <m$.
The number of iterations is
$\Theta\left(1+\log\frac{m}{j}\right).$
This is not the same amount of work for every `j`: larger starting values produce fewer iterations.

Step 3: Sum across the `j` loop
Write m approximately as $2^q$. For $j=1,2,4,\ldots,2^{q-1}$, the inner-loop counts are proportional to
$q,\ q-1,\ q-2,\ \ldots,\ 1$.
Their sum is $q+(q-1)+\cdots+1 =\frac{q(q+1)}2 =\Theta(q^2)$.
Since $q=\Theta(\log m)$, one outer-loop iteration costs
$\Theta((\log m)^2)$.

Step 4: Sum across the outer loop
The outer variable approximately halves:
$n,\ \frac n2,\ \frac n4,\ \ldots,\ 2$.
There are $\Theta(\log n)$ outer iterations. Their costs are proportional to
$(\log n)^2,\ (\log n-1)^2,\ (\log n-2)^2,\ \ldots,\ 1$.
Hence the total work is $\sum_{r=1}^{\Theta(\log n)}r^2 =\Theta((\log n)^3)$.
So the answer is
$\boxed{\Theta((\log n)^3)}$

---
#### ~={purple}***PROBLEM 18***=~: Suppose you know only that:
$f(n)=O(n^2)$ and $g(n)=O(n^3)$
Determine which of the following statements are necessarily true.
1. $f(n)+g(n)=O(n^3)$ 
2. $f(n)g(n)=O(n^5)$ 
3. $f(n)+g(n)=\Theta(n^3)$ 
4. $f(n)g(n)=\Theta(n^5)$
For every statement, classify it as:
- necessarily true,
- not necessarily true.
Then **construct a counterexample** for at least one statement that is not necessarily true.

***SOLUTION***:
$f(n) = O(n^2)$ can be represented as $f(n) \le c_1\times n^2$.
$g(n) = O(n^3)$ can be represented as $g(n) \le c_2\times n^3$. 
1. $f(n) + g(n) \le c_1n^2 + c_2n^3$
   Ignoring the lower order terms $f(n)+g(n) \le c_2n^3$
   Thus we can say $f(n)+g(n) = O(n^3)$
2. $f(n)\times g(n) \le c_1c_2n^5$
   Thus we can say that $f(n)g(n) = O(n^5)$
3. An valid upper bound doesn't guarantee a tight bound. Thus we cannot say $f(n)+g(n)=\Theta(n^3)$ with the available information.
   The tight bound of g(n) may be $\Theta(n)$ where $O(n^3)$ is still a valid upper bound but f(n) + g(n) is not equal to $\Theta(n^3)$. 
4. Similarly we cannot say $f(n)g(n)=\Theta(n^5)$ from knowing that $f(n)g(n) = O(n^5)$ since we don't have enough information to suggest that $n^5$ is a valid tight bound.
   The tight bound of g(n) may be $\Theta(n)$ where $O(n^3)$ is still a valid upper bound but f(n) * * g(n) is not equal to $\Theta(n^5)$. 
Choose
$f(n)=1,\qquad g(n)=1$.
Satisfy both $f(n)=O(n^2)$ and $g(n)=O(n^3)$.
$f(n)+g(n)=2\ne\Theta(n^3)$
$f(n)g(n)=1\ne\Theta(n^5)$.

---
#### ~={purple}***PROBLEM 19***=~: Reason the following:
> "Algorithm A takes \(O(n^2)\) time and Algorithm B takes \(O(n^2)\) time. Therefore, if I combine them sequentially, the combined algorithm takes \(O(n^4)\) time."

Is this reasoning correct?
If not, state the correct general rule and explain exactly what went wrong.
Then answer:
Under what operation would $O(n^2)$ and $O(n^2)$ potentially combine to produce $O(n^4)$?
***SOLUTION***: 
Sequential phases add, so $O(n^2)+O(n^2)=O(n^2)$, not $O(n^4)$. A nested operation may multiply costs when one operation is performed repeatedly inside another, but even nested loops must be analysed using the actual execution counts and dependencies.

---

## RESULTS
| Problem                              | Verdict                 | Evaluation                                                                                                                                                                      |
| ------------------------------------ | ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Bound classification              | Mostly correct          | All six truth values are correct. The proof for statement 2, however, reverses the inequality being tested.                                                                     |
| 2. Formal Big-O proof                | Correct                 | Your \(c=25,\ n_0=1\) bound works. The proof is valid for all \(n\ge1\), not merely \(n>1\).                                                                                    |
| 3. Disprove \(\Theta(n^3)\)          | Correct                 | Both the upper-bound proof and the lower-bound contradiction are sound.                                                                                                         |
| 4. \(T(n)=f(n)+O(n^3)\)              | Correct                 | Excellent distinction between an upper bound and a tight bound. Your examples establish why \(\Theta(n^3)\) cannot be concluded.                                                |
| 5. Sequential phases                 | Correct                 | Both totals are correct: \(\Theta(n^2)\) and \(\Theta(2^n)\).                                                                                                                   |
| 6. Growth-rate ranking               | Correct                 | The order is correct. You included \(n\), although it was not in the supplied list; that does not undermine your ranking.                                                       |
| 7. Pairwise growth comparisons       | Correct, with rigor gap | All three comparisons are correct. Use asymptotic notation rather than treating \(O(\cdot)\) as an exact inequality between growth classes.                                     |
| 8. Two multiplicative loops          | Correct                 | The triangular sum yields \(\Theta((\log n)^2)\).                                                                                                                               |
| 9. Shared inner-loop variable        | Correct                 | Correctly recognized that `j` advances globally and never resets.                                                                                                               |
| 10. Harmonic-type loop               | Correct                 | The summation is right: \(\sum_{i=1}^n\lfloor n/i\rfloor=\Theta(n\log n)\).                                                                                                     |
| 11. Linear search cases              | Correct                 | Best, worst, and expected comparisons are correct under the stated distribution.                                                                                                |
| 12. Nested loop with `break`         | Correct                 | Your example realizes \(\Theta(n^2)\) work. The key is that the break need never execute.                                                                                       |
| 13. Compare shared vs reset variable | Correct                 | Correctly distinguished \(\Theta(n)\) from \(\Theta(n^2)\).                                                                                                                     |
| 14. Geometric sum                    | Correct                 | Correctly summed the powers of two to obtain \(\Theta(n)\).                                                                                                                     |
| 15. Sum of logarithms                | Correct                 | Correct use of \(\sum \log i=\log(n!)\) and \(\log(n!)=\Theta(n\log n)\).                                                                                                       |
| 16. Early-return nested loops        | Correct                 | Best case and worst case are correct. Your comparison count gives the right quadratic bound.                                                                                    |
| 17. Three-level mixed loop           | Correct                 | The per-level triangular sum and outer summation correctly yield \(\Theta((\log n)^3)\).                                                                                        |
| 18. Combining upper bounds           | Correct conclusions     | Your classifications are correct. The proof for statement 1 is a little too casual when it says to ignore lower-order terms, but the conclusion follows from the formal bounds. |
| 19. Sequential vs nested costs       | Correct                 | Correct rule and correct explanation of when multiplication may arise.                                                                                                          |

|Assessment dimension|Score|Judgment|
|---|---|---|
|Conceptual understanding|9/10|Strong distinction between upper and tight bounds|
|Intuition|9/10|Good understanding of dominant terms and loop behavior|
|Pattern recognition|9/10|Correctly identified geometric, harmonic, and logarithmic sums|
|Mathematical reasoning|8/10|One proof uses the wrong inequality; a couple of arguments need tighter justification|
|Correctness|9/10|Conclusions are overwhelmingly correct|
|Complexity analysis|9/10|Strong performance on the mixed loop problems|
|Explanation and communication|8/10|Generally clear, but some statements claim more than the displayed proof establishes|