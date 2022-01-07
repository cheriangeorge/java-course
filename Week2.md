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
### Basic Datatypes in JAVA
* Java is a **strongly typed language**
  - statically typed - once defined cannot change
  - Constraints - In java `if(5){System.out.println("test");}` won't work - nothing other than boolean comparisons in conditional statements
* **Scalar types** 
  - In an object-oriented language, all data should be encapsulated as objects. However , this is cumbersome
  - Java allows scalar types, which are not objects
  - Useful to manipulate numeric values like conventional languages
  - Java has eight primitive scalar types
  - Size of each type is fixed by JVM. Does not depend on native architecture.
  - 2-byte char for Unicode.

|  Type | Size in Bytes  |
|---|---|
| int  | 4  |
| long  | 8  |
| short  | 2  |
| byte  |  1 |
| float  | 4  |
| double  | 8  |
| char  | 2  |
| boolean  | 1  |


* **Declarations, assigning values**
  - We declare variables before we use them
    ```java
    int x, y;
    double y;
    char c;
    boolean b1, b2;
    ```
  - The assignment statement works as usual
    ```java
    int x,y;
    x = 5;
    y = 7;
    ```
  - Declarations can include initializations
  - Characters are written with single-quotes (only)
    ```java
    char c,d;
    c = ’x’;
    d = ’\u03C0’; // Greek pi, unicode
    ```
  - Double quotes denote strings  
  - Boolean constants are true, false
    ```java
    boolean b1, b2;
    b1 = false;
    b2 = true;
    ```

* **Initialization, constants**
  - Declarations can come anywhere. However, Use this judiciously to retain readability.
    ```java
    int x;
    x = 10;
    double y;
    ```
  - Initialize at time of declaration
    ```java
    int x = 10;
    double y = 5.7f;
    // Note: Append f after number for float, else interpreted as double
    ```
  - Can we declare a value to be a constant?
    ```java
    float pi = 3.1415927f;
    pi = 22/7; // Disallow?
    // Modifier final indicates a constant
    final float pi = 3.1415927f;
    pi = 22/7; // Flagged as error;
    ```
* **Operators, shortcuts, type casting**
  - Arithmetic operators are the usual ones
    `+`,`-`,`*`,`/`,`%`
  - **No** separate integer division operator `//`
  - When both arguments are integer, `/` is integer division 
    ```java
    float f = 22/7; // Value is 3.0
    // Note implicit conversion from int to float
    ```
  - No exponentiation operater, use `Math.pow()`
    `Math.pow(a,n)` returns a^n
  - Special operators for incrementing and decrementing integers
    ```java
    int a = 0, b = 10;
    a++; // Same as a = a+1
    b--; // Same as b = b-1
    ```
  - Shortcut for updating a variable
    ```java
    int a = 0, b = 10;
    a += 7; // Same as a = a+7
    b *= 12; // Same as b = b*12
    ```
#### Strings and arrays are objects in JAVA
* **Strings** 
  - String is a built in class
    `String s,t;`
  - String constants enclosed in double quotes
    `String s = "Hello", t = "world";`
  - `+` is overloaded for string concatenation
    ```java
    String s = "Hello";
    String t = "world";
    String u = s + " " + t; // "Hello world"
    ```
  - Strings are not arrays of characters
    Cannot write `s[3] = ’p’;` or `s[4] = ’!’;`
  - Instead, invoke method substring in class String
    `s = s.substring(0,3) + "p!";`
  - If we change a String, we get a new object
    - After the update, s points to a new String
    - Java does automatic garbage collection
* **Arrays** 
  - Arrays are also objects
  - Typical declaration
    ```java
    int[] a;
    a = new int[100];
    ```
    - Or `int a[]` instead of `int[] a`
    - Combine as `int[] a = new int[100];`
  - `a.length` gives size of a
    - Note, for String, it is a method `s.length()!`
  - Array indices run from 0 to `a.length-1`
  - Size of the array can vary
  - Array constants: `{v1, v2, v3}`
  - For example
    ```java
    int[] a;
    int n;
    n = 10;
    a = new int[n];
    n = 20;
    a = new int[n];
    a = {2, 3, 5, 7, 11};
    ```
### Control Flow in JAVA
* **Control Flow**
  - Program layout
    - Statements end with semi-colon
    - Blocks of statements delimited by braces
  - Conditional execution
    - `if (condition) { ... } else { ... }`
  - Conditional loops
    - `while (condition) { ... }`
    - `do { ... } while (condition)`
  - Iteration
    - Two kinds of `for`
  - Multiway branching – `switch`
* **Conditional Execution**
  - `if (c) {...} else {...}`
    - `else` is optional
    - Condition must be in parentheses
    - If body is a single statement, braces are not needed
  - No elif, like Python
    - Indentation is not forced
    - Just align else if
    - Nested if is a single statement, no separate braces required
  - No def for function definition
    ```java
    public class MyClass {
    ...
    public static int sign(int v) {
      if (v < 0) {
        return(-1);
      } else if (v > 0) {
        return(1);
      } else {
        return(0);
      }
     }
    }
    ```
* **Conditional Loops**
  - `while (c) {...}`
    - Condition must be in parentheses
    - If body is a single statement, braces are not needed
  - `do {...} while (c)` 
    - Condition is checked at the end of the loop
    - At least one iteration
    - Useful for interactive user input
      ```java
        do {
          read input;
        } while (input-condition);
      ```
   - Example
      ```java
      public class MyClass {
      ...
       public static int sumupto(int n) {
         int sum = 0;
          int i = 0;
          
          do {
            sum += i;
           i++;
          } while (i <= n);
        
          return(sum);
        
        }
        }
      ```
* **Iteration**
  - for loop is inherited from C
  - `for (init; cond; upd) {...}`
    - init is initialization
    - cond is terminating condition
    - upd is update
  - Intended use is `for(i = 0; i < n; i++){...}`
  - Completely equivalent to
    ```java
    i = 0;
    while (i < n) {
      i++;
    }
    ```
  - However, not good style to write `for` instead of `while`
  - Can define loop variable within loop
    - The scope of `i` is local to the loop
    - *An instance of more general local scoping allowed in Java*
  - Example :
    ```java
    public class MyClass {
      ...
      public static int sumarray(int[] a) {
        int sum = 0;
        int n = a.length;
        int i;
        // one method
        for (i = 0; i < n; i++){
          sum += a[i];
        }
        // another method
        for (int v : a){
          sum += v;
        }
        return(sum);
        }
        }
    ```
  - Iterating over elements directly **ALTERNATE SYNTAX**
    - Java later introduced a for in the style of Python
      ```java
      for x in l:
        do something with x
      ```
    - Another `for` syntax
      ```java
      for (type x : a)
        do something with x;
      }
      ```
      - loop variable must be declared in local scope for this version of `for`
* **Multiway Branching**
  - `switch` selects between different options
  - default is to *“fall through”* from one case to the next
    - Need to explicitly `break` out of switch
    - `break` available for loops as well
  - Options have to be constants. Cannot use conditional expressions 
  - here return type is `void`
    - `Non-void` return type requires an appropriate return value
  - Example :
    ```java
    public static void printsign(int v) {
      switch (v) {
        case -1: {
          System.out.println("Negative");
          break;
        }
        case 1: {
          System.out.println("Positive");
          break;
        }
        case 0: {
          System.out.println("Zero");
          break;
        }
      }
    }
    ```
### Defining classes and objects in Java
* A class is a template for an encapsulated type
* An object is an instance of a class
* **Defining a class**
  - Definition block using class, with class name
    - Modifier `public` to indicate visibility
    - Java allows `public` to be omitted
    - Default visibility is public to `package`
    - Packages are administrative units of code
    - All classes defined in same directory form part of same package
  - Example
      ```java
        public class Date {
          private int day, month, year;
          ...
        }
      ```
  - Instance variables
    - Each concrete object of type `Date` will have local copies of `date`, `month`, `year`
    - These are marked `private`
    - Can also have `public` instance variables, but breaks encapsulation
* **Creating objects**
  - Declare type using class name
  - `new` creates a new object
    ```java
      public void UseDate() {
        Date d;
        d = new Date();
        ...
      }
    ```
  - methods to update values ***Mutator Methods***
    - `this` is a reference to current object
    - Can omit `this` if reference is unambiguous
      ```java
        public class Date {
          private int day, month, year;
          public void setDate(int d, int m,int y){
            this.day = d;
            this.month = m;
            this.year = y;
          }
        }
      ```
  - Methods to read and report values ***Accessor Methods***
      ```java
        public class Date {
          ...
          public int getDay(){
            return(day);
          }
          public int getMonth(){
            return(month);
          }
          public int getYear(){
            return(year);
          }
        }
      ```
* **Initializing Objects**
  - Good to set up an object when we create it
    - Combine `new Date()` and `setDate()`
  - ***Constructors*** — special functions called when an object is created
    - Function with the same name as the class
    - `d = new Date(13,8,2015);`
        ```java
          public class Date {
            private int day, month, year;
            public Date(int d, int m, int y){
              day = d;
              month = m;
              year = y;
            }
            // Constructor with different signature
            public Date(int d, int m){
              day = d; month = m; year = 2021;
            }
          }
        ```
     - Constructors with different signatures
       - `d = new Date(13,8);` sets year to 2021
       - Java allows function overloading — same name, different signatures (Python: default (optional) arguments, no overloading)
     - A later constructor can call an earlier one using `this` . For Example in the code above the following block could be used.
        ```java
          public Date(int d, int m){
            this(d,m,2021);
          }
        ```
     - If no constructor is defined, Java provides a default constructor with empty arguments
        - `new Date()` would implicitly invoke this
        - Sets instance variables to sensible defaults
        - For instance, int variables set to 0
        - Only valid if *no constructor* is defined
        - Otherwise need an explicit constructor without arguments
* **Copy constructors**
  - Create a new object from an existing one
  - Copy constructor takes an object of the same type as argument
    - Copies the instance variables
    - Use object name to disambiguate which instance variables we are talking about
    - Note that private instance variables of argument are visible
      ```java
        public void UseDate() {
          Date d1,d2;
          d1 = new Date(12,4,1954);
          d2 = new Date(d1); //Copy constructor
        }
      ```
   - ***Shallow copy vs deep copy***
      - Want new object to be disjoint from old one
      - If instance variable are objects, we may end up aliasing rather than copying
      - cloning objects (Explore further)

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
* JAVA has call-by-vale only. Not call-by-reference.
