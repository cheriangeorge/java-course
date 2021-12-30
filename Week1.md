### Compiler vs Interpreter:
- Compiler needs entire program to be loaded in RAM while interpreter loads just one line into buffer
- Compiler is faster than interpreter 
- Memory requirement for interpreter is very low (Usually used in memory constrained devices)
- Explore : Which runs faster - Compiled code or interpreted code ? 
- JIT compilers are between the two and more efficient

### Imperative vs Declarative:


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


