# Space and Time Complexity


1. [What is Space and Time Complexity](#what-is-space-and-time-complexity)
2. [Calculation rules for loops](#calculation-rules-for-loops)
3. [Types of time functions](#types-of-time-functions)
4. [Asymptotic notations](#asymptotic-notations)
5. [Best, Worst and Average case Analysis](#best-worst-and-average-case-analysis)
6. [Calculation rules for decreasing function](#calculation-rules-for-decreasing-function)
7. [Master's theorem for decreasing function](#masters-theorem-for-decreasing-function)
8. [Calculation rules for dividing function](#calculation-rules-for-dividing-function)
9. [Master's theorem for dividing function](#masters-theorem-for-dividing-function)

## What is Space and Time Complexity

### Space Complexity
When we calculate the space, we do not use KB, MB, or GB as unit.
We use **1 unit** for a variable. If it is an array of N element we take it as **N unit** of space.

**Code snippet**
```cpp
int a; // 1 unit
int a, b; // 2 unit
double d1, d2;  // 2 unit
```

**Code snippet**
```cpp
int a = 1, int b = 2; // 2 unit
int sum; // 1 unit
sum = a + b;
cout << sum;
```
**Code snippet**
```cpp
int getSum(int A[n]) { // array A is n unit
    int sum = 0; // 1 unit
    for (int i = 0; i < n; ++i) {
        sum += A[i];
    }
    return sum;
}
```

### Time Complexity
When we calculate how much time the program will take to run, we do not use watch time.
We use **1 unit** for a simple statement. If it is a function call then we must take how much time the function will take.

**Code snippet**
```cpp
int a = 1, int b = 2;
int max;
if (a > b) { // 1 unit
  max = a; // 1 unit
} else {
  max = b; // 1 unit
}
```


## Calculation rules for loops

Loops are nothing but a simple statements that repeat for some number of times. So, we need to count how many times the statements are going to execute.

### Simple loops

**Looping from 0 to n - 1**
```cpp
for (int i = 0; i < n; ++i) {
	cout << i;
}
```

**Looping from n - 1 to 0**
```cpp
for (int i = n - 1; i >= 0; --i) {
	cout << i;
}
```

**Find minimum**
```cpp
int findMin(int arr[], int n) {
	int ans = INT_MAX;
	for (int i = 0; i < n; ++i) {
		if (ans > arr[i]) {
			ans = arr[i];
		}
	}
	return ans;
}
```

**Iterate by multiplying 2**
```cpp
for (int i = 1; i < n; i = i * 2) {
	cout << i;
}
```

**Iterate by dividing 2**
```cpp
for (int i = n; i >= 1; i = i / 2) {
	cout << i;
}
```

### Nested loops

**Two nested loops**
```cpp
for (int i = 0; i < n; ++i) {
	for (int j = 0; j < n; ++j) {
		cout << arr[i][j];
	}
}
```

**Three nested loops**
```cpp
for (int i = 0; i < n; ++i) {
	for (int j = 0; j < n; ++j) {
		for (int k = 0; k < n; ++k) {
			cout << arr[i][j][k];
		}
	}
}
```

**Combination of two different loops**
```cpp
for (int i = 0; i < n; ++i) {
	for (int j = 1; j < n; j = j * 2) {
		cout << j;
	}
}
```

## Types of time functions

| Complexity class			| Name 			|
|---------------------------|---------------|
| O(1) 						| Constant 		|
| O(log n) 					| Logarithmic 	|
| O(n) 						| Linear 		|
| O(n log n)				| Linearithmic	|
| O(n^2^)					| Quadratic 	|
| O(n^3^)					| Cubic 		|
| O(2^n^)					| Exponential 	|


**Time functions in increasing order**

$$
1 < log(n) < √n < n < n^2 < n^3 < ... < n^c < 2^n < 3^n < ... < n^n
$$



## Asymptotic notations
Asymptotic notations tells how the Space or Time function is going to grow when the input tends towards a particular value or infinity. It helps us to simplify the Space or Time function. We can use the simplified form of the function to compare algorithms.

***Omega:*** `Ω`
It is used to find the lower bound of a function.

Let `f(n)` and `g(n)` be the function.
The function `f(n) = Ω(g(n))`, if and only if there exists a constant c > 0 and a natural number n~0~ such that `c∗g(n) <= f(n)` for all n >= n~0~

<img 
	src="public/omega-notation.png" 
	alt="omega notation graph" 
	style="max-width: 350px"
/>

***Big O:*** `O`
It is used to find the upper bound of a function

Let `f(n)` and `g(n)` be the function.
The function `f(n) = O(g(n))`, if and only if there exists a constant c > 0 and a natural number n~0~ such that `f(n) <= c∗g(n)` for all n >= n~0~

<img 
	src="public/big-O-notation.png" 
	alt="big O notation graph" 
	style="max-width: 350px"
/>


***Theta:*** `Θ`
It is used to find the average bound of a function

Let `f(n)` and `g(n)` be the function.
The function `f(n) = Θ(g(n))`, if and only if there exists a constant c1 > 0, c2 > 0 and a natural number n~0~ such that `c1∗g(n) <= f(n) <= c2∗g(n)` for all n >= n~0~

<img 
	src="public/theta-notation.png" 
	alt="theta notation graph" 
	style="max-width: 350px"
/>


## Best, Worst and Average case Analysis

**Code snippet**
```cpp
void A(int n) {
	if (some condition on n) {
		// n^2
	} else {
		// n⁎log(n)
	}

	if (different condition on n) {
		// n
	} else {
		// n^3
	}
}
```

**Linear search**
```cpp
int search(int arr[], int n, int target) {
	for (int i = 0; i < n; ++i) {
		if (arr[i] == target) return i;
	}

	return -1;
}
```

## Calculation rules for decreasing function 

**Calling in-build function**
```cpp
void A(int n) {
	int res = sqrt(n);
	cout << res;
}
```

**Calling user defined function**
```cpp
void A(int n) {
	int res = B(n);
	cout << res;
}

void B(int n) {
	// statements
}
```

**Print n to 1**
```cpp
void A(int n) {
	if (n > 0) {
		cout << n;
		A(n - 1);
	}
}
```

**Print 0 to n - 1 for all numbers**
```cpp
void A(int n) {
	if (n > 0) {
		for (int i = 0; i < n; i++) {
			cout << i;
		}
		A(n - 1);
	}
}
```

**Find n^th^ fibonacci number**
```cpp
int Fib(int n) {
	if (n <= 1) {
		return n;
	}
	return Fib(n - 1) + Fib(n - 2);
}
```

## Master's theorem for decreasing function

Consider the time function for the given algorithm as 

$$
a * A(n - b) + f(n)
$$

where **a > 0** and **b > 0**.

For example `2 * A(n - 1) * 1`, here `a = 2`, `b = 1` and `f(n) = 1`

The Masters's theorem for decreasing function is divided in to two cases:

### Case i: (a == 1)
> **Multiply the `f(n)` with `n`**

In the above equation the `f(n) = 1` so, 

=> f(n) * n 
=> 1 * n 
=> O(n)

If `f(n) = n` then 

=> f(n) * n 
=> n * n 
=> O(n^2^)

### Case ii: (a > 1)
> **Multiply the `f(n)` with a^n^**

In the above equation the `a = 2` and `f(n) = 1` so, 

=> f(n) * 2^n^ 
=> 1 * 2^n^ 
=> O(2^n^)


If the equation contains `a = 3` and `f(n) = n`, 

=> f(n) * 3^n^ 
=> n * 3^n^ 
=> O(n * 3^n^)



## Calculation rules for dividing function

**Code snippet**
```cpp
void A(int n) {
	if (n > 1) {
		cout << n;
		A(n / 2);
	}
}
```

**Code snippet**
```cpp
void A(int n) {
	if (n > 1) {
		for (int i = 0; i < n; ++i) {
			cout << i;
		}
		A(n / 2);
	}
}
```

**Code snippet**
```cpp
void A(int n) {
	if (n > 1) {
		for (int i = 0; i < n; ++i) {
			cout << i;
		}
		A(n / 2);
		A(n / 2);
	}
}
```
## Master's theorem for dividing function


Consider the time function for the given algorithm as 

$$ 
a * A(n / b) + f(n)
$$

where **a > 0** and **b > 1**

`f(n)` can be represented as **n^k^ * log^p^n**

For example `2 * A(n / 2) * 1`, here `a = 2`, `b = 2`, `k = 0` and `p = 0`

The Masters's theorem for dividing function is divided in to three cases:

### Case i: (log<small><sub>b</sub></small>a > k)
> **Take n<sup>log<small><sub>b</sub></small>a</sup>**

### Case ii: (log<small><sub>b</sub></small>a = k)

This second case is divided into further three sub cases.

>#### Case 1: p >= 0
>> **Multiply f(n) with log(n)**
>
>#### Case 2: p = -1
>> **Multiply n^k^ with loglog(n)**
>
>#### Case 3: p < -1
>> **Take n^k^**

### Case iii: (log<small><sub>b</sub></small>a < k)

This third case is divided into further two sub cases.

>#### Case 1: p >= 0
>> **Take f(n)**
>
>#### Case 2: p < 0
>> **Take n^k^**
