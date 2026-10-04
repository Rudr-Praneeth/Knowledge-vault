# Time Complexity Analysis - Test
TAGS: #DSA #DSA-PROBLEMS 
BUILT-ON: [[Complexity Analysis]]
ENABLES: - 
PREREQUSITIES: - 

---
## Time Complexity Analysis
~={cyan}Problem=~: Calculate the time complexity for:
```py
def FUNCTION(n):
    for i in range(n):
        for j in range(i, n):
	        // CODE 
    return;
```
~={green}Solution=~:
The outer loop runs for n times.  
The inner loop range is not fixed and is dependent on the value of i.  
The inner loop iteration works as a function of i. 
	When i = 0: inner loop runs n - 0 = n times  
	When i = 1: inner loop runs n - 1 times  
	...  
	When i = n-1: inner loop runs n - (n-1) = 1 time
Total runs is the sum across all i = 0 to n-1:  
Therefore total runs is: n + (n-1) + (n-2)+ ..... + 1 times  i.e. (n* (n+1))/2 times
And since as:
	$n -> \infty$
	$n^2$ dominates the expression and therefore the f(n) = O(n^2)

---
Problem: 
