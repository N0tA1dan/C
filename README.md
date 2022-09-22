# C

Here is everything you need to know on getting started with C.

# Introduction

What is C? C is a statically-typed procedural programming language designed in the 1970's at bell labs by Ken thompson and Dennis Ritchie and was designed as a lower level systems programming language (not low-level language but **lower**) with an easy to use interface that compiles to assembly. It's syntax influenced the usage of curly-brace style code that many languages to this day have adopted. It's a very powerful language that is still used in the industry for small areas of work such as: compiler design, embedded system development, operating system development, malware and more.

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
    Compilation command should look like such: 
    gcc input_file_name.c -o output_file_name
    ./output_file_name 
       
    This will compile and then execute the binary that our compiler will emit, in this case our compiler of choice of gcc from the GCC project.
*/
```
So what's exactly going on here? Let's break this down step by step, first up; ``#include <stdio.h>``this statement is simply going to where the C standard libraries header files are located at, and includes the ``stdio.h`` library defined in this path, the way this would work is we'd use what's called a macro to *include* the contents of ``stdio.h`` in our application so we can use functions and variables that were defined in a separate file for us to use which was given to us by the C standard library. The C standard library is a library of C code that gives us interfaces to regular programming concepts without us having to write them ourselves. Next up, ``int main(void)``, this is a function so let's go ahead and break down the syntax: the first part (in this case the ``int``) defines what *type* of data the function should return, next part of this function is the name of the function, our functions name is ``main`` which is a special function that marks the start of execution in our C program. Next up is the ``(void)``, the brackets is where we define our parameter list of things we want to pass to the ``main`` function, here we defnine ``main`` to take ``void`` arguments, or in other words: no arguments. We signify the start of a function with the ``{}`` pairing, next up is the ``printf()`` function call we see here, ``printf`` stands for print function, and it does exactly what the name says it does, it prints data but also allows you to print formatted data, what this means is we can define the format of what we print without actually going and changing the string we pass to the function. We do that by using format strings in C, we'll learn about data types first then move to formatting strings with ``printf()``

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

These are a list of C's primitive types (types defined by the language), each of these vary in different types of data and the amount of data they can hold (aka their size in bytes in memory)

# Comments and how to use them and when
Comments are a common concept implemented in basically every language and they're designed to have these segments of text that the compiler won't actually read, they're skipped over. So this allows us to document our code for ourselves and other people which make things easier to read and understand. C has 2 main ways of representing commentation of code, that being the single line comment (//) the multi-line comment (/* */).

```c
#include <stdio.h>

// This is a single line comment, this will be altered out in the compiled code.
int main(void) {
    /*
        This is a multi-line comment that can
        be put on many lines to comment properly.
    */
    printf("Hello world!\n");
}
```

# Variables

Let's put these data types to use with the usage of variables in C. Assuming you've taken 6th grade math, you should know what a variable is; a variable is simply a way of referencing some kind of data with a name to it, but the question is how do we define what *kind* or *type* of data we want to store with a name? The answer is with the usage of data types, let's write some examples to further showcase this:

```c
// main.c

int main(void) {
    // to store a number
    int x = 1;
    
    // to store a character
    char y = 'A';

    // to store a float
    float z = 10.00;
}
```
-----

Accessing a variables data is crucial for programming.
Heres an example of printing the data that is stored inside a variable.
```c
// main.c
#include <stdio.h>
#include <stdlib.h>

int main(void) {
    int x = 1;
    
    // printf() in this scenario takes 2 arguments, the format specifier (the "%d"), and the data that is going to be printed. 
    // "%d" specifies the data that will be printed is an integer and to treat it like an integer.
    // all we have to do from there is declare the variable which will return the data it is set to.
    printf("%d\n", x);
}
```
# Format specificers for printf and similar functions
// You do this

# Arrays
As an introduction to arrays I want to start by asking a question: Let's say we wanted to store 3 ages of different people, how could we do this? We could have 3 different variables for those ages but that's not very nice to look at especially when you're dealing with more than 3 elements, so we can use arrays as a way of doing this in a more elegant way. An array is a data structure that holds elements of the same type that are addressed by an identifier / name unit. We define that we want an array in C using the ``[]`` syntax notation. So let's jump into the sytax of what an array looks like in C:
```
data-type name[] = {elements};
```
let's write the code for the example that was given in the preface to this section:
```c
#include <stdio.h>

int main(void) {
    int ages_of_people[3] = {18, 21, 35}; // We notate how to say this like so: We have an array of integers with the name "ages_of_people" 
}
```
So how do we access this data? Well there's a system put in-place in every non-weird programming language that allows us to access data of an array using these things called indexes. Indexes are these numbers that represent the placement of data in the array, the index of the first element in normal languages is 0 but not in every other language (looking at you lua -_-). Let's see what that looks like in C:

```c
#include <stdio.h>

int main(void) {
    int ages_of_people[3] = {18, 21, 35};
    // Side note: We can sort of space out large printf() calls instead of making several printf() calls by just adding a newline with every comma.
    printf("%d %d %d\n", 
        ages_of_people[0],  // ages_of_people[0] = 18;
        ages_of_people[1],  // ages_of_people[1] = 21;
        ages_of_people[2]); // ages_of_people[2] = 35;
}
```

I think this code looks pretty bad, there's a way we can condense this into a little bit more of an elegant way to print all of the elements of the array, with 3 elements it's not that bad but just imagine with hundreds maybe even thousands of elements, it can get rough. We can use for-loops to make this look nicer. 

You can also use arrays to store a string. A string in C is a combonation of multiple bytes/chars in an array. Strings are very useful for text/character storage.

An example of how a string would be formatted

```c
// main.c

int main(){
    char myString[] = "Hello";
}
```



# Conditional statements and loops (aka branching)
// You also do this, for the for-loops make sure to continue with the age example I've defined above.

# Macros
What is a **Macro**? A macro is a statement that tells the preprocessor to replace the statement with the macro's value. Macros helps set a variable to a constant value that you can still access in the program.

The structure of a macro is a `#` followed by the statement. 
heres how the structure looks

```
#macro variableName value
```

Examples of a macro

```c
#include <stdio.h>

// this is our macro, this sets the value of x to the integer 1.
#define x 1

int main(void){
    printf("%d", x);
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
#include "hello.h"

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
Compiling multiple files into a single executable is not much different than a single file. Compiling that code should look like this:
```
gcc hello.c main.c -o main
./main
```
so we declared a function inside of a header, then defined it in a source file that relates to that header file, we'd actually have an issue with this code if we defined code inside of the header which you shouldn't do. We can write safe header files with the use of header guards. We'll go over those later when we actually start writing code with them.
