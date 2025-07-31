# Strings & Final

## String Concepts:
### Char Datatype:
* Doesn't really hold character data
  * Holds a small unsinged int value
  * `Character.MIN_VALUE = 0`
  * `Character.MAX_VALUE = 65,535`
* Can be assigned with integer or char value/literal
  * `char b = 'd'; // variable will hold 100`
  * `char c = 100; // will hold 100`
* When printed, prints ASCII (or Unicode UTF-8) value
  * `System.out.println(b); // will print letter 'd'`
  * `System.out.println((int) b); // will print 100`

### Are Strings Arrays of Chars?
* String is a class
* String variables have useful methods
* Strings are immutable

### Useful String Methods
```java
String s1 = "Hello";
String s2 = "hello";
System.out.println(s1.equals(s2)); // prints false
System.out.println(s1.equalsIgnoreCase(s2)); // prints true
```

* Can get a single character using `charAt()` (index from 0)
```java
char c1 = s1.charAt(1);
System.out.println(c1); // prints e
char c2 = s1.charAt(5); // StringOutOfBoundsException
```

### Strings are Immutable
* Immutable means: *cannot be changed*
* Ex: string s isn't changed:
```java
String s = "hello";
s = "goodbye";
```
* Creates new string & stores in `s`
* Everything in `s` is lost
  * *Replacing* something isn't the same as *changing* it
  * Understand Java's memory model for this to make more sense
## String Methods:
### Useful String Methods Pt. 1:
* `charAt()` useful to get a single character from a string
* `.toUpperCase()` and `.toLowerCase()` don't change the original string but return a new one with the changes applied

### Pt. 2:
* Check the contents of a string with `contains()`, returns a boolean
```java
String s1 = "hello";
if (s1.contains("ll")) {
    System.out.println("it matches");
}
```
* Find the location of contents with indexOf(), returns int

### Char Arrays from Strings:
* Can get `char` arrays from strings:
```java
String s1 = "mark";
char[] ca1 = s1.toCharArray();
char[] ca2 = "set".toCharArray();
char[] ca3 = {'g', 'o'}; // not fun to write
```

* `char` arrays are *mutable*!
```java
ca1[0] = 'd';
System.out.println(ca1); // prints "dark"
System.out.println(ca1[0]); // will print 'd'
```

* `char` arrays **cannot** change size

### Strings from Char Arrays
* `char` arrays don't have methods
```java
char[] ca = "mark".toCharArray();
ca[0] = 'd';
ca.toUpperCase(); // won't compile
```

* Get a string from a `char` array
```java
String s1 = ca; // won't compile
String s2 = new String(ca); // works fine
String s3 = s2.toUpperCase();
System.out.println(s3); // prints "DARK"
```

### Parse Strings w/ Integers:
* `Integer.parseInt()`
  * Takes a string parameter
  * returns or throws `NumberFormatException`
* Ex:
```java
String s1 = "1";
String s2 = "1.5";
String s3 = "one";
int i1 = Integer.parseInt(s1); // works fine i1 = 1
int i2 = Integer.parseint(s2); // Number format exception
int i3 = Integer.parseInt(s3); // Number format exception
```

## Final Variables:
### Concept of Final Variables:
* Java variables are: *named placeholders* with datatypes & values that can change
* Sometimes we don't want to change the value of a variable
* Arrays have fixed size
  * Length can't change unless a new array is created
  * Can be stored in the same variable
* Final variables are like const in c
  * Assigned once, can't be changed

### Final Variable Example:
* always named in `ALL_CAPS`
`final int FOO = 5;`
* Initialize separately
```java
final int BAR;

BAR = 5;
```

### Static Final Variables *Outside* of Main
* Final variables created outside of main can  be seen by all methods
* Must use static & final keywords
```java
public class MyClass{
    static final int SIZE = 10;
    
    public static void main (String[] args) {
        int[] a = new int[SIZE];
    }
    
    public static void someMethod() {
        System.out.println(SIZE); 
    }
}
```