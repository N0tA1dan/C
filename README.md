# C

Here is everything you need to know on getting started with C.

# Introduction

C is a procedural programming language which is used for bulding systems, implementing algorithms, game development, and mostly anything you can imagine.

# Upsides

- C is very fast and can be used for virtually anything. 
- C has a very clean syntax and is implemented in many applications we use today
- C is Powerful and efficient



# Downsides

- C can be difficult to build high level applications without enough experience.
- C Lacks of memory safety 
- C Lacks of Object Orientation
- C has no namespace
- C has no Garbage Collection
- C has lack of DSA (Data structures & algorithms) or generics

And many more. Do not let the downsides scare you away from C, it takes skill to write and C and if you put the time in you can be a great programmer

# Language basics

### simple hello world program in C
```c
#include <stdio.h>
#include <stdlib.h>

int main(){
    printf("Hello World");
}
```
**printf()** is a function that outputs a formatted string to stdout(standard output aka your display). An alternative would be the **puts()** function which does pratically the same thing.

# Header files and how to use them

Header files are crucial in C and allow easy use of the contents inside of it. 
Header files contain C function declerations, global variables, and macros which can be accessed if you import it into a C program.


examples of a header file
```c
// myheader.h
int printhello(){
    printf("Hello");
}
```

how to include a header file and how to use functions declared in it?
```c
// main.c
#include "filename.h"

int main(){
    headerfilefunction();
}
```

When you include a header file in C you can now access its variables and functions inside of it because it is added to the code by the compiler

# Data types

Like any programming language, C has data types and we need them so we can identify what data is what.

**Integer Types**
- char
- unsigned char
- signed char
- int
- unsigned int
- short
- unsigned short
- long 
- unsigned long

**Floating-Point Types**
- float
- double
- long double

# Variables and Arrays

Variables in C store information, such as numbers and chars. We use data types to specify what kind of data a variable contains.

Here are some examples of variables in C
```c
// main.c

int main(){
    // to store a number
    int x = 1;
    // to store a character
    char y = 'A';
}
```
Along with variables we have arrays. Arrays contain data that are identified by their index or key.
Arrays act just like a variable but with 1 or more instances of data inside it it.


Arrays need a size so it knows how much memory to reserve.

example of structuring and reserving space for an array
```c
// main.c

int main(){
    // an array with a size of 10 bytes
    int myarray[10];
}
```

Using an array to store strings.

- Experience
  - Upsides
  - Downsides

- Language basics
  - Printing
  - Importing
  - Variables
  - Loops
  - Structs
  - Functions
  - Etc..

- Modules
  - Networking (net/http, net, etc.)
