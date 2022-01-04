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
