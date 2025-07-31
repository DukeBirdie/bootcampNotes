# Advanced While Loops
## Loop Control
**Controlling Loops**
* Skip the condition: continue
  * Continue to next iteration
  * Don't run rest of the lines
  * Re-evaluate condition (can exit loop if condition is false)
* Early exit: break
  * Used to stop the loop
  * Don't run the rest of the lines
  * Don't re-evaluate the condition
**Basic While Loop Syntax:**
```
while (boolean condition) {
    loop body (can be many lines)
    update loop variable (can be at top of body)
}
```

### Pre & Post-Increment / Decrement:
* The increment **(++)** and **(--)** operators are special
  * If placed after the operand "i++", they happen last -- even after assignment
  * If placed before the operand, they happen first
* Pre-increment example
```java
int x = 0;
System.out.println(++x); // prints 1, x is now 1
```
* Post-decrement example
```java
int x = 1;
System.out.println(x--); // prints 1, x is now 0
```
## Nested Loops:
* Loops inside loops
* Inner loop & outer loop
* If the outer loop never runs, the inner loop never runs
* For each iteration of the outer loop, the inner loop may run many iterations
* Should almost always have separate loop variables

## Do-While Loops:
* While loop
  * Evaluate condition
  * Iterate as long as a condition is true
  * Minimum iterations: 0
* Do-While Loop
  * Perform first iteration
  * Check condition at the end
  * iterate as long as condition is true
  * Minimum iterations: 1
```
do {
  loop body (can be many lines)
  update loop variable (can be at top of body)
  
} while (boolean condition);
```

# For Loops and Loop Tables
* Allow repeated behavior
  * Recursion is another method for repeating behavior
  * Older programming languages supported goto
* While loops reapeat as long as a specific condition is true
  * Structurally similar to if conditionals
  * Can run anywhere from 0 to many times
* Each cycle of the loop is called an iteration
  * A loop iterates
  * From the Latin *iterum* which means again

### For Loops:
**Part 1:**
* Almost always an int
  * Typically named *i*, for an *iterator* or *index*
* Only run once
* Runs at the beginning of the loop
* Scope of the loop variable *if created for the loop*
  * Only exists in the loop
  * Destroyed (freed) when the loop ends
* Technically optional (can just put in the semicolon)
**Part 2:**
* Must be boolean expression
* Run at the beginning of iteration of the loop
  * If true, loop body and update will execute
  * If false, loop will end, code will continue from line after the loop
* Typically one of three forms
  * `i < [some number or variable]`
  * `i >= [some number or variable]`
  * `i != [some number or variable]`
* But any Boolean expression is OK
  * Only required part of a for loop








