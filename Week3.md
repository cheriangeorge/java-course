## Week 3 Notes

### The Philosophy of Object Oriented Programming
* Algorithms + Data Structures = Programs
  - Title of Niklaus Wirth’s introduction to Pascal
  - Traditionally, algorithms come first
  - Structured programming
    - Design a set of procedures for specific tasks
    - Combine them to build complex systems
  - Data representation comes later
    - Design data structures to suit procedural manipulations

* Object Oriented Design
  - Reverse the focus
  - First identify the data we want to maintain and manipulate
  - Then identify algorithms to operate on the data
  - Claim: works better for large systems
  - Example: simple web browser
    - 2000 procedures manipulating global data
    - . . . vs 100 classes, each with about 20 methods
    - Much easier to grasp the design
    - Debugging: an object is in an incorrect state
    - Search among 20 methods rather than 2000 procedures

* Object Oriented design: Example
  - An order processing system typically involves
    - Items
    - Orders
    - Shipping addresses
    - Payments
    - Accounts
  - What happens to these objects?
    - Items are added to orders
    - Orders are shipped, cancelled
    - Payments are accepted, rejected
  - Nouns signify objects, verbs denote methods that operate on objects
    - Associate with each order, a method to add an item
* Designing Objects
  - Behaviour — what methods do we need to operate on objects?
  - State — how does the object react when methods are invoked?
    - State is the information in the instance variables
    - Encapsulation — should not change unless a method operates on it
  - Identity — distinguish between different objects of the same class
    - State may be the same — two orders may contain the same item
  - These features interact
    - State will typically affect behaviour
    - Cannot add an item to an order that has been shipped
    - Cannot ship an empty order
* Relationship between classes
  - Dependence
    - Order needs Account to check credit status
    - Item does not depend on Account
    - Robust design minimizes dependencies, or coupling between classes
  - Aggregation
    - Order contains Item objects
  - Inheritance
    - One object is a specialized versions of another
    - ExpressOrder inherits from Order
    - Extra methods to compute shipping charges, priority handling

### Subclases and Inheritance

* A Java class
  - An Employee class
      ```java
        public class Employee{
          private String name;
          private double salary;
          
          // Some Constructors ...
          
          // "mutator" methods
          public boolean setName(String s){ ... }
          public boolean setSalary(double x){ ... }
          
          // "accessor" methods
          public String getName(){ ... }
          public double getSalary(){ ... }
          
          // other methods
          public double bonus(float percent){
            return (percent/100.0)*salary;
          }
        }
      ```
       - Two private instance variables
       - Some constructors to set up the object
       - Accessor and mutator methods to set instance variables
       - A public method to compute bonus

* Subclasses
  - **Points**
    - A subclass extends a parent class
    - Subclass inherits instance variables and methods from the parent class
    - Subclass can add more instance variables and methods
      - Can also override methods
    - Subclasses cannot see private components of parent class
    - Use super to access constructor of parent class
  - Managers are special types of employees with extra features
    ```java
      public class Manager extends Employee{
        private String secretary;
        public boolean setSecretary(name s){ ... }
        public String getSecretary(){ ... }
      }
    ```
  - Manager objects inherit other fields and methods from Employee
    - Every Manager has a name, salary and methods to access and manipulate these.
  - Manager is a subclass of Employee
    - Manager is a subclass of Employee
  - Manager objects do not automatically have access to private data of parent class.
    - Common to extend a parent class written by someone else
  - How can a constructor for Manager set instance variables that are private to Employee?
  - Some constructors for `Employee`
  - Use parent class’s constructor using `super`
  - A constructor for `Manager`
     ```java
      public class Employee{
        ...
        public Employee(String n, double s){
          name = n; salary = s;
        }
        public Employee(String n){
          this(n,500.00);
        }
      }
      
      public class Manager extends Employee{
        ..
        public Manager(String n, double s, String sn){
          super(n,s); // super calls Employee constructor
          secretary = sn;
        }
      }
     ```
* Inheritance
  - In general, subclass has more features than parent class
    - Subclass inherits instance variables, methods from parent class
  - Every Manager is an Employee, but not vice versa!
  - Can use a subclass in place of a superclass
    - `Employee e = new Manager(...)`
  - But the following will *not work*
    - `Manager m = new Employee(...)`
  - The seemingly redundant reference to `int` in `new`
    - `int[] a = new int[100];`
  - One can now presumably write
    - `Employee[] e = new Manager(...)[100]`

### Dynamic dispatch and polymorphism
* Subclasses and inheritance
  - A subclass extends a parent class
  - Subclass inherits instance variables and methods from the parent class
  - Subclasses cannot see private components of parent class
  - Subclass can add more instance variables and methods
  - Can also override methods
    ```java
      public class Employee{
        private String name;
        private double salary;
        public boolean setName(String s){ ... }
        public boolean setSalary(double x){ ... }
        public String getName(){ ... }
        public double getSalary(){ ... }
        
        public double bonus(float percent){
          return (percent/100.0)*salary;
        }
      }
      public class Manager extends Employee{
        private String secretary;
        public boolean setSecretary(name s){ ... }
        public String getSecretary(){ ... }
      }
    ```
* Dynamic dispatch
  - `Manager` can redefine `bonus()`
      ```java
        double bonus(float percent){
          return 1.5*super.bonus(percent);
        }
      ```
    - Uses parent class `bonus()` via `super`
    - **Overrides** definition in parent class
  - Consider the following assignment
    - `Employee e = new Manager(...)`
  - Can we invoke e.setSecretary()?
    - e is declared to be an Employee
    - Static typechecking — e can only refer to methods in Employee
  - What about e.bonus(p)? Which bonus() do we use?
    - Static: Use Employee.bonus()
    - Dynamic: Use Manager.bonus()
  - Dynamic dispatch (dynamic binding, late method binding, . . . ) turns out to be more useful
    - Default in Java, optional in languages like C++ (virtual function)
* Polymorphism
  - Every `Employee` in `emparray` “knows” how to calculate its bonus correctly!

# From Activity session
* final keyword for variable makes it immutable , method , class makes it uninheritable
* Access Specifiers in Java
  - public - anywhere
  - protected - within the same package + child class
  - default - within same package
  - private - within same class
* Packages - Like a directory or subfolder where we have a collection of classes interfaces and sub packages.

