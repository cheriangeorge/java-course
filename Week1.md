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
- Even if a variable is alive it need not be in scope

### Activation Record
- While invoking a funciton the local variables will be stored in activation record
- return value of the function will be stored in 
- It is like a stack - elements of the stack are activation records - each activation record will have specified fields - 
- bottom of the stack will be main and then on top of it func2 - stack is LIFO - 
- Local variables and parameters are part of the Activation record
- ' Return Link ' of func2 will be given to main
