# Generics, ArrayList, Comparable
## Generics(Templates) and Wrapper Classes
Look at Generic Notes
## `ArrayList`
Look at ArrayList Notes
## Sorting `ArrayList`s and `Comparable`
### Sorting `ArrayList` is Easy
```java
ArrayList<String> al = new ArrayList<>();
al.add("Goodbye");
al.add("Hello");
al.add("Ciao");

Collections.sort(al);

for(String s : al) {
    System.out.print(s + " ");
}
// Prints: "Ciao Goodbye Hello"
```

### Review - `.equals()` isn't automatic
```java
public class Foo {
    int x;
    public Foo(int x) {
        this.x = x; 
    }
    
    public static void main(String[] args) {
        Foo f1 = new Foo(5); 
        Foo f2 = new Foo(5);
        System.out.println(f1.equals(f2)); // prints false
    }
}
```

### Review - How to Implement `.equals()`
```java
public class Bar {
    int x;
    public Bar(int x) { this.x = x; }
    
    public boolean equals(Bar b) { return this.x == b.x; }
    
    public static void main(String[] args) {
        Bar f1 = new Bar(5); 
        Bar f2 = new Bar(5);
        System.out.println(f1.equals(f2)); // prints true
    }
}
```

### The `Comparable` Interface
* Interfaces are commitments to implement methods
  * Added the class declaration - `implements InterfaceName`
  * Like `throws` clause is added to a method declaration
  * Java can then use those methods
* The `Comparable` interface defines a method for ordering two objects
  * `public int compareTo(ClassName n);`
  * The local object(`this`)
  * A parameter (named in the method, in this case n)

### How to Implement `Comparable` and `compareTo`
```java
public class Bar implements Comparable<Bar> {
    int x;
    public Bar(int x) { this.x = x; }
    
    public String toString() { return new String(x); }
    
    public boolean equals(Bar b) { return this.x == b.x; }
    
    public int compareTo(Bar b) { /* return correct value */}
}
```

### Correct way to implement `compareTo()`
```java
public class Bar implements Comparable<Bar> {
    int x;
    public Bar(int x) { this.x = x; }
    public boolean equals(Bar b) { return thix.x == b.x; }
    
    public String toString() {
        return new String(x); 
    }
    
    public int compareTo(Bar b) {
        return this.x - b.x; 
    }
}
```

### Implementing `compareTo()` for a `Money` Class
```java
public class Money implements Comparable<Money> {
    int dollars;
    int cents;
    public Money(int dollars, int cents) {
         
    }
    
    private int toIntValue() {
        return (this.dollars * 100) + this.cents; 
    }
    
    public int compareTo(Money amount) {
        return this.toIntValue() - amount.toIntValue();
    }
}
```

Do Exercise