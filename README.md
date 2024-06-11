# Space and Time Complexity


1. [What is Space and Time Complexity](#what-is-space-and-time-complexity)
 
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


