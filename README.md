# C

Here is everything you need to know on getting started with C.

# Introduction

What is C? C is a programming language designed in the 70's at bell labs by Ken thompson and Dennis Ritchie and was designed as a lower level systems (not low-level language but **lower**) with an easy to use interface that compiles to assembly. It influcened the usage of curly-brace style syntax that many languages to this day have adopted. It's a very powerful language that is still used in the industry for small areas of work such as: compiler design, embedded system development, operating system development and malware.

# Upsides

- C is a very good language for learning about how a computer actually works.
- C has a very clean syntax and is implemented in many applications we use today.
- C is powerful and efficient.

# Downsides

- C can be difficult to build high level applications without enough experience.
- C Lacks of memory safety.
- C has no namespace scopes.
- C has no garbage collection.
- C has a lack of libraries that implement common data structures and algorithms so C requires you to write them by hand.
- C has a lack of generic types other than usage of void pointers and some union magic.
- C lacks function overloading and operator overloading.

And many more. Do not let the downsides scare you away from C, it takes skill to write and C and if you put the time in you can be a great programmer.

# Language basics

### simple hello world program in C
```c
#include <stdio.h>

int main(void) {
    printf("Hello World\n");
}
/* 
    Compilation command should be: gcc input_file_name.c -o output_file_name
    ./output_file_name 
       
    This will compile and then execute the binary that our compiler will emit, in this case our compiler of choice of gcc from the GCC project.
*/
```
So what's exactly going on here? Let's break this down step by step, first up; ``#include <stdio.h>``this statement is simply going to where the C libraries header files are included at, and include the ``stdio.h`` library, the way this will work we'll use what's called a macro to *include* the contents of ``stdio.h`` in our application so we can use functions and variables that were defined in a separate file for us to use that was given to us by the C standard library. Next up, ``int main(void)``, this is a function so let's go ahead and break down the syntax: the first part (in this case the ``int``) defines what *type* of data the function should return, next part of this function is the name of the function, our functions name is ``main`` which is a special function that marks the start of execution in our C program. Next up is the ``(void)``, we in the brackets is where we define our parameter list of things we want to pass to the ``main`` function, here define ``main`` to take ``void`` arguments, or in other words: no arguments. We signify the start of a function with the ``{}`` pairing, next up is the ``printf()`` function call we see here, ``printf`` stands for print function, and it does exactly what the name says it does, it prints data but also allows you to print formatted data, what this means is we can define the format of what we print without actually going and changing the string. We do that using format strings in C, we'll learn about data types first then move to formatting strings with ``printf()``

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
-----

Accessing a variables data is crucial for programming.
Heres an example of printing the data that is stored inside a variable.
```c
// main.c
#include <stdio.h>
#include <stdlib.h>

int main(){
    int x = 1;
    
    // printf() in this scenario takes 2 arguments, the format specifier (the "%i"), and the data that is going to be printed. 
    // "%i" specifies the data that will be printed is an integer and to treat it like an integer.
    // all we have to do from there is declare the variable which will return the data it is set to.
    printf("%i", x);
}
```

-----

Along with variables we have arrays. Arrays contain data that are identified by their index or key.
Arrays act just like a variable but with 1 or more instances of data inside it it.


Arrays need a size so it knows how much memory to reserve, this allows us to access the array and store data in it when necessary.

example of structuring and reserving space for an array.
```c
// main.c

int main(){
    // an array with a size of 10 bytes
    int myarray[10];
}
```

Arrays can store multiple pieces of data such as numbers, characters, and strings.
Heres some examples of storing multiple pieces of data
```c
// main.c

int main(){
    // storing multiple numbers
    int x[] = [1, 2, 3];
    
    // storing a string
    char y[] = "Hello";
}
```

# Header files and how to use them

Header files are crucial in C and allow easy use of the contents inside of it. 
Header files contain C function declerations, global variables, and macros which can be accessed if you import it into a C program. But we should not define code inside of these headers, it's not what they're designed for and can lead to one-definition rule violations. Let's see how to write header files and how NOT to write them.

Here is an example of a header file with a function that prints "Hello".
```c
// hello.h
#include <stdio.h>

void print(void);
```

```c
// hello.c
void print(void) {
    puts("Hello");
}
```

```c
// main.c
#include "hello.h" // When we include external libraries that aren't standard, we have to use ""'s

int main(void) {
    print();
}
```

