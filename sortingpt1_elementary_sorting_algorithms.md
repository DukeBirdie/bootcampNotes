# Elementary Sorting Algorithms

## Defining Sort and Swap
### Sorting Defined
* Assume a list x0, x1, x2, x(n-1)
* Sorting is to arrange the elements of the list in order
  * Either ascending or descending
* Our default order in the course is ascending
  * A, B, C, or 1, 10, 100, rather than the reverse

### Order Defined
* Order is not natural or absolute
* Different orders exist for different purposes
  * Numeric order - 1,2,3 or 1,10,100
  * Alphabetical order - A,B,C or aardvark, abacus, abattoir
  * Alphanumerical order - (treating digits as "letters") - 1, 10, 2, 20, 3, 30
  * ASCII Order - Aardvark, Zebra, aardvark, zebra
* What order solves your problem?
  * How can you compare items to determine correct ordering?

### Swap Algorithm - (bad)
```java
static void swap(int a, int b) {
    int temp = a;
    a = b;
    b = temp;
}
```

### Swap Algorithm - (good)
```java
static void indexSwap(int[] array, int a, int b) {
    int temp = array[b];
    array[b] = array[a];
    array[a] = temp;
}
```

## Bubble Sort
### Algorithm Steps
1. Declare 2 Index Variables
    * Start them at 0 and 1 respectively
2. Compare adjacent elements
   * If the 2 elements are in order, leave them
   * If they aren't in order, swap them
3. Increment each index variable
4. Repeat steps 2 & 3 to the end of the list
5. Repeat steps 1-4, excluding one more element each time

### Measuring Sort Performance
* Big O
  * For bubble sort O(n^2)
  * Most nested loops are either O(n^2) or O(n*log2(n))
* Comparisons & Swaps
  * For bubble sort example above
  * 10 comparisons 
  * 7 swaps

### Example Bubble Sort (Written By Me)
```java
public static int bubbleSort(int[] a) {
    for (int i = 0; i < a.length; i++) {
        for (int j = i + 1; j < a.length-1; j++) {
            if (a[i] > a[j]) {
                // swap
                int temp = a[i];
                a[i] = a[j];
                a[j] = temp;
            }
        }
    }
} 
```
## Selection Sort
### Algorithm
1. Declare an index variable (`next`) and set = 0
2. Find smallest element between `next` and the end of arr
3. Swap the smallest element with the value at `next`
4. Increment `next` by 1 (next++)
5. Return to Step 2

### Selection Sort
```java
public static void selectionSort(int[] a) {
    for (int i = 0; i < a.length-1; i++){
        int minIndex = i; 
        
        for (int j = i + 1; j < a.length; j++) {
            if (a[j] < a[minIndex]) {
                minIndex = j;
            }
        }
        
        if (minIndex != i) {
            swap(a, minIndex, i);
        }
    }
}
```

### Measuring Sort Performance
* Big O
  * For Selection Sort O(n^2)
* Comparisons & Swaps
  * 10 comparisons
  * 3 Swaps

## Insertion Sort
### Algorithm
* Initially, mentally define a sorted sublist at the beginning of the list
  * Only sorted relative to itself
1. Declare index variable `next` and set to 1
2. Declare index variable `comp` and set = `next`
3. If value @ `comp` < `comp - 1`
   1. Swap elements at `comp` & `comp - 1`
   2. Subtract 1 from `comp` and return to Step 3
4. Increment `next` by 1
5. Return to step 2

### Measuring Sort Performance
* Big O
  * Insertion Sort - O(n^2)
* Comparisons & Swaps
  * 9 Comparisons
  * 6 swaps
* A faster variant
  * find correct insertion location & store value in temp variable
  * shift cells to right
  * copy temp value to correct location

### Remembering Sorting Algorithm Names
* Bubble sort
  * The top value floats to the end of the list like a **bubble** rising to the top
* Selection sort
  * **Select** the next correct value in the list to put in order
* Insertion sort
  * Create a sorted list and **insert** each new value into the correct relative position

### How to Not Screw Up Sorting
* Know basic algorithm
  * Watch sorting videos
  * Play around with sorting sims
* Know what inner & outer loops do
* Differentiate between array elements & indexes
  * Indexes are locations
  * Array elements are values at locations
  * Label variables appropriately
* Know what each temp variable holds

### Insertion Sort (my code)
