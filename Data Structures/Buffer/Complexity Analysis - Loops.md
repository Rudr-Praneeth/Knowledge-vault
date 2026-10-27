# Complexity Analysis in Loops
TAGS: #DSA 
BUILT-ON: [[Complexity Analysis]]
ENABLES: - 
PREREQUSITIES: -

---
## Dependent Bound Nested Loops 
Dependent Bound Nested Loops are nested loops whose number of iterations of the internal loops are dependent upon the outer loop. The time complexity of Dependent Bound Nested Loops is calculated by expressing the iteration counts appropriately. 
Below are few solutions on calculating the _**Time Complexity**_ of Dependent Bound Nested Loops.

#### Lower Triangle Nested Loop
```py
for i in range(n):
    for j in range(i):
        work()
```
For ``i = 0``: Inner Executions is 0
For `i = 1`: Inner Executions is 1
Similarly, For `i = n`: Inner Executions n.
Therefore total number of executions is given by: $\sum_{k=0}^{k=n} k$ i.e. sum of natural numbers upto n. Which is given by: $$\frac {n(n-1)} {2} \rightarrow (\frac {n^2} {2}) - (\frac {n} {2}) $$
Ignoring the systemic constants and lower order terms we get: $$f(n) = Θ(n^2)$$

#### Upper Triangle Nested Loop
```py
for i in range(n):
    for j in range(i, n):
        work()
```
For `i = 0`: Inner Executions n
For `i = 1`: Inner Executions (n-1)
Similarly, For `i = n`: Inner Executions 0
Therefore the total number of executions is given by: $\sum_{k=0}^{k=n} (n-k)$ i.e. sum of natural numbers upto n calculated in reverse order.
It is given by: $$\frac {n(n-1)} {2} \rightarrow \frac {n^2} {2} - \frac {n} {2}$$
Ignoring the systemic constants and lower order terms we get:$$f(n) = Θ(n^2)$$

#### Triple Nested Loops
```py
for i in range(n):
    for j in range(i):
        for k in range(j):
            work()
```
The total work done is given by: $$\sum_{i=0}^{i=n} \sum_{j=0}^{j=i} \sum_{k=0}^{k=j}1$$
The $\sum_{k=0}^{k=j} 1$ resolves to `j`.
So we now have: $$\sum_{i=0}^{i=n} \sum_{j=0}^{j=i} j$$
The $\sum_{j=0}^{j=i} \: j$ resolves to $\frac {i(i-1)} {2}$
So we now have: 
$\sum_{i=0}^{i=n} \frac {i(i-1)} {2}$
$\frac {1} {2} \times (\sum_{i=0}^{i=n} i^2- \sum_{i=0}^{i=n} i)$                             Ignoring constants and Lower-order terms
$\sum_{i=0}^{i=n} i^2$                                                      Sum of squares = $\frac {n(n+1)(2n+1)} {6}$
$\frac {n(n+1)(2n + 1)} {6}$                                                Ignoring the constants and Lower-order terms
$f(n) = Θ(n^3)$


#### Shrinking Variables
```py
i = 1
while i < n:
    work()
    i *= 2
```
Let's assume the loop runs for k iterations.
Value of i after k iterations is given by: ${2^k}$
The loop terminates when the condition $n \le 2^k$ is satisfied
So, $n \le 2^k$                                                Logging on both sides with base 2
$log_2 n \le k$
$k=⌈log2​n⌉$
So we can say that $$f(n) = Θ(log_2 n)$$

#### Growing Variables
```py
i = n
while i > 1:
    work()
    i //= 2
```
Let the number of iteration of the loop be k.
The value of i after k iterations: $\frac n {2^k}$
The loop terminates when the condition $\frac {n} {2^k} \le 1$ is satisfied
So, $n \le 2^k$                                                 Logging on both sides with base 2
$log_2 n \le k$
$k=⌈log2​n⌉$
So we can say that $$f(n) = Θ(log_2 n)$$

#### Growing Variables in Increasing Amount
```py
i = 0
while i < n:
    work()
    i += i + 1
```
Lets assume that the loop terminates after k iterations.
Tracing the value of i: 0, 1, 3, 7, 15, ...
Therefore we can say $i = 2^k -1$.
The loop terminates when the condition $n \le (2^k - 1)$ is satisfied.
Ignoring the constants: $n \le 2^k$
Logging on both sides with base 2: $log_2 n \le k$
So we can say that $k=⌈log2​n⌉$
Hence $$f(n) = Θ(log n)$$

#### Mixed Linear and Logarithmic Loops
```py
for i in range(n):
    j = 1
    while j < n:
        work()
        j *= 2
```
Outer Loop: Θ(n)
Inner Loop: Θ(log n)
Since the above nested loop algorithm contains independent bound loops i.e. loops where the internal loop is not depended on the value of the outer loop we can calculate the total work by multiplying the bounds.
Therefore, $$f(n) = Θ(n\: log n)$$
