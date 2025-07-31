# Methods

### Method Inputs
* Methods can have 0 to many inputs
  * Called parameters (or arguments)
* Each parameter is specified as a variable
  * Datatype
  * Name
* To call the method, values *must be specified for each parameter*

### Method Names
* Each method must have a unique name
* The name should be descriptive
* Most method names:
  * Are verbs - run, print, etc.
  * Verb phrases - addTwo, printContents, etc.

### Method Returns
* A method can return a *single* value
* The datatype of the value must be specified
  * Cannot change
  * Can return *one value* of any type
* The method must include 1 or more explicit returns
  * The keyword `return` must be used
  * A return value must follow that `return 10`
  * Return immediately ends the method (similar to `break`)
* Can write methods that never return a value
  * Its return type is `void`

## Writing Methods
### Naming Parameters
* Names should be
  * Clear 
  * Indicate the role of the parameter
* Examples:
  * `int x` vs. `int repeats`
  * `double u` vs. `double height`
* Don't waste time with badly named variables

## Method Definitions
* Start with the method *signature* what makes a method unique
  * Static keyword
  * return type 
  * name
  * parameters
* Method defined in a block of code (between `{}`)
* Each path through the method must end in a return
  * Must include a value of the appropriate type
  * With the exception of `void`

### Example Method Definitions:
```java
static int doubleNumber(int input) {
    return input * 2;
}
static void printIfOdd(int input) {
    if (input % 2 == 0) {
        System.out.println(input);
    }
}
```

