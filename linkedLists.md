# Intro to Linked Lists

## Linked List Concepts
### Requirements for a List
* Construct empty list
* Insert element
* Remove element
* Check if list empty
* Display all elements in list
* Not have blank elements (gaps) in list 

### Linked List
* Elements stored non-contiguously
  * Link connects element to successor
  * Series of *nodes* (aka: elements)
* Each node has 2 parts
  * Data part
  * Link to next node
  * Sometimes link to prev node
* Node Links
  * Java uses object (reference) variables
  * if next == null, at end of list
## Implementing a Linked List
### Traversal Code:
```java
public void display() {
    if (isEmpty()) {
        System.out.println("Empty!");
        return;
    }
    
    Node next = first;
    while (next != null) {
        Sytem.out.println(next.getData());
        next = next.getNext();
    }
}
```

-- Note --
Example Code for Adding, Removing, and Appending (Empty & Non-empty lists)
Not available
Must write myself... :)