# Recursive Methods in Linked Lists

### Traversal - Recursive Algorithm
1. If the list is empty, report & return
2. Else, start w/ 1st node
3. Tell node to print
4. Check for next node, & rerun step 3 for next()
5. Else, stop

### Display (Recursive Ex.) Code
**In LinkedList**
```java
public void display() {
    if (isEmpty()) {
        System.out.println("Empty!");
    } else {
        head.display(); // display node that head points to
    }
}
```
**In Node**
```java
public void display() {
    System.out.print(data + " ");
    if (hasNext()) {
        next.display();
    } else {
        System.out.println();
    }
}
```

-- Do the Exercise --