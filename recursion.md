# Recursion Concepts & Recursive Methods
## Recursion Concepts & Basic Methods
### Defining Recursion
* "A computer programming technique involving the use of a procedure, subroutine, function, or algorithm that calls itself one or more times until a specified condition is met."
### Factorial Defined - Example
```java
public static int factorial(int n) {
    int nFactorial = 1;
    for (int i = 0; i < n; i++) {
        nFactorial *= (n-i);
    }
    return factorial;
}
```

### Recursive Algorithms Have At Least 2 Cases
* Base case (or stopping case)
  * Returns a result without a recursive call
  * The simple case(s) for which the answer is known
  * Example: 0! = 1, 1! = 1
* Recursive case (or inductive case)
  * Will call the method itself
  * Argument will be reduced (or increased)
* Example: f(n) = n * f(n-1);
  * n! = n*(n-1);

### General Format of a Recursive Method
```java
public static int foo(int x) {
    if (condition) {
        // base case
        return solution statement;
    } else {
        // recursive case
        return call to foo (different parameter);
    }
}
```

### Recursive Factorial
```java
public static void main(String[] args) {
    System.out.printf("%d! = %d\n", 5, factorial(5));
}

public static int factorial(int n) {
    // assume that n >= 0
    if (n==0) {
        return 1; // base case
    }
    return n*factorial(n-1);
}
```

## Recursion & Arrays
### Recursive Methods W/ Arrays
* Need to pass a parameter to keep track of indexes
* To summ array:
``` 
public static int sumArray(int[] data, int index) {}
```

### Iterative sumArray()
```java
public static int sumArray(int[] a) {
    int sum = 0;
    for (int i = 0; i < a.length; i++) {
        sum += a[i];
    }
    return sum;
}
```

### Implementing sum() recursively
```java
public static void main(String[] args) {
    int[] a = {2, 3, 1, 5, 4};
    System.out.printf("Sum: %d", sum(a,5));
}

public static int sum(int[] a, int size) {
    if (size == 0) {
        return 0;
    } else {
        return a[size-1] + sum(a, size-1);
    }
}
```

### Implement multiply() recursively
```java
public static void main(String[] args) {
    int[] a = {2, 3, 1, 5, 4};
    System.out.println("Product: " + multiply(a, 5));
}

public static int multiply(int[] a, int size) {
    if (???){
        return ?
    } else{
        return ???multiply(a, size - 1);
    }
}
```
