# Programming Paradigms and OOP

## Programming Paradigms:
### Defining Programming Paradigms
* All programming involves abstraction
  * From the Latin word *abstrahere*: to draw away
  * Taking relevant aspects of a problem
* Different programming languages require different forms of abstracton
  * Major categories called *paradigms*
  * A *paradigm* is a worldview that underlies all thought or work

### Programming Language (PL) Paradigms
General-Purpose Programming Languages (Imperative Languages & Declarative Languages)
Imperative Languages (Object Oriented Languages & Procedural Languages)
Declarative Languages (Functional Programming Languages & Logic Programming Languages)

### PL Domain Categories
* Imperative
  * Specify what the computer does
  * Must explain all actions
  * Allows for fine control
* Declarative
  * Tell comp. what you want
  * Let comp. decide how to do work
  * Very high-level algorithm descriptions

### Imperative Programming Categories
* Procedural
  * Procedure: unit of code or set of stored actions
    * Also called functions, subroutines, or methods
  * Best for batch-processing or small tasks
* OOP Languages
  * Class or Object: Unit of code
  * Objects are defined as discrete entities
  * Can build large, flexible systems
    * High reusability
  * Most popular paradigm for professional development

### Imperative Lng. Ex:
* Procedural
  * C
  * COBOL
  * BASIC
  * PHP
  * Assembly
* OO 
  * Smalltalk
  * C++
  * Objective C
  * Java
  * JavaScript
  * C#
  * Python

### Declaring Programming Categories:
* Functional Programming (FP) Languages
  * Built around mathematical definitions
  * Relationship between 2 sets
    * domain and codomain
    * each value in domain has exactly 1 corresponding value in codomain
* Logic Programming (not logical programming) Languages
  * System is expressed in terms of relationships
    * Defined with formal logic
  * Less commonly used in general software development

### Declarative Languages Ex:
* FP Languages
  * Lisp
  * Scheme
  * Haskell
  * F#
* Logic Programming Languages
  * Prolog
  * Prolog variants
  * Rule-based programming langs.
    * R++
    * Jess

### Domain-Specific Programming Languages
* Designed to solve particular problem
* Not useful for broad range of problems
* Typically declarative
* Ex:
  * SQL, only used for db access
  * R, only used for statistical analysis

### Functional Equivalence
* All general purpose prg. lang.
  * Functionally equivalent
  * No language is better than another
  * Are Turing complete
* Non-Turing languages exist to solve special problems
  * Not general purpose
* Choosing a language depends on the problem & your skills

## Object-Oriented Programming in Java:
### C++ is Derived From C, Java from C++
* C was developed in 1969 & beyond
  * Support for low-level (close to hardware)
  * Support for high-level (close to the world)
  * Very influential
  * Core sy(ntax used in Java, C++, C#, Objective C, and many other languages
* C++ Developed in early 1980s 
  * Added OOP features to C
  * C++ compilers can usually compile c
* Java created in early 1990s
  * Response to C++
  * Addressed many issues in C++

### Objects & Classes
* Objects are instances 
  * Datatype is a class
* In java files must:
  * Contain no more than 1 public class
  * Have the same name as the public class
* The public class `Foo` must be in the file `Foo.java`
* Objects are complex data types
* Objects have agency
  * Know things
  * Can do things

### Object Concepts
* Objects know things
  * Called *attributes*
    * Sometimes instance or member variables
* Objects can do things
    * Called *methods*
      * Sometimes member methods
* Objects are discrete
  * Accelerating CarA won't change CarB
  * Reading from a System.in Scanner won't alter FileReader Scanner

### Implementing Classes
* Attributes
  * Variables declared outside methods
  * Declared `private`
  * Can only be accessed by methods (scope)
* Methods
  * Can (see & change) attributes
  * Typically declared `public`
  * Can be invoked on objects
* Constructors
  * Special method
    * Has no return type
  * Only invoked when instantiating (creating) objects with `new`

### Example Class- Person:
```java
class Person {
    private String name;
    private int age;
    
    public Person(string n, int a) {
        name = n;
        age = a;
    }
    
    public void display() {
        System.out.println(name + ", age " + age); 
    }
}
```

### Using Person Class
```java
public static void main(String[] args) {
    Person p1 = new Person("Kyle", 21);
    Person p2 = new Person("Arjun", 21);
    p1.display();
    p2.display();
}
```

** Don't do:**
`Person p2 = new Person("Kyle", 21).display();`

### Object Declaration and Method Invocation
```java
Student a = new Student();
Student b = new Student();
a.set("Kyle", 123455, 3.2);
b.set("Arjun", 123466, 4.2);

// prints name, ID, GPA
a.display();

b.display();
b.setGPA(3.7);

// prints updated information for b
b.display();
```
## Special Methods:

### toString
* Converts object to String
  * Should **NOT** print anything
  * Should create & return a string representation of the object
* Automatic invocation
  * Can use almost any object **anywhere** a string is expected
  * toString is automatically invoked
* Default behavior
  * returns class name & memory address

### Default Behavior:
```java
public class Foo {
    int bar = 5;
    double quix = 0.5;
    
    public static void main(String args) {
        Foo f = new Foo();
        System.out.println(f);
    }
}
```

### toString Implemented Behavior
```java
public class Foo {
    int bar = 5;
    double quux = 0.5;
    
    public static void main(String[] args) {
        Foo f = new Foo();
        System.out.println(f);
    }
    
    public String toString() {
        return "Total Value: " + (bar + quux);
    }
}
```

### Constructors:
* Only used to instantiate new objects of the class
  * Overloadable 
    * Can have multiple with different parameters
    * No return type
    * Always named the same as class
  * Default constructor
    * Automatically created
    * Takes no parameters and does nothing
    * Automatic one is lost if any constructors are created

### Example Class w/ Default Constructor
```java
public class Person {
    String name;
    
    public static void main(String[] args) {
        Person p = new Person(); 
        System.out.println(p);
    }
    
    public String toString() {
        return "Name: " + name;
    }
}
```

*Prints:*

**Nothing... I'm pretty sure**

### Overridden Default Constructor
```java
public class Person {
     public Person() {
         System.out.println("I don't do much");
     }
     
    public static void main(String[] args) {
         Person p = new Person();
         System.out.println(p);
    }
}
```
*Prints:*

I don't do much

### Parameterized Constructor
```java
public class Person {
    public Person(String n) {
        System.out.println("I take a parameter");
    }
    
    public static void main(String[] args) {
        Person p = new Person("Kazu"); 
        System.out.println(p);
    }
}
```
*Prints:*

I take a parameter

Kazu 

### Overloaded Constructors
```java
public class Person {
    public Person() {
        System.out.println("I don't do much");
    }
    public Person(String n) {
        System.out.println("I take a parameter");
    }
    public static void main(String[] args) {
        Person p1 = new Person();
        Person p2 = new Person("Kazu");
        System.out.println(p1);
        System.out.println(p2);
    }
}
```
*Prints:*

I don't do much

I take a parameter

Kazu
