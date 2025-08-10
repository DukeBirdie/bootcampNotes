# Introduction to the Analysis of Algorithms

## Analysis of Algorithms
* Defining an algorithm
  * "A step-by-step procedure for solving a problem or accomplishing a task using a program"
  * A finite sequence of unambiguous instructions that, given any necessary input, produces a correct result and stops
* Popular types of algorithms
  * Sorting
  * Searching
  * Graph Traversal
  * etc.

### Analysis of Algorithms
* Algorithm analysis determines the efficiency of an algorithm
  * Measures the resources (time or memory) necessary to execute the algorithm as a *functon of input size*
* Main focus: time efficiency
  * AKA *time complexity*

### How is Time Complexity Measured
* Time depends on
  * Speed of machine
  * Quality of source code
  * Quality of compiler
  * What else is happening on comp at the same time
  * Other factors (e.g., IO)
* Count the # of operations executed while algo runs
  * Not all operations take same amount of time
  * Can't get a precise execution time
  * Estimate useful for comparison purposes

### How to Analyze an Algorithm
* For simplest non-repeating algorithms
  * Count each separate operation 
  * Sum operations
* For most complex algorithms that repeat
  * If an operation is in a loop that repeats n times, count as **1n**
  * Some operations can be *1n + 1* `while(a > b) {}`
  * a > b will occur n + 1 times, because it must return false to exit

## Time Complexity and Big O
### Example Analysis: Sum an Array
```java
// input: a[n], array of n integer type element
// output: sum of all items in array a
public static int sumArray(int[] a) {
    int sum = 0;
    for (int i = 0; i < a.length; i++) {
        sum += a[i];
    }
    return sum;
}
```

### Time Complexity - T(n)
1. Count each operation as a
    * A constant OR
    * A function of *n*
2. Sum the operations
* This is called the *time complexity* of an algorithm, or T(n)
  * Written as T(n) = an^2 + bn + c(logn) + d, where a/b/c/d are constants
  * For multiple algorithms, use subscript
  * T1(n), T2(n)

### Big O Notation
* Big O is a simple way to measure an algorithm's growth rate
  * In the example, we ignore the constant and multiplicative factor
  * T(n) = 4n + 4 becomes O(n)
* **Two rules** to transform T(n) to Big O
1. Eliminate low order terms
``` 
4n + 5 => 4n
0.5n*logn - 2n + 7 => 0.5n*logn
2^n + n^3 + 3n => 2^n
```
2. Eliminate constant coefficients
``` 
4n => n => O(n)
0.5n*logn => n*logn => O(nlogn)
2^n => O(2^n)
```

### Exercise #1 - Calculate T(n) & Convert to Big O
```java
public static void main(String[] args) {
    Scanner in = new Scanner(System.in);
    System.out.print("Enter a number: ");
    int n = in.nextInt();
    for (int i = 0; i < n; i++) {
        System.out.print("*");
    } 
    System.out.println();
}
```

### Exercise #2 - Calculate T(n) & Convert to Big O
```java
public static void main(String[] args) {
    Scanner in = new Scanner(System.in);
    System.out.print("Enter a number: ");
    int n = in.nextInt();
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            System.out.print("*");
        }
        System.out.println();
    }
}
```

### Self-Answer: Questions
* Will a longer program (more LOC) have a higher or lower Big O?
  * No. The length of a program doesn't determine its Big O. 
* Do these 2 things mean the same thing?
  * The first algorithm is faster than the second algorithm.
  * The first algorithm grows faster than the second algorithm.
* No they don't. The second one is referring to an exponentially growing algorithm whereas the first one likely refers to a linear algorithm.


## Comparing Time Complexity
### Common Time Complexity Classes
Efficiency Order: | Complexity: | Written As: | Name:
1 | 1 | O(1) | Constant Time 
2 | log(base2)(n) | O(log(2)(n)) | Logarithmic Time
3 | n | O(n) | Linear Time
4 | n log2(n) | O(n log2(n)) | Log-linear (or linearithmic) Time
5 | n^2 | O(n^2) | Quadratic Time 
6 | n^3 | O(n^3) | Cubic Time 
7 | 2^n | O(2^n) | Exponential Time
8 | n! | O(n!) | Factorial Time

### Time Complexity Examples
Name: | Sample Function: | Example Algorithms:
Constant Time | 1 | Append a number at the end of an array. Even if the input array is very big, we can append a number to the array with the size information of the arrayl.
Logarithmic Time | log n | Binary Search in a sorted array with n numbers
Linear Time | n | Calculate the sum of n numbers in an array
Linearithmic Time | n*log(n) | Merge sort
Quadratic Time | n^2 | Bubble sort
Cubic Time | n^3 | Multiplication of two n*n matrices
Exponential Time | 2^n | Tower of Hanoi problem with n disks
Factorial Time | n! |TSP (Travelling Salesman Problem) using brute-force approach

### Time Complexity Converted To Real Time
* Suppose each instruction can be done in 1 microsecond
  * Microsecond - one millionth of a second, or 1 million instructions/second
* For n = 256 inputs, results for various f(n)
Function: | Time:
Log2(n) | 8 microseconds
n | 0.25 milliseconds
n log2(n) | 2 milliseconds
n^2 | 65 milliseconds
n^3 | 17 seconds
2^n | 3.7+E64 centuries

### Worst-Case vs. Best-Case vs. Average Case
* Algorithms often have different execution times depending on the characteristics of the input
* This, when we analyze those algorithms, we should consider:
  * The best-case time complexity
  * The worst-case time complexity
  * A typical case for our data

### Example - Sequential (Linear) Search
```java
public static int linearSearch(int[] a, int find) {
    // searches for value find in an array a
    int i = 0;
    while ((i < a.length) && (a[i] != find)) {
        i++;
    }
    if (i < a.length) {
        return i; // found
    } else {
        return -1; // not found
    }
}
```

### Worst vs. Best Case
* Worst case
  * Array `a` is [100, 5, 89, 70, 20, 64, 77]
  * Value `find` is 55
  * How many operations
    * 7 operations
* Best Case
  * Array `a` is [100, 5, 89, 70, 20, 64, 77]
  * Value `find` is 100
  * How many operations?
    * 1 operation (or 0 depending on how it's counted)

