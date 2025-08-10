*Make sure to do the "demo- adding google guava to an IDEA project" thing above this*
# Formatted Printing

## `printf` and `String.format()` Basics
### Printing Formatted Text
* Two choices for printing formatted text
* String concatenation (easier to read but awkward to type and slow)
* StringBuffer/StringBuilder (faster, but long code)
```java
StringBuffer sb = new StringBuffer("The sum of ");
sb.append(a).append(" and ").append(b);
sb.append(" is ").append(a + b);
String s = sb.toString();
```

### `String.format()`
* Static method on String
* Returns new String object
* Combines
  * A string
  * Formatting Placeholders
  * Arguments to substitute for the placholders

### Comparing Concatenation to Formatted Text
* String concatenation
`String s = "The sum of " + a + " and " + b + " is " + (a + b);`
* String.format()
`String s = String.format("The sum of %d and %d is %d", a, b, (a+b));`

### String.format() placeholders
* %s -> string
* %d -> (base 10) integer
* %f -> float
* %b -> boolean

### Print Directly with printf()
* String concatenation
`System.out.println("The sum of " + a + " and " + b + " is " + (a+b));`
* printf
`System.out.printf("The sum of %d and %d is %d.", a, b, (a+b));`

## Padding and Shortening
### Several Ways to Pad & Shorten
* For all data
  * Right align, `%Nt`, where N is the number of spaces to pad and t is the type
  * Left align, `-%Nt`, where N is the number of spaces to pad and t is the type
  * This is a minimum, not a maximum
* For floats, shorten and round *output*
  * If no specified size, `%f` prints 6 digits past the decimal place
  * `%.Nf`, where N is the number of decimal places
  * Doesn't change the underlying number
* Two can be combined

### Example:
```java
double u1 = 0.0859163, u2 = 859163.0004, u3 = 1.0;

System.out.printf("[%f] - [-%f] - [%5.2f]\n", u1, u2, u3);
// outputs: [0.085916] - [  859163.000400] - [1.00]
// can have different combinations of the formatting items
```