# Undefined Behavior in C due to free() on Stack Memory

This repository demonstrates a common error in C programming: attempting to free memory allocated on the stack using `free()`. This can lead to undefined behavior, making the program unstable and prone to crashes.

The `bug.c` file shows the erroneous code.  The `bugSolution.c` file presents the corrected version.

**Key Concept:**
The `free()` function is used to release memory dynamically allocated using `malloc()`, `calloc()`, or `realloc()`.  It should *never* be used to release memory allocated on the stack (as in the case of local variables). Attempting to do so results in undefined behavior.

**How to reproduce the bug:**
1. Compile `bug.c` using a C compiler (like GCC): `gcc bug.c -o bug`
2. Run the executable: `./bug`
3. Observe the potential crash or unexpected behavior.

**How the solution addresses the issue:**
The `bugSolution.c` file demonstrates how to avoid this error. Local variables are allocated and deallocated automatically by the compiler, eliminating the need for `free()`. The solution demonstrates proper stack management and avoid improper use of `free()` leading to undefined behaviour. 