# Resizing, Index Review
## Resizing Array Based Data Structures
### Arrays Can't Be Resized
* Once an array is created (statically) its size can't be changed
```
int[] a = new int[10];
a[0] = 5;
```
* Using new creates a new array and doesn't *copy* data over
```
a = new int[20];
System.out.println(a[0]); // will print 0
```

**What happens when a list is full?**
* Throws error
* Need to know size ahead of time

### Alternative- Resizing Internally
1. Check if list is full (or any ds)
2. If not, add as normal
3. If full, call resize method
    1. Allocate a new array of larger size
    2. Copy elements from old array to new array
    3. Assign new array to array attribute (old array is garbage collected)

### Copy Data from One Array To Another
* Create 2 separate arrays
```
int[] a = new int[10];
a[0] = 5;
int[] b = new int[20];
```

* Copy Contents
```
for (int i = 0; i < a.length; i++) {
    b[i] = a[i];
}
```

* Reassign the old array
`a = b; // old array is gone`

### List Class Outline
```java
public class List {
 int size; 
 int[] data;
 public static final int LIST_CAPACITY = 10;
 
 public List() {}
    public boolean isFull() {}
    private void resize() {}
    public void append(int pos) {}
    public void insert(int item, int pos) {}
}
```
```java
// method definitions
public boolean isFull() {
    return data.length == size;
}

public void resize() {
    // declare new array
    int[] temp = new int[data.length * 2]; // can also specify new list size in parameters
    // copy values from old to new list
    for (int i = 0; i < size; i++) {
        temp[i] = data[i];
    }
    // garbage collect old array
    data = b;
}

public void insert(int value, int pos) {
    // check if pos is valid
    if (pos < 0 || pos > size) {
        System.err.println("Error: Invalid Position");
    }
    
    if (isFull()) { // check if there's anything in the list
        resize(); // space & resize arr if not
    }
    // otherwise insert as normal
}

public void append(int value) {
    if (isFull()) { // check if list is full
        resize(); // space & resize if not
    }
    data[size++] = value; // otherwise set next index = value
}
```
## Index Review
### Requirements for Array-Based DS
* Construct empty instance
  * Use constructor
* Check if instance is empty
  * `isEmpty()`
* Add element
* Get element
* Remove element
* Iterate over

### List DS
* Add element
* `void insert(int pos, [TYPE] value)`
  * takes integer index where to insert *(must shift values to right to make room for new value)*
  * `void append([TYPE] value)`
* Get element from instance
  * `[TYPE] get()`
* Remove element from instance
  * `void remove(int pos)`
  * Takes integer index where to remove *(shift left to fill up list and make room for new elements to the right)*

### List Index
* `int size`
  * Starts at 0
  * Indicates next pos to write to
  * Increment **after** inserting/appending data
  * Decrement **after** removing data

* Not the capacity of the list  
  * Counts the # of elements currently stored in the list

* `boolean isEmpty()`
  * Checks if `size` is == 0

### Stack DS
* Add element to instance
  * `void push([TYPE] value)`
  * Increment the `top` index and writes data to the new index
* Get element from instance
  * `[TYPE] top()`
  * Returns value at current `top` index
* Remove element from index
  * `void pop()`
  * Decrements `top` index

### Stack Index
* `int top`
  * Starts at -1
  * Indicates last pos written to (current top of stack)
  * Increment **before** inserting/appending data
  * Decrement **after** removing data
* `boolean isEmpty()`
  * Checks if `top` is == -1

### Queue DS
* Add ele to instance
  * `void enqueue([TYPE] value)`
  * Add one to `back` and use remainder operator to get new value
* Get ele from instance
  * `[TYPE] front()`
  * Returns value at current `front` index
* Remove element from index
  * `void dequeue()`
  * Add 1 to front and use % to get new value
    * value = (front+1) % data.length;

### Queue Index: 
* `int front`
  * Index from 0
  * Indicates next pos to read from
  * Increment **after** removing data
  * Incremental value is `front = (front+1) % data.length;`
* `int back`
  * Index from 0
  * Indicates next post to write to
  * Increment **after** inserting/appending
  * Incremental value `back = (back+1) % data.length;`
* `boolean isEmpty()`
  * Checks if `front` == `back`

**Do Exercise**