# References
### `variables != objects, objects != variables`
```java
StringBuffer sb = new StringBuffer("A");
sb.append("B");
sb = new StringBuffer("cde");
```
### Passed References Are Copies
* Only a copy of the original reference is passed
* If you change the array or variable that it's referring to, the calling method's data won't change
```java
public static void main(String[] args) {
    int[] x = {10};
    changeMe(x); // after the call, x still refers to the og. array (prints 10)
    System.out.pringln(x[0]);
}

public static void changeMe(int[] a) {
    int[] b = {5};
    a = b; 
}
```

### Attributes are Shared Variables
```java
public class List {
    int[] data = new int[10];
    int size = 10;
    
    public void resize() {
        int[] copy = new int[data.length * 2];
        for (int i = 0; i < data.legnth; i++) {
            copy[i] = data[i];
        }
        data = copy;
    }
}
```

### Immutable Objects
* Immutable objects can't be changed
* String doesn't change
  * `toUpperCase()` doesn't change the object
  * Instead returns new string with all uppercase letters

```java
String s1 = "hello";
String s2 = s1.toUpperCase();
System.out.println(s1); // prints hello
System.out.println(s2); // prints HELLO
```

### Calling Methods on Object References
* Outside object, call methods on object
```java
public static void main(String[] args) {
    Foo f = new Foo();
    f.runA();
}
```
* Inside of object, can call methods w/o object reference
```java
class Foo {
    public void runA() {
        runB(); 
    }
    public void runB() {}
}
```
# `this`
* Inside of object, can reference the local object
* Alias (phrase used to access): `this`
```java
public class Foo {
    public void runA() { 
        this.runB(); 
    }
    public void runB() {}
}
```

### The Naming Scope Problem
* Two can have the same name but different scope
  * Local variable (parameter)
  * Attribute (part of the object)
* Which one is printed?
```java
public class Foo {
    int x = 5;
    public Foo(int x) {
        System.out.println(x); 
    }
    
    public static void main(String[] args) {
        Foo f = new Foo(10); // i think 10 is printed, because parameter overrides global scope
    }
}
```

### `this` Resolves the Naming Scope Problem
* Can use `this` to explicitly refer the attribute
```java
public class Foo {
    int x = 5;
    public Foo(int x) {
        System.out.println(x); // prints 10
        System.out.println(this.x); // prints 5
    }
    public static void main(String[] args) {
        Foo f = new Foo(10); 
    }
}
```
* Inside of an object, can reference the local object

`this` Simplifies Parameter Naming
* Can use `this` to explicitly refer to the attribute
```java
public class Person {
    String name;
    
    public Person(String name) {
        this.name = name; // don't use: name = this.name; 
    }
    public void setName(String name) {
        this.name = name;
    }
}
```
* Don't need different names

### Problem: Repeated Code in Constructors
```java
public class List {
    int size; 
    int[] data;
    public static final int LIST_CAPACITY = 10;
    
    public List() {
        this.size = 0; 
        this.data = new int[LIST_CAPACITY];
    }
    
    public List(int capacity) {
        this.size = 0;
        this.data = new int[capacity];
    }

}
```
### Can't Explicitly Invoke Constructors
```java
public class List {
    int size;
    int[] data;
    public static final int LIST_CAPACITY = 10;
    
    public List() {
        new List(LIST_CAPACITY); // creates entirely separate list object
    }
    public List(int capacity) {
        this.size = 0;
        this.data = new int[capacity];
    }
}
```
### `this` Simplifies Constructors With Delegation
```java
public class List {
    int size;
    int[] data;
    public static final int LIST_CAPACITY = 10;
    
    public List() {
        this(LIST_CAPACITY); // constructor delegation
    }
    public List(int capacity) {
        this.size = 0; 
        this.data = new int[capacity];
    }
}
```
# Static Methods & Attributes
* Attributes are properties of objects
  * "This marker's color is red"   
    * `private String color;`
  * "Olivia's age is 20"
    * `private int age;`
* Methods are things objects can do
  * "This marker can open"
    * `public void open();`
  * "This bank account can take a deposit"
    * `public boolean deposit(double amount);`
* Objects are instances of a class 

### Methods & Attributes Belong to Objects
* Objects are instances of a class
  * Attributes are sometimes called *instance attributes*
  * Methods are sometimes called *instance methods*
* Sometimes methods or attributes are not specific to an object
  * "How many BankAccount objects have been created?"
  * "What is a list of all colors that can be used?"
* These can be called *class methods* and *class attributes*
* The other term for these is *static* methods and attributes

### Static Methods & Attributes
* Static methods and attributes belong to a class
  * You don't need an instance (object) of that class to use them
* To make a method or attribute static
  * Use keyword `static` after visibility but before the datatype/return type
* Static Methods
  * Cannot access instance (non-static) attributes
* Static attributes
  * Can be accessed by static and instance (non-static) methods

### Example - Final Attributes
```java
public class List {
    public static final int DEFAULT_LIST_SIZE = 10;
}
public static void main(String[] args) {
    System.out.println(List.DEFAULT_LIST_SIZE);
}
```

### Example Counting Instances 
```java
public class Account {
    private static int numberOfAccounts = 0;
    
    public Account() {
        numberOfAccounts++; // when constructor is initialized, increment instance counter 
    }
    
    public static int getNumberOfAccounts() {
        return numberOfAccounts;
    }
}
```

### Example Color List
```java
public class Color {
    private static Color[] allColors = new Color[10];
    private static int colorCount = 0;
    private String name;
    
    public Color(String name) {
        this.name = name;
        if(colorCount > allColors.length) {
            System.out.println("too many colors");
        } else {
            allColors[colorCount++] = this; // everytime a color is added to allColors with this -> increment colorCount
        }
    }
}
// pt2
public String toString() { return this.name; }

private static String listAllColors() {
    if (colorCount == 0) {
        return "no colors";
    }
    StringBuffer sb = new StringBuffer();
    for (int i = 0; i < colorCount; i++) {
        sb.append(allColors[i].append(" "));
    }
    return sb.toString();
}
```

