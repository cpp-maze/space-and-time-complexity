# Space and Time Complexity


1. [What is Space and Time Complexity](#what-is-space-and-time-complexity)
2. [Calculation rules for loops](#calculation-rules-for-loops)
 
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
