# LOGIC BUILDING PROBLEMS
TAGS: #DSA #DSA-PROBLEMS
BUILT-ON: [[DSA Fundamentals]]
ENABLES: - 
PREREQUSITIES: - 

---
## LOGIC BUILDING PROBLEMS
### CHECK EVEN OR ODD
~={purple}PROBLEM=~: Given a number n, check whether it is even or odd. Return true for even and false for odd.
~={green}SOLUTION=~
`[ NATIVE APPROACH ]` 
	O(1) Time Complexity
	O(1) Space Complexity 
```py
def isEven(n):
	return n%2 == 0
```

`[ EFFECTIVE APPROACH ]`
	O(1) Time Complexity
	O(1) Space Complexity
	Bitwise operations are faster than athematic operations
```py
def isEven(n):
	return (n&1) == 0
```


### MULTIPLICATION TABLE
~={purple}PROBLEM=~: Given a number ****n****, we need to print its table.
~={green}SOLUTION=~: 
`[ NATIVE SOLUTION ]` - Iterative Approach
	Time Complexity: O(1)
	Space Complexity: O(1)
```py
def printTable(n):
	for i in range(1,11):
		print(f"{n} * {i} = {n*i}")
```

`[ NATIVE APPROACH ]` - Recursive Approach
	Time Complexity - O(1)
	Space Complexity - O(1)
```py
def printTable(n, i=1):
	if(n>=10):
		return
	print(f"{n} * {i} = {n*i}")
	printTable(n, i+1)
```

### SUM OF N NATURAL NUMBERS
~={purple}PROBLEM=~: Given a positive integer ****n****, find the ****sum**** of the first ****n**** natural numbers.
~={green}SOLUTION=~:
`[ NATIVE APPROACH ]` - Iterative Approach
	Time Complexity - O(n)
	Space Complexity - O(1)
```py
def iterativeSum(n):
	total = 0
	if(n<=0):
		return total
	for i in range(1,n+1):
		total += i
	return total
```

`[ NATIVE APPROACH ]` - Recursive Approach
	Time Complexity - O(n)
	Space Complexity - O(1)
```py
def recursiveSum(n, total=0):
	if(n<=0):
		return total
	total+=n
	recursiveSum(n-1, total)
	
	// OR
	
	if(n<=0) return 0
	return n + recursiveSum(n-1)
```

`[ Effective Approach ]` - Formulae Based Approach
	Time Complexity - O(1)
	Space Complexity - O(1)
```py
def nSum(n):
	return (n* (n+1))/2
```


### SUM OF SQUARES
~={purple}PROBLEM=~: Given a positive integer n, we have to find the sum of squares of first n natural numbers.
~={green}SOLUTION=~:
`[ NATIVE APPROACH ]` - Iterative Approach
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
def SquareSummation(n):
	if(n<=0):
		return 0
	return sum([i**2 for i in range(1,n+1)])
```

`[ALTERNATE APPROACG ]` - Recursive Approach
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
def SquareSummation(n):
	if(n<=0):
		return 0
	return (n**2) = SquareSummation(n-1)
```

`[ EFFECTIVE APPROACH ]` - Formulae Based Approach
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
def SquareSummation(n):
	// return (n * (n+1) * (2*n + 1)) - CAN CAUSE STACK-OVERFLOW ERROR
	return ((n * (n+1))/2) * ((2*n + 1)/3)
```
> IMPORTANT NOTE:
> 	(n * (n+1) * (2*n + 1))/6 can cause a Stack-Overflow Error.
> 	Hence we use ((n * (n+1))/2) * ((2*n + 1)/3)


### SWAP TWO NUMBERS
~={purple}PROBLEM=~: Given two numbers ****a**** and ****b****, the task is to swap them.
~={green}SOLUTION=~:
`[ NATIVE APPROACH ]` 
	Time Complexity: O(1)
	Space Complexity: O(1)
```py
def swapNumbers(a,b):
	return b,a
	
	// BUILT-IN METHOD
	return swap(a, b)
```

`[ ALTERNATE APPROACH ]` - Using Athematic/Bit-wise Operations
	Time Complexity: O(1)
	Space Complexity: O(1)
```py
def SwapNumbers(a,b):
	// ARTHEMATIC OPERATION APPROACH
	a = a + b
	b = a - b
	a = a - b
	
	// BIT-WISE OPERATION APPROACH
	a = a ^ b
	b = a ^ b
	a = a ^ b
```


### CLOSEST TO N DIVISIBLE BY M
~={purple}PROBLEM=~: Given two integers n and m (m != 0). Find the number closest to n and divisible by m. If there is more than one such number, then output the one having maximum absolute value.
~={green}SOLUTION=~:

### DICE PROBLEM
~={purple}PROBLEM=~: You are given a ****cubic dice**** with ****6**** faces. All the individual faces have a number printed on them. The numbers are in the range of ****1 to 6****, like any ordinary dice. You will be provided with a face of this cube, your task is to guess the number on the opposite face of the cube.
~={green}SOLUTION=~:
`[ NATIVE APPROACH ]` - Conditional Statement
`[ EFFECTIVE APPROACH ]` - Sum of Sides
	Time Complexity: O(1)
	Space Complexity: O(1)
```py
def OppositeFace(n):
	return 7 - n;
```
> Sum of opposite sides of a 6-faced dice is always 7

### SUM OF DIGITS
~={purple}PROBLEM=~: Given a number n, find the sum of its digits.
~={green}SOLUTION=~:
`[ NATIVE APPROACH]` - Iterative Approach
	Time Complexity: O(d)
	Space Complexity: O(d)
```py
def SumOfDigits(n):
	return sum([int(i) for i in str(n)])
```
`[ ALTERNATE APPROACH ]` - Recursive Approach
	Time Complexity: O(log n)
	Space Complexity: O(log n)
```py
def SumofDigits(n):
	if (n == 0): return 0
	return n%10 + SumOfDigits(n//10)
```

### REVERSE A NUMBER
~={purple}PROBLEM=~:  Given an Integer n, find the reverse of its digits.
~={green}SOLUTION=~:
`[ NATIVE APPROACH ]` - Iterative Approach
	Time Complexity: O(log n)
	Space Complexity: O(1)
```py
def ReverseDigit(n):
	reversed = 0
	while(n>0){
		reversed = (reversed * 10) + (n % 10)
		n = n//10
	}
	return reversed
```

`[ ALTERNATE APPROACH ]` - Type conversion & Built-In Methods
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
def ReverseDigits(n):
	return int(str(n)[::-1])
```

### PRIME NUMBER CHECK
~={purple}PROBLEM=~: Given a number ****n****, check whether it is a prime number or not.
~={green}SOLUTION=~:
`[ NATIVE APPROACH ]` - Recursive Approach
```py
def CheckPrime(n, current=2):
	if(n<=1) return False
	if(current >= n) return True
	if(n%current == 0 and n != current) return False
	return CheckPrime(n, current+1)
	
	if n <= 1:
        return False
    for i in range(2, n):
        if n % i == 0:
            return False
    return True
```

`[ EFFECTIVE APPROACH ]` - Square Root Trial Division Method
Consider a number n with a pair of factors (a, b) such that a × b = n.  
- If a < b, then a × a < a × b = n, which means a < √n.
- - This shows that any factor larger than √n must have a corresponding factor smaller than or equal to √n.
- Therefore, it is enough to check numbers up to √n.
- If no factor ≤ √n is found, n is prime.
```py
def CheckPrime(n):
	if(n<=1): return False
	while((i**2) <= n):
		if(n%i)==0: return False
		i+=1
	return True
```
> i always less than √n i.e. $i^2$ less than or equal n

### POWER CHECK
~={purple}PROBLEM=~: Given two positive numbers x and y, check if y is a power of x or not.
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]` - Repeated Multiplication Method 
	Time Complexity: O($log_xy$)
	Space Complexity: O(1)
```py
def isPower(self, x, y):
    if(x>y and y != 0): return False
    if(y == 0): return True
    power = x
    while power<y:
        power *= x
    return power==y
```

`[EFFECTIVE APPROACH ]` - Exponential Search
```py
class Solution:
    def isPower(self, x, y):
        if y == 1:
            return True
        if x == 1:
            return y == 1
        if x == 0:
            return y == 0
        while y % x == 0:
            y //= x
        return y == 1
```

`[ BEST APPROACH ]` - Logarithmic Method
	Time Complexity: O(1)
	Space Complexity: O(1)
```py
class Solution:
    def isPower(self, x, y):
        if y == 1:
            return True
        if x == 1:
            return y == 1
        result = math.log(y) / math.log(x)
        return abs(result - round(result)) < 1e-10
```
>IMPORTANT NOTE
>abs(result - round(result)) < 1e-10
>	Checks that result is a whole number i.e. when whole number and not float. 
>	1e-10 ($10^{-10}$) is present to ensure very small int difference is ignored

### OVERLAPPING RECTANGES
~={purple}PROBLEM=~: Given two rectangles, find if the given two rectangles overlap or not.
Coordinates: (X, Y)
l1: Top Left coordinate of first rectangle. 
r1: Bottom Right coordinate of first rectangle. 
l2: Top Left coordinate of second rectangle. 
r2: Bottom Right coordinate of second rectangle.
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]` 
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
def Overlaps(L1, R1, L2, R2):
	if(L1[0] > R2[0] or R1[0] < L2[0]): return "DOESN'T OVERLAP"
	if(R1[1] > L2[1] or L1[1] < R2[1]): return "DOESN'T OVERLAP"
	return "Overlaps"
```

### FACTORIAL
~={purple}PROBLEM=~: Given a non-negative integers n, compute the factorial of the given number.
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]` - Recursive Approach
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
def FACTORIAL(n):
	if n == 0:
        return 1
    return n * FACTORIAL(n - 1)
    
def FACTORIAL_ITERATIVE(n):
	if(n==0): return 1
	output = 1
	while n > 0:
		output *= n
		n-=1
	return output
```

### PAIR CUBE COUNT
~={purple}PROBLEM=~: Given n, count all 'a' and 'b' that satisfy the condition a^3 + b^3 = n. Where (a, b) and (b, a) are considered two different pairs
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]`  
	Time Complexity: O($n^2$)
	Space Complexity: O(1)
```py
	def PairCube(n):
		count = 0
	    for a in range(1, n + 1):
	        for b in range(n + 1):
	            if a**3 + b**3 == n:
	                count += 1
	    return count
```

`[ EFFECTIVE APPROACH ]`
	Time Complexity: O($n^{1/3}$)
	Space Complexity: O(1)
```py
	def PairCube(n):
		count = 0
        for i in range(1, int(math.pow(n, 1/3)) + 1):
            a_cube = i ** 3
            remaining = n - a_cube
            b = round(remaining ** (1/3))
            if (n == int(a_cube + (b**3))):
                count += 1
        return count
```
> IMPORTANT NOTE
> 	We use range `(1, int(math.pow(n, 1/3)) + 1)` for i. As all numbers from $n^{1/3}$ will result in a cube greater than n.

### PERFECT NUMBER
~={purple}PROBLEM=~: A number is a perfect number if it is equal to the sum of its proper divisors, that is, the sum of its positive divisors excluding the number itself. Find whether a given positive integer n is perfect or not.
	****Input****: n = 15  
	****Output****: false  
	****Explanation:**** Divisors of 15 are 1, 3 and 5. Sum of divisors is 9 which is not equal to 15.
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]`  
	Time Complexity: O($n$)
	Space Complexity: O(1)
```py
	def PerfectNumber(n):
		result = 0
	    for i in range(1, n):
			if(n%i == 0):
				result += i
	    return result
```

`[ EFFECTIVE APPROACH ]`
	Time Complexity: O($n^{1/2}$)
	Space Complexity: O(1)
```py
	def PerfectNumber(n):
		result = 0
	    for i in range(1, (n ** (1/2)) + 1):
			if(n%i == 0):
				result += i 
				if(n != n//i): result += n//i
	    return result == n
```
> IMPORTANT NOTE
> 	We are looking in range 1-$n^{1/2}$ since $n^{1/2} * n^{1/2}$ = n. And any factor of n say a has a pair b that is greater than $n^{1/2}$ such that $a* b = n$. So by finding a we can calculate b by performing the operation n//a thereby acquiring both the factors a, b 

### ARMSTRONG NUMBER
~={purple}PROBLEM=~: Given a number x, check if the given number is Armstrong's number or not. A positive integer of n digits is called an Armstrong number of order n (order is the number of digits) if
****abcd... = pow(a,n) + pow(b,n) + pow(c,n) + pow(d,n) + ....****
	****Input:**** n = 153  
	****Output:**** true  
	****Explanation:**** 153 is an Armstrong number, 1*1*1 + 5*5*5 + 3*3*3 = 153
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]` - 
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
    def armstrongNumber (self, n):
        # code here 
        s = str(n)
        armstrong = sum([(int(i) ** len(s)) for i in s])
        return n == armstrong
```

### PALINDROME
~={purple}PROBLEM=~: Given an integer n, determine whether it is a palindrome number or not. A number is called a palindrome if it reads the same from forward and backward.
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]` - 
	Time Complexity: O(d)
	Space Complexity: O(1)
```py
    def isPalindrome(self, n):
		# code here
		temp = str(n)
		s = "".join([i for i in temp if i.isdigit()])
		l, h = 0, len(s)-1
		while l<h:
		    if(s[l] != s[h]): return False
		    l +=1
		    h -=1
		return True
```

### Nth SERIES-NUMBER
~={purple}PROBLEM=~: Given a number n, find the n-th term in the series 1, 3, 6, 10, 15, 21...
	****Input**** 3  
	****Output**** 6
	****Input**** 4  
	****Output**** 10
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]`
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
def NthNumber(n):
	result = 0
	for i in range(1, n+1):
		result += i
```

### SQUARE ROOT OF INTEGER
~={purple}PROBLEM=~: Given a positive integer ****n****, find its square root. If ****n**** is not a perfect square, then return ****floor**** of ****√n****.
~={green}SOLUTION=~: 
`[ NATIVE APPROACH ]` - 
	Time Complexity: O(n)
	Space Complexity: O(1)
```py
class Solution:
    def floorSqrt(self, n): 
        # return int(n ** (1/2))
        # OR
        l, h = 1, n
        result = 1
        while l<=h:
            mid = (l+h)//2
            mid_sq = mid ** 2
            if(mid_sq <= n):
                l = mid + 1
                result = mid
            else:
                h = mid - 1
        return result
```

### 







---
#### SUMMARY


---
#### FOOTNOTES

