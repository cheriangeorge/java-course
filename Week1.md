## Week 1 Notes 

### Compiler vs Interpreter:
* Compiler needs entire program to be loaded in RAM while interpreter loads just one line into buffer
* Compiler is faster than interpreter 
* Memory requirement for interpreter is very low (Usually used in memory constrained devices)
* Explore : Which runs faster - Compiled code or interpreted code ? 
* Speed of Execution in a compiler and interpreter
  - Compiler can do a lot more optimization than a normal interpreter can do. Interpreter doesn't have the full view of the code. Full view of the code helps to do a lot more optimisation 
  - Some interpreters do some amount of compilation in it (Java JIT compiler)
  - Full view of the code helps in different types of optimisation - 1) Code motion 2) Register Allocation (varible folding) 3) Constant Propogation 4) Dead Code Elimination  
* **Just In Time (JIT) compilers** are between the two and more efficient
  - Also called Run Time Compiler (oxymoron)
  - Module of interpreter marks lines that are executed multiple times. Only this part of the code is compiled once. The interpreter will just run this compiled code.

### Imperative vs Declarative:
- Imperative and procedural are same
- Declerative and functional are the same 
- These are programming styles not languages. 
- You can do both ways in the same program

### Role of Data types in programming languages


### Static vs Dynamic typing
- In static typing the type of a variable is declared in advance
- In dynamic typing the type of a variable is determined by its current value
- Early detection of errors in static typing
- Java, C, C++ are examples of statically typed languages

### Scope vs Lifetime
- If a variable is in scope then it is available for use
- Even if a variable is alive it need not be in scope - A variable's lifetime may have certain points in time when it is not in scope.

### Activation Record
- While invoking a funciton the local variables will be stored in activation record
- return value of the function will be stored in 
- It is like a stack - elements of the stack are activation records - each activation record will have specified fields - 
- bottom of the stack will be main and then on top of it func2 - stack is LIFO - 
- Local variables and parameters are part of the Activation record
- **' Return Link '** of func2 will be given to main. It is a pointer. Points to memory location which stores the return value.
- **' Control Link '** if main is calling func2. func2's control link will point to main ; Control link points to caller's activation record.
- When converting HLL to LLL just before the last step, the memory location is added to the program code (this is the penultimate step)
- If a variable is in activation record then it is in its scope : FALSE. If main is calling func2, the local variable in main is in its activation record but not in scope. 

### Memory
- Heap is free pool of memory given to your program to store your variables. Memory from heap is pushed into stack
- The variables visible to you belong to the top of the stack . These are the ones in scope.
- Memory management is automatic in a stack. When the function ends all the activation records are cleared.
- If there is no base case for a recursion the stack will go on eating the heap and then finally will give a stack overflow error.
- Dynamic / Run time memory allocation happens for Heaps. 
- Any allocation in the Heap is called unnamed memory
- For each allocation in the Heap we keep a handler in the stack that stores the reference.

### Call by value vs call by reference
- Call by reference is pointing to the original memory location

### Explicit memory deallocation vs automatic garbage collection
- Automatic garbage collection is error prone - FALSE
- Memory leakage can happen in explicit memory deallocation - TRUE
- As a programmer, if you do an allocation on the heap it is your responsibility to clear it.
- Garbage collector finds memory that doesn't have a reference and cleares it.

### Interface vs Specification
- Interface : What is visible to other components.
- Specification : Intended input output behaviour.

### Features of OOP
- Abstraction
- Inheritance
- Subtyping
- Dynamic lookup

### Stack , Queue
- Deque is a subtype of stack and queue 
- Stack and queue inherit from deque

- Classes are abstract data types 
- Class has private implementation and public interface

- Java is statically typed
- Python is dynamically typed
