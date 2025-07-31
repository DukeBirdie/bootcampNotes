# Arrays
## Array Concepts:
### Variables are limited
* Each can only store 1 value
  * Called *scalar* variables
* Each must be passed individually
* Methods can only return one value

### Solution: Arrays
* Are *vector* variables
  * Have **dimensionality**
* An array is a list of elements
* Each must be of the same data type
* Elements are accessed with their position in the array
* Indexes at 0

### Concepts: Arrays
**"An ordered series of elements of a specific datatype, stored contiguously in memory"**
*"Contiguously: One after the other"*
* Order -> [7, -3, 8], won't change unless we change it
* Series -> arbitrary number of members, one following another
* Elements -> Members of arrays are referred to as elemens
* Datatype -> Only holds one specific datatype
* Stored contiguously in memory

## Array Creation & Manipulation:

### Creating An Array:
* An array has a datatype (can't change), like a double or string
* Has a size (can't change)

### Declaring an Array:
* An array of 5 int values:
`int[] a = new int[5];`
* An array of 5 int values, called b, initialized with values [1, 2, 3, 4, 5]
`int[] b = {1, 2, 3, 4, 5};`
* An array of 5 double values, called c:
`double[] c = new double[5];`
* An *array variable* called d but does **NOT** create an array
`int[] d;`

### Accessing Elements of an Array:
* Array elements are accessed with the index operator `[]`
* To access a specific element, we specify the
  * Name of the array variable
  * The index operator
  * The position of the element we want (counting from 0)
* Example: Printing the first element of the array
```java
int[] b = {12, 14, 17, 19, 21};
System.out.println(b[0]);
```

### Populating an Array:
```java
int size = 5;
int[] b = new int[size];
b[0] = 5;
b[1] = 10;
b[2] = 15;
b[3] = 20;
b[4] = 25;
```
b[5] = 30 -> **OUT OF BOUNDS**

**Use to print array:**
```java
for (int i = 0; i < size; i++) {
    System.out.println(b[i]);        
}
```

### Array Size:
* Array size cannot change
* Can declare a new array of different size with same variable
  * Ex: New array variable `a` points to an array to hold 5 ints
  * `int[] a = new int[5];`
  * Ex: New array that holds 7 ints and points a to that
  * `a = new int[7];`
* This deletes everything that was previously in `a`

### Array Size pt. 2:
* Each array in Java knows its own size
  * Size counts from 1 not 0
* Accessed with the `.length` property
  * Ex: Array variable called `a` that points to an array to hold 3 ints
  * `int[] a = {1, 2, 3};`
  * Prints the length of the array (3)
  * `System.out.println(a.length);`
  * Prints each element of the array
```java
for (int i = 0; i < a.length; i++) {
    System.out.println(a[i]);        
}
```

## Arrays and Methods:

### Array Variable Properties:
* Can be passed to methods as parameters
* Can be return values
* Are passed by *reference*!

### Pass By Reference vs. Pass By Value:
* Pass by value:
  * Send copies of each parameter passed in
  * Changing parameter in method doesn't change original value
* Scalars (e.g., int, double) are always passed by value
* Pass by reference:
  * Pass in the variable itself
  * Done with memory addresses
  * Changing a reference parameter in the method will the change the original
* Arrays are always passed by reference

**Example:**
```java
public static void main() {
    int [] a = {3, 6, 9, 12, 15};
    System.out.println(a[4]); // prints 15
    foo(a);
    System.out.println(a[4]); // now prints 30
}

public static void foo(int [] a) { // doubles all values in original array
    for (int i = 0; i < a.size; i++) {
        a[i] = a[i] * 2;
    }
}
```

### Copying Arrays:
* What if you don't want the method changing the array?
  * Create copy
* 2 ways
  * Manual copy
  * Using the `.clone()` method
```java
int[] t = {1, 2, 3};
int[] u = t.clone();
```

### Returning Arrays:
```java
public static void main(String[] args) {
    int[] q = {1, 2, 3};
    int[] r = copy(q);
    q[1] = 5;
    r[1] = 10;
    System.out.println(q[1]);
    System.out.println(r[1]);
}

public static int[] copy (int[] a) {
    int[] b = new int[a.length];
    for (int i = 0; i < a.length; i++) {
        b[i] = a[i];
    }
    return b;
}
```

