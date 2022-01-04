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
* Modifier **public** specifies visibility
* Fix a function name that will be called by default - From C, the convention is to call this function **main()**
* Specify input and output types for main()
  - The signature of main()
  - **String[] args** Input parameter is an array of strings; command line arguments 
  - **void** No output, so return type. Implicit return type of main is int

### From Activity Questions 
* Strings are fixed immutable **objects** - Any function to modify a string returns a new string. **name1.concat(name2)** creates a new string. Strings are not an array of characters.
* For a variable if you use final it cannot be reassigned.
* String - length method 
* Character must be single quoted 
* final needs to always be initialised. 
* if and switch are conditional statements

* Among logical operators Not has heighst precedence followed by And (If the left side operand is False the result is always False. Only if it is true need to check the right side.)
