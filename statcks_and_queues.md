# Stacks and Queues
## Stacks:

### Stacks With Arrays:
### Defining a Stack:
* "A pile of things arranged one on top of another."
  * "You take the top one."
  * "When a new one is added, it's added at the top."
* *LIFO* - Last in First Out

### How to Make a Stack:
* Use a constructor to make an empty stack
* Check if the stack is emptpy
* Add element to top of the stack
* Popping
  * (Removing the top element) - Remember LIFO
* Getting top element
  * Get data of top element in a stack without modifying the data

### Stacks as ADTs (Abstract Data Types)
* Data
  * Collection of homogenous data items
  * Data is accessed at only one end (top)
* Operations
**Constructor: Construct an empty stack**
```java
boolean isEmpty() // check if empty
void push(data) // add element to the top
void top() // retrieve top element
void pop() // remove top element
```

### Implementing a Stack With a Static Array
* Array/Stack has specified and static size
* Elements that are pushed onto the stack must be held within the static data
* Requires 2 member variables
* Array called `data`
* Integer variable to keep the top index of the stack called `top`

### Stack Easier than List:
* Add Data: 
  * Increment top
  * Write to array
* Remove Data:
  * Decrement top
  * No need to shift array
  * Primitive data isn't removed from array
    * Objects are set to `null`

### Stack Implementation:
* Constructor
  * Init. empty stack `top = 1`
  * Check if empty - `top == -`
  * Push (if `data` isn't full)
    * If `top > data.length - 1`
    * Incrment top
    * Store value to push in `data[top]`
  * Top
    * If stack !empty, return `data[top]`
  * Pop
    * If stack !empty, decrement top 

### Stack - Class Outline:
```java
class Stack {
    public static final int STACK_CAPACITY = 128;
  int[] data;
  int top;
  
  public Stack() {}
  public boolean isEmpty() {}
  public void push(int value) {}
  public void display() {}
  public int top() {}
  public void pop() {}
}
```
### Stack - Method Definitions:
```java
// Complete implementation of stack constructor
public Stack() {
    data = new int[STACK_CAPACITY];
    top = -1; // top always starts @ -1
}

// complete implementation of isEmpty()
// stack with top = -1 is empty by definition
public boolean isEmpty() {
    return top == -1;
}

public void push(int value) {
    if (top < data.length-1) {
      ++top; // increment top first because we start at -1
      data[top] = value; // then place data in array 
    } else {
      System.out.println("**Stack full**");
      System.out.println("**Can't add new value**");
}
    
public void pop() {
    if (!isEmpty()) {
        // data[top] = null; // only if stack contains objects
      top--; 
    } else {
      System.out.println("**Stack empty**");
      System.out.println("**Can't remove value**");
}
    
public int top() {
      if (!isEmpty()) {
          return data[top];
      } else {
          System.out.println("**Stack Empty**");
          System.out.println("**Return garbage value**");
          return 0;
      }
}
    
// print in stack order, top first
public void display() {
    for (int i = top; i >= 0; i--) {
        System.out.println(data[i]);
    }
}
```
## Stacks in Method Calls (Also Known: Runtime Stacks):
### Call Stacks:
* Method can call another method
  * Current method's execution is put on pause
  * Run-time stack of OS stores address of current instruction
  * Execution control jumps to new called method
* When the called method ends
  * Return value is placed in a register
  * Original method resumes
* Call Stack stores return addresses in LIFO order

## Queues:
### Queue Concepts:
* **Queue:**
* A DS with FIFO
* Same type
* Accessed only at front (removal) and back (insertion)
  * Front: First element in queue
  * Back: Last element of queue

**Queue Operations:**
* Construct empty queue
* Check if empty
* Enqueue
  * Add element to back
* Dequeue
  * Remove element from front
* Front
  * Get value from front
* Display
  * Display all elements in queue

**Queue Implementation in Java:**
* Need array
  * Index from 0
* Front
  * Where queue starts
  * Where we remove from
* Back
  * Where queue ends
  * Where we add to

**Queue Class Outline:**
```java
class Queue {
    private static final int QUEUE_CAPACITY = 128;
  int[] data;
  int front;
  int back;
  
  public Queue() {}
  public boolean isEmpty() {}
  public void enqueue(int value) {}
  public void dequeue() {}
  public void display() {}
  public int front() {}
}

// Method definitions
// Constructor

public Queue::Queue() {
  data = new int[QUEUE_CAPACITY];
  front = 0;
  back = 0;
}

// isEmpty
public boolean Queue::isEmpty() {
    return front == back;
}

// enqueue
public void Queue::enqueue(int value) {
 int newBack = (back + 1) % data.length;
  if (newBack != front) {
    data[back] = value;
    back = newBack;
  } else {
      System.out.println("Queue full");
      System.out.println("Can't add new value");
  }
}

// dequeue
public void Queue::dequeue() {
    if (!isEmpty()) {
        front = (front+1) % data.length;
    } else {
        System.out.println("Queue empty");
        System.out.println("Can't remove a value");
    }
}

// front
public int Queue::front() {
    if (!isEmpty()) {
        return data[front];
    } else {
        System.out.println("Stack empty");
        System.out.println("Returning garbage value");
        return 0;
    }
}

// print
void Queue::display() const {
    for (int i = front; i != back; i = (i + 1) % data.length) {
       System.out.print(data[i] + " "); 
    }
    System.out.println(); // newline
}
```
```java
// queue example code
Queue q = new Queue();
q.enqueue(100);
q.enqueue(200);
q.enqueue(300);

int result = q.front();
q.dequeue();
q.enqueue(result);
q.display();
```

### Queue Example:
Queue: `100, 200, 300` 
Result = `100`
Dequeue Front
Queue: `200, 300`
Equeue Result
Queue: `200, 300, 100`

Exercise in other file


