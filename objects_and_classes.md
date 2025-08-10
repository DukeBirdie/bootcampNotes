# Chapter 2:

## 07. - Objects:

### Example Class:
```java
class Account {
    private String name;
    private double balance;
    
    public void setInfo(String n, double b) {
        name = n;
        balance = b;
    }
    
    public double getBalance() { return balace; }
    
    public void deposit(double amount) { 
        balance += amount;
    }
    
    public boolean withdraw(double amount) {
        if (balance >= amount) {
            balance -= amount;
            return true;
        }
        return false;
    }
}
```

### Program Using Account Class:
```java
public static void main(String[] args) {
    Account a1 = new Account();
    Account a2 = new Account();
    
    a1.setInfo("Rosa", 1000.00);
    a2.setInfo("Hector", 2000.00);
    
    a1.deposit(400.00);
    boolean result = a1.withdraw(2500.0);
    System.out.println(result);
    
    result = a2.withdraw(1500.0);
    System.out.println(result);
}
```

## 09. - Classes as Datatypes & Constructors:

### Example classes as datatypes:
```java
class DayOfYear {
    int day;
    int month;
}
```

```java
class Holiday {
    String name;
    DayOfYear date;
}
```

### Class as Parameters:

```java
class Holiday {
    string name;
    DayOfYear date;
}

public void setDate(DayOfyear d){
    date = d;
}
```

## List ADT:

### List Data Structure

*Abstract data type (ADT) and collection are related concepts*
   Assume ADT = collection

### Requirements for a List Class
* Construct empty list
* Check if list is empty
* Add element to location in list
* Remove element from list
* Iterate over list (print -> sometimes)

### Lists vs. Arrays:
* Array is contiguous in memory
* List isn't contiguous

## Implementing a List With an Array
### Designing a List Class
* Lists have a fixed size
  * Unless using referential nodes
* Need >= 2 attributes
  * Array to store elements
  * Index to hold # of elements stored `size`

### Methods for List Class
* `Constructor`
    * Set variable `size` to 0
* `isEmpty()` 
  * Check if `size` is == 0
* `insert()`
  * Shift elements to right of insertion point
    * Make room to insert element
* `remove()`
  * Shift elements to left to avoid blank element
* `get()`
  * Given index, return value of index
    * Verify the index is valid

### List Class Outline:
```java
public class List {
    int size;
    int[] data;
    public static final int LIST_CAPACITY = 10;
    
    public List() {/*empty*/}
    public List(int capacity) {}
    public boolean isEmpty() {}
    public int get(int pos) {}
    public void display() {} 
    public void insert(int item, int pos) {}
    public void remove(int pos) {}
}
```

### Method Definitions
```java
public List() { // default constructor
    size = 0;
    data = new int[LIST_CAPACITY];
}

public List(int capacity) {
    size = 0;
    data = new int[capacity];
}

public boolean isEmpty() {
    // don't use conditional
    return size == 0;
}

public int get(int index) {
    if (index < 0 || index >= size) { // check for valid index
        System.out.println("Invalid index"); 
        return -1; // return a fake value of not
    } else {
        return data[i]; // else, return correct value
    }
}

public void display() {
    for (int i = 0; i < size; i++) { // print values separated by spaces 
        System.out.print(data[i] + " ");
    }
    System.out.println(); // end with newline
}

public void insert(int value, int pos) {
    if (size == data.length) { // check if there's space
        System.out.println("List at capacity");
        return;
    }
    
    if(pos < 0 || pos > size) { // check for valid position
        System.out.println("Invalid position");
        return;
    }
    
    for (int i = size; i > pos; i--) { // shift right
        data[i] = data[i - 1];
    }
    
    data[pos] = value; // add to array
    size++; // increment size of array
}

public void remove(int pos) {
    if (isEmpty()) { // check if list is empty
       System.out.println("Empty list"); 
       return;
    }
    
    if (pos < 0 || pos >= size) { // check for valid position
        System.err.println("Invalid position");
        return;
    }
    
    for (int i = pos; i < size-1; i++) { // shift left
        data[i] = data[i + 1];
    }
    
    data[size] = null; // unset reference to first shifted element
                       // only for objects
    size--; // decrement size;
}
```

### Example Run:
```java
List a = new List();

System.out.println("Inserting 100 at position 1");
a.insert(100, 1);

System.out.println("Inserting 100 at position 0");
a.insert(100, 0);

System.out.println("Inserting 200 at position 0");
a.insert(200, 0);

System.out.println("Inserting 300 at position 1");
a.insert(300, 1);
```