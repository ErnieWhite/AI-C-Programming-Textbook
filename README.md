# AI-C-Programming-Textbook
Below is a college-level, instructor-ready C programming curriculum designed as a 15-week, 4-credit course. It assumes little or no prior C experience but prgresses into pointers, dynamic memory, data structures, file processing, debugging, modular design, and a substantial capstone.

The course is deliberately mastery- and project-oriented: students repeatedly build, debug, test and extend real C programs instead of learning syntax in isolation. The sequence aligns with Beej's Guide to C Programming, which progresses from compilation and control flow through pointers, arrays, string, structures, fileI/O, pointer arithmietic, and manual memory allocation.

# CS 231: Programming in C
Credits: 4
Duration: 15 weeks
Lecture 3 hours/week
Laboratory: 2 hours/week
Expected independent work: 5-7 hours/week
Language: ISO C17, with selected C23 features discussed
Primary compiler: GCC or Clang
Development environment: VS Code, Vim/Neovim, or another test editor plus terminal
Build tools: GCC/Clang, Make
Debugging: GDB, AdressSanitizer, compilor diagnostics
Version control: Git

---
# 1. Course Description

This course develops profieciency in the C programming language while introducing the systems-level concepts that destinguish C from higher-level languages.

Student learn to design, implement, compile, test, debug, and document C programs while developing a concrete understanding of:
 - variables and primitive types
 - expressions and operators
 - control flow
 - functions and decomposition
 - arrays and strings
 - pointers
 - memory representation
 - structures and enumerations
 - file processing
 - dynamic memory allocation
 - pointer arithmetic
 - linked data structures
 - header files and separate compilation
 - debugging and defensive programming
 - bitwise operations
 - command-line programs
 - reusable libraries
 
 A central theme is:
 
    What is actually happening in memory when this C program executes?
By the end of the semester, studets should be able to move beyond small coding exercises and construct a multi-file C application containing dynamic data structures, persistent storage, error handling, automated tests, and documented interfaces.

---
# 2. Prerequisites
## Required
Students should have:
- basic computer literacy
- comfort navigating files and directories
- basic algebra
- logical problem-solving ability

Previous prgramming experience is helpful but not mandatory.

## Recommended
Students benefit from prior exposure to :
- variables
- boolean logic
- loops
- functions
- command-line environments

Students coming from Python, JavaScript, VBA, or similar languages are appropriate candidates.
## Week 0 technical preparation
Before Week 1, students install:
```text
GCC or Clang
Git
GDB
Text editor / IDE
Terminal environment
```
Student must successfully execute:
```text
gcc --version
git --version
gdb --version
```
and compile:
```C
# include <stdio.h>

int main(void)
{
    printf("Hello, C!\n");
    return 0;
}
```
Beej's Guide to C Prgramming specifically covers building programs with both GCC and Clang, making it suitable as a prmary companion text.

----
# 3. Leaning Outcomes
Upon successful completion, students will be able to:

## LO1: Write correct C Programs
Use C syntax, expressions, operators, conditionals, loops, functions, arrays, pointers, structures, and standard-library facilities.

## LO2: Understand memory
Explain the relationships among:
- variables
- addresses
- pointers
- arrays
- stack objects
- dynamically allocated objects

## LO3: Decompose programs
Break larger problems into cohesive functions an dmodules.

## LO4: Manage memory safely
Use:
```C
malloc()
calloc()
realloc()
free()
```
while recognizing:
- leaks
- dangling pointers
- double frees
- invalid reads/writes
- buffer overruns

## LO5: Work with aggregate data
Create and manipulate:
```C
struct
enum
union
typedef
```

# LO6: Process external data
Read and write:
- text files
- CSV-like records
- binary data
- command-line arguments

# LO7: Implement fundamental data structures
Implement at least:
- dynamic arrays
- linked lists
- stacks and queues

# LO8: Debug systematically
Use:
- compiler warnings
- assertions
- GDB
- sanitizers
- unit tests
- controlled experiments

# LO9: Construct multi-file programms
Use:
- .c source files
- .h headers
- include guards
- separate compilation
- Makefiles

# LO10: Analyze program correctness
Reason about:
- preconditions
- postconditions
- edge cases
- memory ownership
- undefined behavior

# LO11: practice professional development
Use Git, documentation, coding standards, tests, and reproducable builds.

# LO12: Devalop a complete C application
Desing and implement a substantial progrma of roughly 1,000-2,000 lines of student-authored C.

---

# 4. Module Breakdown

| Module  | Weeks | Subject |
|---|---|---|
| I | 1-2 | Foundations of C |
| II | 3 | Functions and Program Decomposition |
| III | 4 | Arrays and Strings |
| IV | 5-6 | Pointers and Memory |
| V | 7 | Structures and Data Modeling |
| VI | 8 | Review and Midterm |
| VII | 9 | Files and Command-Line Programs |
| VIII | 10 | Dynamic Memory |
| IX | 11 | Modular Programming |
| X | 12 | Dynamic Data Structures |
| XI | 13 | Bitwise and Systems-Oriented C |
| XII | 14 | Defensive C and Debugging |
| XIII | 15 | Capstone Integration |

The progression intentionall places arrays before deeper pointer arithmetic and malloc(). Students first need a concrete model of contiguous storage before reasoning about dynamically allocated memory.

---
# 5. Weekly Lesson Plan

# Week1: C and the Compilation Model

## Lesson 1.1: What is C?

### Student learns
- history and purpose of C
- compiles versus interpreted languages
- source files and executables
- role of the C standard
- portabliltiy
- C17/C23 terminology

### Why it matters
C exposes concepts that Python and many higher-level languages deliberatley hide. Students need to understand that they are reponsible for details such as object representation, resource management, and valid memory access.

### Prerequisites
None.

Practice
1. Locatate C in operating systems, databases, embedded software, and language runtimes.
2. Compare a tiny Python program with its C equivalent.
3. Identify responsiblities handed automatically by Python but explicitly by C.

### Additional reading
Beej's Guide to C Programming, "What to Expect from C."

---

## Lesson 1.2: Compile, Link, Execute

### Student learns

The basic pipeline:
```text
source code
    ↓
preprocessor
    ↓
compiler
    ↓
object code
    ↓
linker
    ↓
executable
```
Commands:
```shell
gcc hello.c -o hello
```
and preferably:
```shell
gcc -std=c17 -Wall -Wextra -Wpedantic hello.c -o hello
```
### Why it matters
Many later C problems are not runtime errors at all. Students must distinguish:
- syntax/compiler errors
- linker errors
- runtime errors
- logical errors

### Prerequisites
- files and directories
- terminal basics

### Practice
Create intentional:
1. syntax error
2. unresolved symbol/linker error
3. incorrect output
4. runtime failure

Students classify each.

### Reading
Beej's Guide to C Programming, compilation, GCC, and CLang sections.

### Lab 1

Build a command-line unit converter.

Convert:
- Farenheit/Celsius
- inches/centimeters
- pounds/kilograms

---


