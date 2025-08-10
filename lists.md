# Lists
## Object Arrays:
* Object arrays start empty
  * Don't contain objects
  * Elements are null
* Array element holds a reference to an object

### Example:
* Create an arr to hold 10 strings
* Printing each string will result in `null` being printed
```java
String[] names = new String[10];

for (int i = 0; i < names.length; i++) {
    System.out.println(names[i]);
}
```
### Loading Array of Strings
* Each string loaded from user input
```java
Scanner in = new Scanner(System.in);
String[] names = new String[10];

for (int i = 0; i < names.length; i++) {
    System.out.print("Enter a name: ");
    String name = in.next();
    names[i] = name; // or names[i] = in.next();
}
```

* Since array element are all objects
  * Can call methods

### DayOfYear Example
```java
DayOfYear[] may = new DayOfYear[31];

for (int i = 0; i < names.length; i++) {
    may[i] = new DayOfYear(5, (i + 1));    
    System.out.println(may[i]);
}
```
## Lists of Objects:
### Adding Objects to an Array:
```java
Person[] classRoster = new Person[5];

Person p1 = newPerson("Sultan", 27);
classRoster[0] = p1;

... etc.

// can also do:
classRoster[1] = new Person("Kyle", 21);
```

