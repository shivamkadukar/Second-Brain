- compiler - convert high level language to low level language.

- When compiler runs on same machine and produces machine code for the same machine on which it is running. Then it is called as self compiler or _resident compiler_. 

- Compiler may run on one machine and produces the machine codes for other computer then in that case it is called as _cross compiler_.

- _Source-to-source Compiler_ or transcompiler or transpiler is a compiler that translates source code written in one programming language into the source code of another programming language.


high level language - stream of characters

## Stages of Compiler Design
- [[Lexical Analysis]] also know as _Scanning_ - 
	- input --> stream of characters, output --> stream of tokens
	- reads code character by character and breaks it down to token(keywords, identifiers, operators).
	
- [[Syntax Analysis]] also known as _parsing_ - 
	- checks syntax of the code to confirm it follows the rule of the programming language.
	- builds a parse tree(heirarchical representation of the prgram;s structure), uses to check for syntax error.
	- output is usually Abstract syntax tree(AST)

- [[Semantic Analysis]] - 
	- performs type checking to ensure variables are used correctly and operations are on compatible data types.
	- checks for other semantic errors, including undeclared variables and incorrect function calls.

- [[Code Generation]] - 
	- translates the parse tree into machine code that can be executed by the computer.
	
- [[Code Optimization]] - 
	- Analyzes the generated code to make performance optimizations.
	- Optimizations may include constant folding, loop unrolling, and function inlining.

- Intermediate code generation - Converts parse tree to 3 address code.


Till this point the phases are same irrespective of the operating system. after this the phases depends on the operating system.
- Code optimization - 
- Target Code Generation -

### Language Processing Systems - 
![[Pasted image 20240609111501.png|150]]
- **High-Level Language and Pre-Processor:** High-level languages with pre-processor directives (e.g., #include, #define) are more human-readable. The pre-processor handles file inclusion and macro expansion before actual compilation.
    
- **Assembly Language and Assembler:** Assembly language is an intermediate code between high-level and binary. The assembler, specific to each platform, converts assembly code to machine code, producing an object file.
    
- **Interpreter vs. Compiler:** An interpreter converts high-level code to machine code line by line, while a compiler processes the entire program at once. Interpreted programs are typically slower than compiled ones.
    
- **Relocatable Machine Code and Loader/Linker:** Relocatable machine code can be loaded and run from any memory address. The linker combines object files into an executable, and the loader places it in memory and executes it, resolving the final addresses.

### Types of Compiler - 
- **Single Pass Compiler:** Converts source code to machine code in a single pass through all compiler phases within one module.
    
- **Two Pass Compiler:** Translates the program twice, first by the front end and then by the back end.
    
- **Multipass Compiler:** Creates several intermediate codes and processes the syntax tree multiple times, breaking the code into smaller programs.

### Phases of Compiler - 
![[Pasted image 20240609112651.png|500]]
[[Lexical Analysis]]
[[Syntax Analysis]]
[[Semantic Analysis]]
[[Intermediate COde Generation]]
[[Optimization]]
[[Code Generation]]
