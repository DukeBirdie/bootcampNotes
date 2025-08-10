# Class Diagrams

### Class Diagrams
* Part of the Unified Modeling Language (UML)
* A standard way to visually describe
  * Classes
  * Relationships between classes
  * Attributes (member variables)
  * Methods (member functions)

### Example: Class Diagram
* Note that static methods/attributes should be underlined

Class: | AnotherClass:
+CONSTANTATTRIBUTE:type | -staticAttribute:type
-privateAttribute:type | -privateAttribute2:type
------------------------------------------------
+publicMethod(input:int):returnType | +publicMethod(name:string):returnType
-privateMethod() | +publicStaticMethod():returnType

### Class Diagram Syntax
* Format for attributes - `name:datatype`
``` 
name:String
top:int
```
* Format for method - `methodName(param:datatype):returntype`(unless void)
```
hasLargerBalance(comp:Account):boolean
setName(newName:String)
getName():String
```
* Modifiers
``` 
- == private
+ == public
```
* Simplify - assume all methods shown are public, and all attributes are private


### Final Notes About Class Diagrams
* Do NOT call them "UML Diagrams"
  * There are 11 types of UML Diagrams
  * This is only 1
* They show
  * Classes
  * Relationships between classes
  * Attributes
  * Methods
  * Mostly used to show private attributes and public methods



