# Two Dimensional Arrays

## 2D Array Concepts
### Array Dimensions
* "Normal" arrays are one-dimensional
* `{1, 2, 3, 4, 5}`
* Two-dimensional (2D) arrays, basically 2 arrays in one
  * Think of how a nested loop works
* `{{1, 2, 3, 4}, {1, 2, 3, 4}, {1, 2, 3, 5}}`
  * Think of an array of arrays
  * Or an array of single values represented in arrays
    * `{{1}, {2}, {3}, {4}, {5}}`

### Purpose of Multidimensional Arrays:
* Describe more complex relationships
* Describe spatial relationships
  * Maps
  * Rooms
* Examples:
  * Game boards
  * Grids of numbers
  * Spreadsheets
  * Tables

### 2D Array Dimensions
* 2D Arrays have 2 dimensions
  * Represented with rows and columns
* Each dimension has a size
  * Can be the same or different
* Total size of the *array = rows * columns*

### Element Locations
* To specify the location of an element:
  * Specify 2 indexes
    * Row
    * Column
* Everything is linear
  * Row is an offset from the start of the array
  * Size of the offset is the number of columns
  * ---|---|---|
      * ex. where `|` represents columns
      * and `-` represents rows

### Index Translation Algorithms:
* From single-dimension index -> 2D Indexes
  * `row = index / numberOfColumns`
  * `col = index % numberOfColumns`
* From 2D indexes to single-dimension index
  * `index = col + (row * numberOfColumns)`
* This assumes zero-based indexing

## Manipulating 2D Arrays
### Creating 2D Arrays in Java:
* Add a second index operator `[]`
  * The number of rows goes in the first `[]`
  * The number of columns goes in the second `[]`
* Ex:
  * 2D array of ints of 3 rows / 4 columns
  * `int[][] grid = new int[3][4];`
  * 2D array of doubles of 2 rows / 6 columns
  * `double[][] grades = new double[2][6];`
  * 2D array of Strings of 5 rows / 10 columns
  * `String[][] lettesr = new String[5][10];`

### Accessing 2D Array Elements
* Cannot specify only one index
  * Given
  * `int[][] grid = new[3][4];`
  * Cannot do any of these:
  * `grid[1] = 5;`
  * `grid[1][] = 5;`
  * `grid[][1] = 5;`
* Must specify both indexes
```java
int[][] grid = new int[3][4];
grid[1][2] = 44;
System.out.println(grid[1][2]); // prints 44
```

## 2D Array Algorithms
### 2D Array Algorithm Basics:
* Nested for loops commonly used
* Outer loop increments rows
* Inner loop increments columns

### Populating a 2D Array:
```java
final int COLS = 4, ROWS = 3;

int[][] data = new int[ROWS][COLS];
for(int row = 0; row < ROWS; row++) {
    for (int col = 0; col < COLS; col++) {
        data[row][col] = row * COLS + col + 1;
    }
}
```

### Printing a 2D Array:
```java
int[][] data = new int[ROWS][COLS];
for (int row = 0; row < ROWS; row++) {
    for (int col = 0; col < COLS; col++) {
        if (row * COLS + col < 9) {
            System.out.print("0"); // prepend zero as needed     
        }
        System.out.print(data[row][col] + " ");
    }
    System.out.println(); // end each row
}
```
*Result:*

`01 02 03 04`

`05 06 07 08`

`09 10 11 12`

### Calculating the Sum of Each Row:
```java
// calculate the sum of each separate row
int[] rowSums = new int[ROWS];
for (int row = 0; row < ROWS; row++) {
    rowSums[row] = 0; // initialize
    for (int col = 0; col < COLS; col++) {
        rowSums[row] += data[row][col];
    }
}

// print row sums
for (int row = 0; row < ROWS; row++) {
    System.out.println("Sum of row: " + row + " = " + rowSums[row]);
}
```

*Result:*

`Sum of row: 0 = 10`

`Sum of row: 1 = 26`

`Sum of row: 2 = 42`

### Calculating the Product of Each Column:
```java
// calculate the product of each column and store in colProducts
int[] colProducts = new int[COLS];
for (int col = 0; col < COLS; col++) {
    colProducts[col] = 1; // must initialize
    for (int row = 0; row < ROWS; row++) {
       colProducts[col] *= data[row][col]; 
    }
}
// print
for (int i = 0; i < COLS; i++) {
    System.out.println("Product of column: " + i + " = " + colProducts[i]);
}
```
*Result:*

`Product of column: 0 = 45`

`Product of column: 1 = 120`

`Product of column: 2 = 231`

`Product of column: 3 = 384`
