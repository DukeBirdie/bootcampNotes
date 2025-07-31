# File I/O
## Data Streams
### Including Libraries:
* *Examples:*
  * `import fully.qualified.classname;`
  * `import all.class.in.directory;`
* Real Library Examples:
  * `import java.util.Random;`
  * `import java.util.Scanner;`
  * **DON'T**
  * `import java.util.*;`
## File Streams for Reading
**Creating and Opening Files:**
```java
import java.io.FileReader;
class Main {
    public static void main(String[] args) {
        String filename = "hello.txt";
        FileReader fr = new FileReader(filename); // can also sub "hello.txt" for filename
    }
}
```
### Exceptions -- Runtime Errors
* Most common type of runtime errors in Java
* Some can be ignored unless they happen
  * Will cause a `java.lang.ArithmeticException: / by zero` if the user inputs 0
```java
Scanner s = new Scanner(System.in);
System.out.print("Enter a number: ");
int a = s.nextInt();
int b = 100/a;
``` 
* Some must be acknowledged or handled
  * Acknowledge with the `throws` clause
* IO Exceptions must be acknowledged or handled
  * Most Common - `FileNotFoundException`
*Fix the Exception for FileReader*
```java
import java.io.*; // change import
class Main {
    throws IOException;
    public static void main(String[] args) {
        String filename = "hello.txt";
        FileReader fr = new FileReader(filename);
        ...
        fr.close(); // don't forget to close files
    } 
}
```
**Use FileReader with Scanner**
* Scanner **can take any open source of data**
* Can be `System.in` (from the console) or a FileReader
* With Scanner can use `hasNext()`
  * `hasNext()` is a method that returns a boolean value
  * Can use as a boolean expression
### Files:
* Must be in the correct location -- the root of IDEA project
* Filenames must be exact (case sensitive)
* Files will often contain lists of data

### Reading Data in a Loop:
```java
FileReader infile = new FileReader("nums.txt");
Scanner f = new Scanner(infile);

int sum = 0, data;
while (f.hasNext()) {
    data = f.nextInt();
    sum += data;
}
fr.close();
System.out.println("Sum is: " + sum);
```
## File Streams for Writing
### The `java.io` Library - Overview
* FileReader
  * For opening and reading data from files
  * Use with Scanner
* FileWriter
  * For opening files and writing data to said files * PrintWriter
  * Print any type of data
* IOException
  * Errors in opening, reading from, or writing to files

### File Writer:
```java
import java.io.*; // don't do this
class Main {
    throws IOException;
    public static void main(String[] args) {
        String filename = "output.txt";
        FileWriter fw = new FileWriter(filename);
        ...
        fw.close();
    }
}
```
* FileWriter has 2 groups of methods
  * `write()` and `append()`
  * They do the same thing
* Only designed to write Strings


### FileWrite Overwrites!
* When FileWriter opens a file, it overwrites the existing contents
  * Can open a file for appending
* Use a second parameter when creating the FileWriter
  * Boolean expression
  * True - Append (add to the end)
  * False - Overwrite all data
*Example to Append:*
```java
String filename = "output.txt";
FileWriter fw = new FileWriter(filename, true);
PrintWriter pw = new PrintWriter(fw);
pw.println(5);
fw.close();
```

### Efficient File Reading:
* Scanner slow
* Buffering and flushing
  * `BufferedReader` and `BufferedWriter`