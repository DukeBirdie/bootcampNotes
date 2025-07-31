## While Loops, Review, and Turing Machines

### Definition:
Any system that can do what a Turing machine can do will (eventually)
be able to compute anything that can be computed.

### Functional Equivalence:
* Using functions as substitutes for repeatable code

### What can a Turing machine do?
* Store data
  * Literals, datatypes, variables
* Manipulate data
  * Operators
* Make decisions
  * Conditionals
* Repeat behavior
  * Loops

### Loops:
* Allow *repeated* behavior
  * Recursion is similar to loops
  * Goto (used in older prg. languages)
* While loops repeat until their conditional is no longer true
* Each cycle is called an iteration
  * From the Latin word *iterum*, which means "again"

### Check User Input:
```java
String input = "Y";
Scanner s = new Scanner(System.in);
while(input.equals("Y") || input.equals("y")) {
    System.out.print("Continue? (y/n): ");
    input = s.next();
}
```
Can also use `input.equalsIgnoreCase("Y")`

## Flowcharts
* Describe conditional processes
* Express logic visually
* Design conceptually rather than through code
* *Not all detail is necessary*

### Concepts:
* Graphs
  * Nodes that connect to other nodes
* Flowcharts have 3 features
  * Processes (boxes)
  * Decisions (diamonds)
  * Directed arcs (arrows)
* Processes & Decisions are both nodes

### Processes:
* An event that happens
* Can't be a condition
* Straightforward
* *Examples:*
  * Create integer variable foo
  * Add one to foo
  * Print foo

### Decisions:
* Must be a question with a **yes/no answer**
* *Good* Examples:
  * Is foo > bar?
  * Is the user-entered password == to the stored password
* *Bad* Examples:
  * Which is greater? Foo or bar?
  * How many times has this process been run?
* *If the question doesn't have a **yes/no answer** it's a bad question*
  * May need multiple decisions

### Directed Arcs:
* Just arrows from one node to the next
* From processes:
  * Only one outgoing arrow
  * No label
* From decisions
  * Exactly 2 outgoing arrows
  * Labeled "Yes" or "No"
* Any node can have multiple *incoming* arrows
  * Processes can **converge**
  
### To view flowcharts:
*Go to: https://csumb.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=a8c6b42e-4d12-4305-ab8e-afa000391125*

