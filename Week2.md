## Week 2 Notes 

### Java Syntax 

```Java
public class helloworld{
  public static void main(String[] args)
  {
    System.out.println("hello, world");
  }
}
```
* All code in Java lives within a class
  - No free floating functions (All functions must be within a class)
  - Modifier `public` specifies visibility for the class. Each program must have only one public class.
  - Function name that will be called by default - From C, the convention is to call this function `main()`
* Input and output types for main()
  - The **signature** of main() - `void` and `String[] args` 
  - `String[] args` Input parameter is an array of strings; command line arguments 
  - `void` No output, so return type. Implicit return type of main is int
  - Modifier `public` indicates that function is available to run from outside the class.
  - A class is a blueprint of an object
* Availability 
  - Functions defined inside classes are attached to objects.
  - `static` indicates that the function exists independent of dynamic creation of objects.
* Actual operation
  - `System` is a public class
  - `out` is a stream object defined in System (Like a file handle ; out must also ve static)
  - `println()` is a method associated with streams (Prints argument with a newline)
* Blocks and Statements are delimited by punctuation `{` , `}` , `;`
### Compiling and running Java code
* A Java program is a collection of classes
* Each class is defined in a separate file with the same name, with extension *.java*
  - Class helloworld in helloworld.java
* Java programs are interpreted on Java Virtual Machine (JVM)
  - JVM provides a uniform execution environment across operating systems
  - Semantics of Java is defined in terms of JVM, OS-independent
  - **Write once, run anywhere** - Code is guaranteed to be portable
* `javac` compiles into JVM bytecode
  - `javac helloworld.java` creates bytecode file `helloworld.class` 
  - javac requires .java extention
  - javac automatically follows dependencies and compiles all classes required
  - Sufficient to trigger compilation for class containing main()
  - `java helloworld` interprets and runs bytecode in `helloworld.class`
  - java should not be given .class extention.

### From Activity Questions 
* Strings are fixed immutable **objects** - Any function to modify a string returns a new string. **name1.concat(name2)** creates a new string. Strings are not an array of characters.
* For a variable if you use final it cannot be reassigned.
* String - length method 
* Character must be single quoted 
* final needs to always be initialised. 
* if and switch are conditional statements
#### Short circuit operations 
* Among logical operators Not has heighst precedence followed by And (If the left side operand is False the result is always False. Only if it is true need to check the right side.)

#### Additional Discussion Points
* Code motion in Compiler optimisation 
  - Loop unrolling . String.length is not recomputed in every iteration.
