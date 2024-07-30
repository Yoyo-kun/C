# C Language Introduction Tutorial

This content is adapted from Mr. [Ruan Yifeng(阮一峰)](https://wangdoc.com/clang/)'s C Language Introduction Tutorial.

GitHub Address: https://github.com/wangdoc/clang-tutorial

Online Reading Address: https://wangdoc.com/clang/intro

***

# 1. Introduction to C Language

## History

The C language was originally invented as a development tool for the Unix system.

In 1969, Ken Thompson and Dennis Ritchie at Bell Labs in the United States developed the Unix operating system. Unix was written in assembly language and could not be ported to other computers, so they decided to rewrite it in a high-level language. However, the high-level languages at that time could not meet their requirements, so Thompson invented the B language based on the BCPL language.

In 1972, Dennis Ritchie and Brian Kernighan redesigned a new language while developing the UNIX operating system, based on the B language, which replaced the B language and was therefore called the C language.

In 1973, the entire Unix system was rewritten in C. After that, this language spread rapidly and was widely used for developing various operating systems and system software.

In 1988, the American National Standards Institute (ANSI) formally standardized the C language, marking the beginning of its stability and standardization.

Decades later, C remains one of the most widely used and popular system programming languages. Unix and Linux systems are still developed using C.

## Features of C Language

The main reasons C language has remained popular and widely used are its distinctive features.

#### (1) Low-Level Language

C language can directly operate hardware, manage memory, and interact with the operating system, making it a very low-level language. It is particularly suitable for writing programs that need to interact with hardware and have very high performance requirements.

#### (2) Portability

The original design purpose of C language was to port the Unix system to other computer architectures. This made it highly portable from the beginning, and C programs can be relatively easily ported to various hardware architectures and operating systems.

Besides computers, C is now also the preferred programming language for embedded systems, and the underlying systems of devices such as cars, cameras, and household appliances are programmed in C, thanks to its good portability.

#### (3) Simplicity

C language syntax is relatively simple, with not too many syntax rules and almost no syntactic sugar. Generally speaking, if two syntax forms can accomplish nearly the same task, C language will only provide one, greatly reducing the complexity of the language.

Top-down planning, structured programming, and modular design concepts make code more readable and reliable.

Moreover, C language syntax is fundamental, not providing advanced data structures. For example, C does not have "classes"; complex data structures must be constructed by the programmer.

#### (4) Flexibility

C language imposes very few restrictions on programmers. It assumes that programmers know what they are doing and does not prevent you from performing dangerous operations; you can do anything, and the consequences are your responsibility.

C's philosophy is "trust the programmer, don't hinder them from doing things." For example, it lets programmers manage memory themselves and does not provide automatic memory cleanup. It also does not provide protection measures like type checking, array bounds checking, or pointer position checking.

On the surface, this may seem dangerous, but it gives advanced programmers greater programming freedom. However, this also makes debugging C language more difficult.

#### (5) Summary

These features allow C language to write programs that are highly efficient and fully exploit hardware capabilities, and C compilers are relatively easy to implement. On the other hand, C code is prone to errors, and it is generally not easy for average programmers to write well.

Moreover, many modern popular languages are based on C, such as C++, Java, C#, JavaScript, etc. Learning C well can help deepen understanding of these languages.

## Versions of the C Language

Historically, the C language has had multiple versions.

#### (1) K&R C

"K&R C" refers to the original version of the C language. In 1978, C language inventors Dennis Ritchie and Brian Kernighan co-authored the famous textbook "The C Programming Language." Since there was no written syntax standard for C, this book became the de facto standard, named after the initials of the authors' last names, "K&R C."

#### (2) ANSI C (also known as C89 or C90)

The original version of C was very simple and vague in many areas, and the syntax was still rapidly evolving, leading to calls for standardization. In 1989, the American National Standards Institute (ANSI) established a standard for the C language. In 1990, the International Organization for Standardization (ISO) adopted this standard. It is known as "ANSI C" and can also be referred to by the year of publication, "C89 or C90."

#### (3) C95

In 1995, ANSI made a supplement to the 1989 standard, adding support for multibyte and wide characters. This version is known as C95.

#### (4) C99

The first major revision of the C standard occurred in 1999, adding many language features such as the double-slash (`//`) comment syntax. This version is called C99 and is currently the most popular version of C.

#### (5) C11

In 2011, the standardization organization again revised the C language, adding support for Unicode and multithreading. This version is known as C11.

#### (6) C17

The C11 standard was patched in 2017, but the release was in 2018. The new version only addressed some of the deficiencies in C11 without introducing any new features. This version is called C17.

#### (7) C2x

The standardization organization is discussing the next version of the C language, which is expected to be approved in 2023 and will be called C23.

## Compilation of C Language

<img src="https://s2.loli.net/2024/07/13/Z9nyUvtsm82jEOa.png" alt="image-20240713195934877" style="zoom:50%;" />

The compiler converts source code into intermediate code; the linker merges the intermediate code with other code to create an executable file; the startup code acts as an interface between the program and the operating system.

C is a compiled language, meaning that the source code, which is in the form of text files, cannot be executed directly. It must be compiled into a binary executable file by a compiler. The process of translating code from text to binary instructions is called the compilation phase, or "compile time," which is distinct from the runtime phase.

Currently, the most common C language compiler is the GCC compiler provided by the Free Software Foundation, which is available for free. This book also uses this compiler. GCC can be installed directly on Linux and Mac systems, while Windows systems can install MinGW. However, it is also possible to use online compilers, which can simulate running C code on a web page and display the results. Here are two such tools:

-   CodingGround: https://tutorialspoint.com/compile_c_online.php
-   OnlineGDB: https://onlinegdb.com/online_c_compiler

The examples in this book are compiled using GCC in the command line.

## Hello World Example

C language source code files typically have the `.c` extension. Below is a simple C program called `hello.c`. It is just an ordinary text file that can be written with any text editor.

```c
#include <stdio.h>

int main(void) 
{
  printf("Hello World\n");
  return 0;
}
```

The only function of this program is to display "Hello World" on the screen.

Here, we won't explain what this code means; it's just an example to show how to compile and run C code. Assuming you have GCC installed, you can open the command line and run the following command.

```c
$ gcc hello.c
```

This command uses the `gcc` compiler to compile the source file `hello.c` into binary code. Note that `$` is the command line prompt, and you only need to type the part after `$`.

After running this command, a compiled output file named `a.out` (short for assembler output; on Windows, it would be `a.exe`) is generated in the current directory by default. Executing this file will display `Hello World` on the screen.

```c
$ ./a.out
Hello World
```

The `-o` option of GCC (short for output) can specify the filename of the compiled output.

```c
$ gcc -o hello hello.c
```

The command above, with `-o hello`, specifies that the output file should be named `hello` (replacing the default `a.out`). This will create an executable file named `hello`. Running this file will produce the same result.

```c
$ ./hello
Hello World
```

The `-std=` option of GCC (short for standard) can specify which C language standard to use for compilation.

```c
$ gcc -std=c99 hello.c
```

The command above specifies compiling according to the C99 standard.

Note that the `-std` option requires an `=` to connect the parameter, unlike the space used with `-o`. Also, there should be no extra spaces before or after the `=`.

# 2. Basic Syntax of C Language

## Statements

C language code consists of lines of statements. A statement is an operation command executed by the program. C language requires that statements must end with a semicolon, unless explicitly specified otherwise.

```c
int x = 1;
```

The above is a variable declaration statement, declaring an integer variable `x` and setting its value to `1`.

Multiple statements can be written on one line.

```c
int x; x = 1;
```

The above example shows two statements written on one line. Therefore, line breaks between statements are not necessary; they are just for code readability.

A single statement can also be written across multiple lines; in this case, the semicolon determines where the statement ends.

```c
int x;
x
=
1
;
```

In the example above, the second statement `x = 1;` is split into four lines. The compiler will automatically ignore line breaks within the code.

A single semicolon is also a valid statement, known as an "empty statement," although it does nothing.

```c
;
```

## Expressions

Various calculations in C language are mainly performed through expressions. An expression is a computation used to obtain a value.

```c
1 + 2
```

The above code is an expression used to get the result of the arithmetic calculation `1 + 2`.

An expression followed by a semicolon can also become a statement, but it has no practical effect.

```c
8;
3 + 4;
```

The above example shows two expressions, which become statements when followed by semicolons.

The main differences between expressions and statements are:

- Statements can contain expressions, but expressions themselves do not constitute statements.
- Expressions always have return values, whereas statements do not necessarily have return values. This is because statements are used to execute a command, and often do not need a return value. For example, a variable declaration statement (`int x = 1`) has no return value.

## Statement Blocks

C language allows multiple statements to be grouped within a pair of curly braces `{}`, forming a block, also known as a compound statement. In syntax, a statement block can be regarded as a composite statement consisting of multiple statements.

```c
{
  int x;
  x = 1;
}
```

In the example above, the curly braces form a statement block.

No semicolon is needed at the end of the curly braces.

## Whitespace

In C language, whitespace is mainly used to help the compiler distinguish syntax units. If syntax units can be distinguished without whitespace, it is not mandatory; it is just for readability.

```c
int x = 1;
// Equivalent to
int x=1;
```

In the above example, whether there is whitespace before and after the assignment operator (`=`) does not matter because the compiler can distinguish syntax units without it.

Multiple spaces between syntax units are equivalent to a single space.

```c
int    x =     1;
```

In the above example, multiple spaces between syntax units have the same effect as a single space.

Whitespace is also used for indentation. Whether code has indentation or not does not affect the compiler; non-indented code can also run perfectly. Indentation is emphasized only to enhance code readability and distinguish code blocks.

Most C language styles require that the next level of code is indented by 4 spaces. For compactness, this book uses 2 spaces for indentation.

```c
// Indent four spaces
if (x > 0)
    printf("positive\n");

// Indent two spaces
if (x > 0)
  printf("positive\n");
```

Lines containing only whitespace are called blank lines, and the compiler will completely ignore them.

## Comments

Comments are explanations of code that the compiler ignores, meaning comments do not affect the actual code.

There are two ways to write comments in C language. The first method is placing comments between `/*...*/`, which can span multiple lines.

```c
/* Comment */

/*
  This is a comment line
*/
```

Such comments can be inserted inline.

```c
int open(char* s /* file name */, int mode);
```

In the above example, `/* file name */` is used to explain a function parameter, and the code following it will still execute correctly.

This type of comment must not forget to include the closing symbol `*/`, otherwise, it can lead to errors.

```c
printf("a "); /* Comment one
printf("b ");
printf("c "); /* Comment two */
printf("d ");
```

In the above example, the intention is to have two comments at the end of the first and third lines of code. However, forgetting to include the end symbol for the first comment causes Comment one to extend to the end of the third line.

The second method is placing comments after double slashes `//`, from the double slashes to the end of the line. This type of comment can only be a single line, either at the beginning of a line or at the end of a line of code. This syntax was introduced in the C99 standard.

```c
// This is a comment

int x = 1; // This is also a comment
```

Regardless of the type of comment, it cannot be placed inside double quotes. Comment symbols inside double quotes will be treated as part of the string, interpreted as normal symbols, losing their comment function.

```c
printf("// hello /* world */ ");
```

In the above example, comment symbols inside double quotes are treated as ordinary characters and have no commenting effect.

During compilation, comments are replaced with a space, so `min/* space */Value` becomes `min Value`, not `minValue`.

## printf()

#### Basic Usage

The `printf()` function is used extensively in examples in this book, so here is a brief introduction to this function.

`printf()` outputs parameter text to the screen. The `f` in its name stands for `format`, indicating that you can customize the format of the output text.

```c
printf("Hello World");
```

The above command will output "Hello World" on the screen.

`printf()` does not automatically add a newline character at the end of the line; after execution, the cursor remains at the end of the output. To move the cursor to the beginning of the next line, you can add a newline character `\n` at the end of the output text.

```c
printf("Hello World\n");
```

If there are newlines inside the text, they are also inserted using newline characters.

```c
printf("Hello\nWorld\n");
```

The above example first outputs `Hello`, then a newline, then outputs `World` at the beginning of the next line, followed by another newline.

The above example can also be written as two `printf()` calls with the same effect.

```c
printf("Hello\n");
printf("World\n");
```

`printf()` is defined in the standard library header file `stdio.h`. Before using this function, you must include this header file at the beginning of the source file.

```c
#include <stdio.h>

int main(void) {
  printf("Hello World\n");
}
```

In the above example, `#include <stdio.h>` must be added at the beginning of the source file to use the `printf()` function. For a detailed explanation of the `#include` directive, refer to the chapter on "Preprocessor".

#### Placeholders

`printf()` allows you to specify placeholders in the output text. A "placeholder" means this position can be replaced by another value.

```c
// Outputs: There are 3 apples
printf("There are %i apples\n", 3);
```

In the above example, `There are %i apples\n` is the output text, where `%i` is the placeholder indicating that this position will be replaced with another value. The first character of a placeholder is always a percent sign `%`, and the second character indicates the type of the placeholder. `%i` signifies that the value to replace it must be an integer.

The second parameter of `printf()` is the value that replaces the placeholder, which in this example is the integer `3`. The output is `There are 3 apples`.

Common placeholders include `%i` for integers and `%s` for strings.

```c
printf("%s will come tonight\n", "Jane");
```

In this example, `%s` indicates that a string will replace this placeholder, so `printf()`'s second parameter must be a string, which is `Jane` in this case. The output is `Jane will come tonight`.

You can use multiple placeholders in the output text.

```c
printf("%s says it is %i o'clock\n", "Ben", 21);
```

In this example, the output text `%s says it is %i o'clock` contains two placeholders: the first is a string placeholder `%s`, and the second is an integer placeholder `%i`, corresponding to the second parameter (`Ben`) and the third parameter (`21`). The output is `Ben says it is 21 o'clock`.

The parameters of `printf()` correspond one-to-one with the placeholders. If there are `n` placeholders, `printf()` should have `n + 1` parameters. If the number of parameters is less than the corresponding placeholders, `printf()` may output arbitrary values from memory.

Here are common placeholders, categorized by type, for quick reference. Details will be provided in later chapters.

- **Octal** ---- `o`
  - `%o`: Octal integer.
  - `%ho`: Octal `short int`.
  - `%lo`: Octal `long int`.
  - `%llo`: Octal `long long int`.

- **Decimal** ---- `d/i-f`
  - `%d`: Decimal integer.
  - `%i`: Integer, basically the same as `%d`.
  - `%u`: Unsigned integer (`unsigned int`).
  - `%hd`: Decimal `short int`.
  - `%hu`: Decimal `unsigned short int`.
  - `%ld`: Decimal `long int`.
  - `%lu`: Decimal `unsigned long int`.
  - `%lld`: Decimal `long long int`.
  - `%llu`: Decimal `unsigned long long int`.
  - `%f`: Floating-point number (includes `float` and `double`).
  - `%Lf`: `long double` type floating-point number.
  - `%Le`: `long double` in scientific notation.
  - `%e`: Floating-point number in scientific notation, with `e` in lowercase.
  - `%E`: Floating-point number in scientific notation, with `E` in uppercase.
  - `%g`: Floating-point number with 6 significant digits. If the integer part exceeds 6 digits, it will be automatically converted to scientific notation, with `e` in lowercase.
  - `%G`: Same as `%g`, but `E` is uppercase.

- **Hexadecimal** ---- `x-a`
  - `%x`: Hexadecimal integer.
  - `%hx`: Hexadecimal `short int`.
  - `%lx`: Hexadecimal `long int`.
  - `%llx`: Hexadecimal `long long int`.
  - `%a`: Hexadecimal floating-point number, with letters in lowercase.
  - `%A`: Hexadecimal floating-point number, with letters in uppercase.

- **Character** ---- `c`
  - `%c`: Character.

- **String** ---- `s`
  - `%s`: String.

- **Pointer** ---- `p`
  - `%p`: Pointer.

- **Size_t** ---- `zd`
  - `%zd`: `size_t` type.
  - **`%zu`**: For outputting unsigned `size_t` values.
  - **`%zd`**: For outputting signed `size_t` values (less commonly used).
  - **If the system does not support these two, use:**
    - **`%u`**: If `size_t` is defined as `unsigned int`.
    - **`%lu`**: If `size_t` is defined as `unsigned long`.

- **Percent** ---- `%`
  - `%%`: Outputs a percent sign.

- **Number** ---- `n`
  - `%n`: The number of characters written so far. This placeholder does not output anything but stores the value in the memory pointed to by the corresponding variable pointer.

```c
int main(void)
{
  int i = 0;
  printf("Hello %nworld\n", &i);
  printf("%d", i);

  return 0;
}
```

#### Output Formatting

`printf()` allows customizing the output format of placeholders.

##### (1) Specifying Width

`printf()` allows specifying the minimum width of a placeholder.

```c
printf("%5d\n", 123); // Outputs "  123"
```

In the above example, `%5d` means the placeholder should have a minimum width of 5 characters. If the value is less than 5 characters, spaces will be added in front.

By default, the output is right-aligned, meaning spaces are added before the output. To left-align the output, add a minus sign `-` after the `%`.

```c
printf("%-5d\n", 123); // Outputs "123  "
```

In this example, the output `123` is followed by spaces.

For floating-point numbers, this width specifier limits the minimum width for all digits.

```c
// Outputs "  123.450000"
printf("%12f\n", 123.45);
```

In this example, `%12f` means the floating-point number should take up at least 12 characters. Since the default precision is 6 decimal places, the result will have 2 leading spaces.

##### (2) Always Display Sign

By default, `printf()` does not display a `+` for positive numbers, only a `-` for negative numbers. To display a `+` for positive numbers as well, add a `+` after `%`.

```c
printf("%+d\n", 12); // Outputs +12
printf("%+d\n", -12); // Outputs -12
```

Here, `%+d` ensures that the output always has a sign.

##### (3) Specifying Decimal Places

When outputting floating-point numbers, you might want to specify the number of decimal places. For example, to keep two decimal places, use `%.2f`.

```c
// Outputs: Number is 0.50
printf("Number is %.2f\n", 0.5);
```

In this example, if you want 3 decimal places (`0.500`), use `%.3f`.

This format specifier can be combined with width specifiers.

```c
// Outputs "  0.50"
printf("%6.2f\n", 0.5);
```

In this example, `%6.2f` specifies that the output should be at least 6 characters wide with 2 decimal places. Thus, the result has 2 leading spaces.

Both width and decimal places can be specified using `*`, with values passed as additional `printf()` parameters.

```c
printf("%*.*f\n", 6, 2, 0.5);

// Equivalent to
printf("%6.2f\n", 0.5);
```

In this example, `%*.*f` uses `6` and `2` as parameters for width and decimal places.

##### (4) Output Partial String

The `%s` placeholder outputs the entire string by default. To output only a portion, use `%.[m]s` to specify the length, where `[m]` is a number indicating the length.

```c
// Outputs: hello
printf("%.5s\n", "hello world");
```

In this example, `%.5s` means only the first 5 characters of "hello world" are output, which results in "hello".

## Standard Library and Header Files

Programs often need functionality that may not need to be written from scratch, as C provides many built-in functions. For example, the `printf()` function is built into C, allowing you to display output on the screen without having to write your own code for this purpose.

All these built-in functions in C are collectively known as the "standard library." The standard library is defined by standards, which specify what functionality is included and how it should be used, ensuring code is consistent and portable.

Different functionalities are defined in different files, which are collectively known as "header files." If a system provides a particular function, it will also include a header file that describes this function. For instance, the header file for the `printf()` function is `stdio.h`, which is provided by the system. Header files typically have the `.h` extension.

To use a particular function, you must first include its corresponding header file using the `#include` directive. This is why you need to include `stdio.h` before using `printf()`.

```c
#include <stdio.h>
```

Note that the `#include` directive for loading header files does not require a semicolon at the end, as detailed in the chapter on "Preprocessor."

# 3. Variables

A variable can be understood as a named block of memory. Through the variable name, you can refer to this memory block and access the value stored in it. Since the value may change, it's called a variable, otherwise, it would be a constant.

## Variable Names

In C, variable names are a type of identifier with strict naming rules:

- Can only include letters (both uppercase and lowercase), digits, and underscores (`_`).
- Cannot start with a digit.
- Cannot exceed 63 characters in length.

Here are examples of invalid variable names:

```c
$zj
j**p
2cat
Hot-tab
tax rate
don't
```

Variable names are case-sensitive, so `star`, `Star`, and `STAR` are considered different variables.

Certain words in C have special meanings (e.g., `int`), and some are reserved for commands (e.g., `continue`). These are known as keywords and cannot be used as variable names. C also reserves some words for future use, and these reserved words cannot be used as variable names either. Here are some of C's main keywords and reserved words:

> auto, break, case, char, const, continue, default, do, double, else, enum, extern, float, for, goto, if, inline, int, long, register, restrict, return, short, signed, sizeof, static, struct, switch, typedef, union, unsigned, void, volatile, while

Additionally, variable names starting with two underscores or an underscore followed by an uppercase letter are reserved for the system and should not be used.

## Variable Declaration

In C, variables must be declared before use. Using a variable without declaring it first will result in an error.

Each variable has a type. When declaring a variable, you must specify its type to the compiler.

```c
int height;
```

In the above code, the variable `height` is declared with the type `int` (integer).

If multiple variables have the same type, they can be declared on the same line:

```c
int height, width;

// Equivalent to
int height;
int width;
```

Note that the variable declaration statement must end with a semicolon.

Once declared, a variable's type cannot be changed at runtime.

## Variable Assignment

In C, memory space is allocated for a variable when it's declared, but the memory is not initialized, leading to the variable containing a random value. Therefore, a variable should be assigned a value before use.

The assignment operation is performed using the assignment operator (`=`).

```c
int num;
num = 42;
```

In the above example, the first line declares an integer variable `num`, and the second line assigns the value `42` to it.

The value assigned to a variable should match its type. For example, `num` is an integer variable, so it should not be assigned a floating-point value. Although C can automatically convert types, it's best to avoid type mismatches in assignment operations.

Variable declaration and assignment can also be done in one line:

```c
int num = 42;
```

Multiple variables of the same type can be assigned values on the same line:

```c
int x = 1, y = 2;
```

Note that assignment expressions have a return value, which is the value on the right-hand side of the assignment.

```c
int x, y;

x = 1;
y = (x = 2 * x);
```

In the above code, the value of variable `y` is the return value of the assignment expression `(x = 2 * x)`, which is `2`.

Because assignment expressions have a return value, C allows for multiple assignment expressions:

```c
int x, y, z, m, n;

x = y = z = m = n = 3;
```

In the above code, multiple variables are assigned values in one line. The assignment operator is evaluated from right to left, so `n` is assigned first, followed by `m`, `z`, `y`, and `x`.

C distinguishes between lvalues (left values) and rvalues (right values). An lvalue can appear on the left side of an assignment operator and is usually a variable; an rvalue can appear on the right side of an assignment operator and is usually a literal value. This distinction is to ensure that only valid expressions appear on the left side of the assignment operator. For instance, `x = 1` is valid, but `1 = x` will result in an error.

## Variable Scope

Scope refers to the range in which a variable is valid and can be used. In C, variables have two main types of scope: file scope and block scope.

**File Scope** refers to variables declared at the top level of a source file. These variables are valid from the point of declaration to the end of the file.

```c
int x = 1;

int main(void) 
{
  printf("%i\n", x);
}
```

In the above example, the variable `x` is declared at the top level of the file and is accessible throughout the entire file, including within the `main()` function.

**Block Scope** refers to variables declared within a block of code enclosed by curly braces (`{}`). Variables declared within a block are only valid within that block and are not visible outside of it.

```c
int a = 12;

if (a == 12) 
{
  int b = 99;
  printf("%d %d\n", a, b);  // 12 99
}

printf("%d\n", a);  // 12
printf("%d\n", b);  // Error
```

In the above example, the variable `b` is declared within the `if` block and is not visible outside this block, leading to an error if accessed outside.

Blocks can be nested, creating multiple levels of block scope. The rules are: inner blocks can use variables declared in outer blocks, but outer blocks cannot use variables declared in inner blocks. If a variable in an inner block has the same name as a variable in an outer block, it will shadow the outer variable within the inner block.

```c
{
  int i = 10;

  {
    int i = 20;
    printf("%d\n", i);  // 20
  }

  printf("%d\n", i);  // 10
}
```

In the above example, both inner and outer blocks declare a variable `i`. Each block uses the `i` declared within its own scope.

The most common block scope is a function. Variables declared within a function are not visible outside the function. The `for` loop also creates a block scope, where loop variables are only visible inside the loop body.

```c
for (int i = 0; i < 10; i++)
  printf("%d\n", i);

printf("%d\n", i); // Error
```

In the above example, the `for` loop, even without curly braces, creates a block scope. Attempting to access the loop variable `i` outside the loop results in a compile-time error.

# 4. Operators

There are over 50 operators in C language, which can be divided into several categories.

## Arithmetic Operators

Arithmetic operators are used for arithmetic operations, mainly including the following:

- `+`: Unary plus operator
- `-`: Unary minus operator
- `+`: Binary addition operator
- `-`: Binary subtraction operator
- `*`: Multiplication operator
- `/`: Division operator
- `%`: Modulus operator

#### (1) `+`, `-`

`+` and `-` can be used as both unary and binary operators. A "unary operator" is one that operates on a single operand. The unary operator `-` changes the sign of a value.

```c
int x = -12;
```

In the example above, `-` changes the value `12` to `-12`.

The unary operator `+` has no effect on the sign of the value and is completely optional; however, it will not cause an error if used.

```c
int x = -12;
int y = +x;
```

In the example above, the value of `y` is still `-12` because `+` does not change the sign.

Binary operators `+` and `-` are used for addition and subtraction.

```c
int x = 4 + 22;
int y = 61 - 23;
```

#### (2) `*`

The operator `*` is used for multiplication.

```c
int num = 5;
printf("%i\n", num * num); // Output 25
```

#### (3) `/`

The operator `/` is used for division. Note that dividing two integers results in an integer.

```c
float x = 6 / 4;
printf("%f\n", x); // Output 1.000000
```

In the example above, even though the variable `x` is of type `float`, the result of `6 / 4` is `1.0`, not `1.5`. This is because integer division in C language performs integer division and returns only the integer part, discarding the fractional part.

To get a floating-point result, at least one of the operands must be a floating-point number, in which case C will perform floating-point division.

```c
float x = 6.0 / 4; // or written as 6 / 4.0
printf("%f\n", x); // Output 1.500000
```

In the example above, `6.0 / 4` performs floating-point division, resulting in `1.5`.

Here's another example.

```c
int score = 5;
score = (score / 20) * 100;
```

In this code, you might expect `score` to be `25` after the calculation, but in reality, `score` is `0`. This is because `score / 20` is integer division and results in `0`, so multiplying by `100` also results in `0`.

To get the expected result, you can change the divisor `20` to `20.0` to perform floating-point division.

```c
score = (score / 20.0) * 100;
```

#### (4) `%`

The operator `%` represents the modulus operation, which returns the remainder of the division of two integers. This operator can only be used with integers, not floating-point numbers.

```c
int x = 6 % 4; // 2
```

The rule for modulus with negative numbers is that the sign of the result is determined by the sign of the first operand.

```c
11 % -5 // 1
-11 % -5 // -1
-11 % 5 // -1
```

In the examples above, the sign of the result is determined by the sign of the first operand (`11` or `-11`).

#### (5) Compound Assignment Operators

If a variable performs arithmetic operations on itself, C provides shorthand forms that combine the assignment operator with the arithmetic operator.

- `+=`
- `-=`
- `*=`
- `/=`
- `%=` 

Here are some examples.

```c
i += 3;  // Equivalent to i = i + 3
i -= 8;  // Equivalent to i = i - 8
i *= 9;  // Equivalent to i = i * 9
i /= 2;  // Equivalent to i = i / 2
i %= 5;  // Equivalent to i = i % 5
```

## Increment and Decrement Operators

C language provides two operators for incrementing and decrementing a variable by `+1` and `-1`.

- `++`: Increment operator
- `--`: Decrement operator

```c
i++; // Equivalent to i = i + 1
i--; // Equivalent to i = i - 1
```

The position of these operators before or after the variable makes a difference. `++var` and `--var` perform the increment or decrement operation first and then return the value of `var` after the operation; `var++` and `var--` return the value of `var` before the operation and then perform the increment or decrement.

```c
int i = 42;
int j;

j = (i++ + 10);
// i: 43
// j: 52

j = (++i + 10);
// i: 44
// j: 54
```

In the example above, the position of the increment operator causes `j` to receive different values. This kind of writing can lead to unexpected results, so you can use the following alternative approaches to avoid such issues.

```c
/* Approach 1 */
j = (i + 10);
i++;

/* Approach 2 */
i++;
j = (i + 10);
```

In these examples, the increment operation and the value return of variable `i` are separated into two steps, which reduces the chance of errors and improves code readability.

## Relational Operators

Expressions used for comparison in C are called "relational expressions," and the operators used in them are called "relational operators." There are mainly 6 relational operators:

- `>` Greater than operator
- `<` Less than operator
- `>=` Greater than or equal to operator
- `<=` Less than or equal to operator
- `==` Equal to operator
- `!=` Not equal to operator

Here are some examples.

```c
a == b;
a != b;
a < b;
a > b;
a <= b;
a >= b;
```

Relational expressions usually return `0` or `1`, representing false or true. In C language, `0` means false, and all non-zero values mean true. For example, `20 > 12` returns `1`, while `12 > 20` returns `0`.

Relational expressions are commonly used in `if` or `while` structures.

```c
if (x == 3) 
{
  printf("x is 3.\n");
}
```

Note that the equal-to operator `==` and the assignment operator `=` are different and should not be confused. Sometimes, you might accidentally write the following code, which can run but may produce unintended results.

```c
if (x = 3) ...
```

In this example, the intention was `x == 3`, but it was mistakenly written as `x = 3`. This statement assigns `3` to variable `x`, and its return value is `3`, so the `if` condition is always true.

To avoid this error, some programmers prefer to write the variable on the right side of the equality.

```c
if (3 == x) ...
```

In this way, if you mistakenly write `==` as `=`, the compiler will generate an error.

```c
/* Error */
if (3 = x) ...
```

Another mistake to avoid is using multiple relational operators in a chain.

```c
i < j < k
```

In this example, two less-than operators are used consecutively. This is a valid expression but usually does not achieve the intended result, meaning it does not guarantee that variable `j` is between `i` and `k`. Since relational operators are evaluated left to right, the actual expression executed is:

```c
(i < j) < k
```

In this expression, `i < j` returns `0` or `1`, so the final comparison is between `0` or `1` and variable `k`. To check if variable `j` is between `i` and `k`, you should use the following approach:

```c
i < j && j < k
```

## Logical Operators

Logical operators provide logical judgment functions for constructing more complex expressions. The main ones are:

- `!`: NOT operator (negates the truth value of a single expression).
- `&&`: AND operator (true if both expressions are true, otherwise false).
- `||`: OR operator (true if at least one expression is true, otherwise false).

Here is an example of the AND operator.

```c
if (x < 10 && y > 20)
  printf("Doing something!\n");
```

In this example, `x < 10 && y > 20` is true only if both `x < 10` and `y > 20` are true.

Here is an example of the NOT operator.

```c
if (!(x < 12))
  printf("x is not less than 12\n");
```

In this example, the NOT operator `!` has higher precedence than `<`, so parentheses are required to negate the expression `x < 12`. A more straightforward approach would be `if (x >= 12)`, but this is just for illustration.

For logical operators, any non-zero value represents true, and zero represents false. For example, `5 || 0` returns `1`, and `5 && 0` returns `0`.

A characteristic of logical operators is that they always evaluate the left-hand expression first and then the right-hand expression. This sequence is guaranteed. If the left-hand expression satisfies the condition for the logical operator, the right-hand expression is not evaluated. This situation is called "short-circuiting."

```c
if (number != 0 && 12/number == 2)
```

In this example, if the left-hand expression (`number != 0`) is false (i.e., `number` is `0`), the right-hand expression (`12/number == 2`) will not be executed. Since the left-hand expression returns `0`, the entire `&&` expression is false, so the right-hand expression is skipped.

Since logical operators evaluate from left to right, the following code can be problematic.

```c
while ((x++ < 10) && (x + y < 20))
```

In this example, after evaluating the left-hand expression, the value of `x` changes. By the time the right-hand expression is evaluated, it uses the updated value, which might not be the original intent.

## Bitwise Operators

C language provides several bitwise operators to manipulate binary bits.

1. **Bitwise NOT Operator `~`**

The bitwise NOT operator `~` is a unary operator that inverts each binary bit, i.e., `0` becomes `1` and `1` becomes `0`.

```c
// Returns 01101100
~10010011
```

In this example, `~` inverts each binary bit to get a new value.

Note that the `~` operator does not change the variable's value but returns a new value.

2. **Bitwise AND Operator `&`**

The bitwise AND operator `&` compares each binary bit of two values and returns a new value. It returns `1` if both bits are `1`; otherwise, it returns `0`.

```c
// Returns 00010001
10010011 & 00111101
```

In this example, the two 8-bit binary numbers are compared bit by bit, resulting in a new value.

The bitwise AND operator `&` can be combined with the assignment operator `=` as `&=`.

```c
int val = 3;
val = val & 0377;

// Simplified as
val &= 0377;
```

3. **Bitwise OR Operator `|`**

The bitwise OR operator `|` compares each binary bit of two values and returns a new value. It returns `1` if at least one of the bits is `1` (including the case where both are `1`); otherwise, it returns `0`.

```c
// Returns 10111111
10010011 | 00111101
```

The bitwise OR operator `|` can be combined with the assignment operator `=` as `|=`.

```c
int val = 3;
val = val | 0377;

// Simplified as
val |= 0377;
```

4. **Bitwise XOR Operator `^`**

The bitwise XOR operator `^` compares each binary bit of two values and returns a new value. It returns `1` if exactly one of the bits is `1`; otherwise, it returns `0`.

```c
// Returns 10101110
10010011 ^ 00111101
```

The bitwise XOR operator `^` can be combined with the assignment operator `=` as `^=`.

```c
int val = 3;
val = val ^ 0377;

// Simplified as
val ^= 0377;
```

5. **Bitwise Left Shift Operator `<<`**

The bitwise left shift operator `<<` shifts each bit of the left operand to the left by the number of positions specified by the right operand. The vacated positions are filled with `0`.

```c
// 1000101000
10001010 << 2
```

In this example, each bit of `10001010` is shifted two positions to the left.

The left shift operator effectively multiplies the operand by 2 raised to the specified power. For example, shifting left by 2 positions is equivalent to multiplying by 4 (2^2).

The left shift operator `<<` can be combined with the assignment operator `=` as `<<=`.

```c
int val = 1;
val = val << 2;

// Simplified as
val <<= 2;
```

6. **Bitwise Right Shift Operator `>>`**

The bitwise right shift operator `>>` shifts each bit of the left operand to the right by the number of positions specified by the right operand. The discarded values are lost, and the vacated positions are filled with `0`.

```c
// Returns 00100010
10001010 >> 2
```

In this example, each bit of `10001010` is shifted two positions to the right. The lowest two bits `10` are discarded, and the vacated positions are filled with `0`, resulting in `00100010`.

Note that the right shift operator is best used with unsigned integers and should not be used with negative numbers, as different systems handle the sign bit differently, which may lead to inconsistent results.

The right shift operator effectively divides the operand by 2 raised to the specified power. For example, shifting right by 2 positions is equivalent to dividing by 4 (2^2).

The right shift operator `>>` can be combined with the assignment operator `=` as `>>=`.

```c
int val = 1;
val = val >> 2;

// Simplified as
val >>= 2;
```

## Comma Operator

The comma operator allows multiple expressions to be written together, with each expression being executed from left to right.

```c
x = 10, y = 20;
```

In this example, there are two expressions (`x = 10` and `y = 20`), and the comma operator allows them to be on the same line of code.

The comma operator returns the value of the last expression as the result of the entire statement.

```c
int x;

x = (1, 2, 3);
```

In this example, the comma operator within the parentheses returns the value of the last expression, so the variable `x` is assigned the value `3`.

## Operator Precedence

Operator precedence determines which operator should be evaluated first in an expression that contains multiple operators. Different operators have different levels of precedence.

```c
3 + 4 * 5;
```

In this example, the expression `3 + 4 * 5` includes both addition (`+`) and multiplication (`*`) operators. Since multiplication has higher precedence than addition, `4 * 5` is evaluated first, not `3 + 4`.

If two operators have the same precedence, their order of evaluation is determined by whether they are left-associative or right-associative. Most operators are left-associative (evaluated from left to right), but a few operators are right-associative (evaluated from right to left), such as the assignment operator (`=`).

```c
5 * 6 / 2;
```

In this example, both `*` and `/` have the same precedence and are left-associative, so they are evaluated from left to right: first `5 * 6` and then `30 / 2`.

The precedence of operators is complex. Here are some operators' precedence levels (from highest to lowest):

- Parentheses (`()`)
- Unary increment (`++`), unary decrement (`--`)
- Unary operators (`+` and `-`)
- Multiplication (`*`), division (`/`)
- Addition (`+`), subtraction (`-`)
- Relational operators (`<`, `>`, etc.)
- Assignment operator (`=`)

Since parentheses have the highest precedence, they can be used to change the precedence of other operators.

```c
int x = (3 + 4) * 5;
```

In this example, because of the parentheses, addition is performed before multiplication.

Memorizing all operator precedence levels is not necessary. Using parentheses frequently helps prevent unintended outcomes and improves code readability.

# 5. Flow Control

In C programming, the default execution is sequential—statements are executed one after another. To control the flow of execution, developers use flow control constructs, primarily conditional and looping statements.

## `if` Statement

The `if` statement is used for conditional execution. It executes a specified statement if the condition is true.

```c
if (expression) statement;
```

In this syntax, if the condition `expression` is true (non-zero), the `statement` is executed.

The condition `expression` must be enclosed in parentheses, or a syntax error will occur. The `statement` part can be a single statement or a block of statements enclosed in curly braces. Here’s an example:

```c
if (x == 10) 
    printf("x is 10");
```

In this example, when the variable `x` is `10`, the program prints a message. For a single statement, it’s common to place the statement on a new line.

```c
if (x == 10) 
    printf("x is 10\n");
```

If there are multiple statements, they should be enclosed in curly braces to form a compound statement:

```c
if (line_num == MAX_LINES) 
{
    line_num = 0;
    page_num++;
}
```

The `if` statement can be paired with an `else` branch, which specifies the code to be executed if the condition is false (i.e., when `expression` evaluates to `0`).

```c
if (expression) 
    statement;
else 
    statement;
```

Here’s an example:

```c
if (i > j) 
    max = i;
else 
    max = j;
```

If the `else` branch contains multiple statements, they should be enclosed in curly braces as well.

The `else` can be used with another `if` statement to form a nested conditional structure.

```c
if (expression) 
    statement;
else if (expression) 
    statement;
...
else if (expression) 
    statement;
else 
    statement;
```

When there are multiple `if` and `else` statements, remember that an `else` always matches the nearest preceding `if`.

```c
if (number > 6) 
    if (number < 12) 
        printf("The number is more than 6, less than 12.\n");
else 
    printf("It is a wrong number.\n");
```

In this example, the `else` matches the nearest `if` (i.e., `number < 12`), so if `number` is `6`, the `else` part will not be executed.

To avoid confusion and improve code readability, it is recommended to use curly braces to clearly indicate which `if` an `else` matches.

```c
if (number > 6) 
{
    if (number < 12) 
    {
        printf("The number is more than 6, less than 12.\n");
    }
} 
else 
{
    printf("It is a wrong number.\n");
}
```

In this example, using curly braces makes it clear that the `else` corresponds to the outer `if`.

## Ternary Operator `?:`

The ternary operator `?:` in C is a shorthand for the `if...else` statement.

```c
<expression1> ? <expression2> : <expression3>
```

This operator means that if `expression1` is true (non-zero), `expression2` is executed; otherwise, `expression3` is executed.

Here’s an example that returns the larger of two values:

```c
(i > j) ? i : j;
```

The above code is equivalent to the following `if` statement:

```c
if (i > j)
    return i;
else
    return j;
```

## `switch` Statement

The `switch` statement is a special form of the `if...else` structure used for multiple possible results. It transforms multiple `else if` branches into a more readable and manageable format.

```c
switch (expression) 
{
    case value1: statement;
    case value2: statement;
    default: statement;
}
```

In this code, depending on the value of `expression`, the corresponding `case` branch is executed. If no matching value is found, the `default` branch is executed.

Here’s an example:

```c
switch (grade) 
{
    case 0:
        printf("False");
        break;
    case 1:
        printf("True");
        break;
    default:
        printf("Illegal");
}
```

In this example, based on the value of the `grade` variable, different `case` branches are executed. If the value is `0`, the code for `case 0` executes; if `1`, the code for `case 1` executes; otherwise, the `default` branch is executed. The `default` branch handles cases not covered by the preceding `case` branches.

Each `case` statement should end with a `break` statement to exit the `switch` block and prevent execution from falling through to the next `case` or `default` branch. Without `break`, execution will continue to the next `case` or `default` block.

```c
switch (grade) 
{
    case 0:
        printf("False");
    case 1:
        printf("True");
        break;
    default:
        printf("Illegal");
}
```

In the above example, the lack of a `break` statement in `case 0` causes the code to continue executing into `case 1`.

This feature can be utilized if multiple `case` branches should execute the same code:

```c
switch (grade)
{
    case 0:
    case 1:
        printf("True");
        break;
    default:
        printf("Illegal");
}
```

In this example, both `case 0` and `case 1` will execute the same `printf` statement because `case 0` has no `break` statement.

The `case` statements do not need to be enclosed in curly braces, which is why the `break` statement is necessary to avoid fall-through.

The `default` branch handles cases where none of the preceding `case` values match. It’s best placed at the end of all `case` statements, so you don’t need a `break` statement. This branch is optional; if omitted, the program will simply exit the `switch` block when no `case` matches.

## `while` Statement

The `while` statement is used for looping, executing the loop body as long as a specified condition is true.

```c
while (expression)
    statement;
```

In this code, if `expression` is non-zero (true), `statement` is executed. After execution, the condition `expression` is checked again. If `expression` becomes zero (false), the loop exits and does not execute the loop body anymore.

```c
while (i < n)
    i = i + 2;
```

In this example, as long as `i` is less than `n`, `i` will keep increasing by 2.

If the loop body contains multiple statements, they should be enclosed in curly braces.

```c
while (expression) 
{
    statement;
    statement;
}
```

Here’s an example:

```c
i = 0;

while (i < 10)
{
    printf("i is now %d!\n", i);
    i++;
}

printf("All done!\n");
```

In this example, the loop body will execute 10 times, incrementing `i` by 1 each time until `i` equals 10, at which point the loop exits.

A `while` loop can run indefinitely if the condition always remains true. Here is a common way to write an infinite loop:

```c
while (1) 
{
    // ...
}
```

In the above example, the loop will run indefinitely, but you can use a `break` statement within the loop to exit.

## `do...while` Structure

The `do...while` structure is a variant of the `while` loop. It executes the loop body once before checking the condition. If the condition is true, it continues to execute the loop body; otherwise, it exits the loop.

```c
do statement
while (expression);
```

In this code, the loop body `statement` will execute at least once, regardless of whether `expression` is true or false. After executing `statement`, `expression` is evaluated to determine whether to continue the loop.

```c
i = 10;

do --i;
while (i > 0);
```

In this example, `i` is decremented by 1, and then checked to see if it is greater than 0. The loop continues until `i` equals 0.

If the loop body contains multiple statements, they should be enclosed in curly braces.

```c
i = 10;

do 
{
    printf("i is %d\n", i);
    i++;
} while (i < 10);

printf("All done!\n");
```

In this example, even though `i` does not satisfy the condition to be less than 10, the loop body executes once.

## `for` Statement

The `for` statement is commonly used for loops where the number of iterations is known beforehand.

```c
for (initialization; continuation; action)
    statement;
```

In this code, the `for` statement includes three expressions:

- `initialization`: An expression to initialize the loop variable, executed only once.
- `continuation`: A condition to test before each iteration. The loop continues as long as this expression is true.
- `action`: An expression to modify the loop variable, executed after each iteration.

The loop body `statement` can be a single statement or a block of statements enclosed in curly braces. Here’s an example:

```c
for (int i = 10; i > 0; i--)
    printf("i is %d\n", i);
```

In this example, the loop variable `i` is declared and initialized in the `for` statement. The variable `i` is scoped only within the loop. After exiting the loop, it is no longer available.

Each of the three expressions in a `for` loop can contain multiple statements, separated by commas.

```c
int i, j;
for (i = 0, j = 999; i < 10; i++, j--) 
{
    printf("%d, %d\n", i, j);
}
```

In this example, the initialization part has two statements, initializing `i` and `j`.

All three expressions in a `for` statement are optional, and you can omit them, which results in an infinite loop if no condition is provided.

```c
for (;;) 
{
    printf("This line will print indefinitely.\n");
}
```

In this example, since no condition is provided, the loop will run indefinitely.

## `break` Statement

The `break` statement serves two main purposes. One is to be used with the `switch` statement to terminate the execution of a particular branch, which has already been discussed. The other use is to exit a loop early, skipping the remaining iterations.

```c
for (int i = 0; i < 3; i++) 
{
    for (int j = 0; j < 3; j++) 
    {
        printf("%d, %d\n", i, j);
        break;
    }
}
```

In this example, the `break` statement causes the inner loop to exit after the first iteration, so the outer loop proceeds to the next iteration.

```c
while ((ch = getchar()) != EOF) 
{
    if (ch == '\n') break;
    putchar(ch);
}
```

In this example, once a newline character (`'\n'`) is encountered, the `break` statement exits the entire `while` loop and stops reading further characters.

Note that `break` can only be used to exit loops and `switch` statements, and cannot be used to exit an `if` structure.

```c
if (n > 1) 
{
    if (n > 2) break; // Invalid
    printf("hello\n");
}
```

In this example, the `break` statement is invalid because it cannot exit the outer `if` structure.

## `continue` Statement

The `continue` statement is used to skip the remaining statements in the current iteration of the loop and proceed to the next iteration. When `continue` is encountered, the rest of the code in the loop body is skipped, and the loop condition is re-evaluated to determine whether to continue.

```c
for (int i = 0; i < 3; i++) 
{
    for (int j = 0; j < 3; j++)
    {
        printf("%d, %d\n", i, j);
        continue;
    }
}
```

In this example, the `continue` statement makes no difference because it doesn't change the behavior of the loop. It just skips to the next iteration of the inner loop.

```c
while ((ch = getchar()) != '\n') 
{
    if (ch == '\t') continue;
    putchar(ch);
}
```

In this example, if the character read is a tab (`'\t'`), the `continue` statement skips the `putchar` call and reads the next character.

## `goto` Statement

The `goto` statement is used to jump to a specified label within the code. It is generally discouraged in structured programming due to its tendency to create confusing and hard-to-maintain code, but it is included here for completeness.

```c
char ch;

top: ch = getchar();

if (ch == 'q')
    goto top;
```

In this example, `top` is a label that the `goto` statement can jump to, effectively creating a loop that continues to read characters until `'q'` is encountered.

```c
infinite_loop:
    printf("Hello, world!\n");
    goto infinite_loop;
```

This code creates an infinite loop by repeatedly jumping to the `infinite_loop` label.

One primary use of `goto` is to break out of multiple nested loops.

```c
for(...) 
{
    for (...) 
    {
        while (...) 
        {
            do 
            {
                if (some_error_condition)
                    goto bail;    
            } while(...);
        }
    }
}

bail:
// ... 
```

In this example, `goto` allows for an immediate exit from several layers of nested loops.

Another use of `goto` is to handle errors in a series of checks more gracefully.

```c
if (do_something() == ERR)
    goto error;
if (do_something2() == ERR)
    goto error;
if (do_something3() == ERR)
    goto error;
if (do_something4() == ERR)
    goto error;
```

In this example, if any function returns an error, `goto` will skip to the `error` label.

Note that `goto` can only jump within the same function and cannot jump to a label in a different function.

# 6. Data Types

Each type of data in C language has a type, which the compiler must know to operate on the data. The "type" refers to the common characteristics shared by similar data. Once the type of a value is known, its characteristics and operations can be determined.

There are three basic data types: characters (char), integers (int), and floating-point numbers (float). Complex types are built upon these.

## Character Type

The character type refers to a single character, and the type declaration uses the `char` keyword.

```c
char c = 'B';
```

The example above declares that the variable `c` is of type char and assigns it the letter `B`.

In C language, character constants must be enclosed in single quotes.

Internally, characters are stored using one byte (8 bits). C language treats it as an integer, so the character type is an integer with a width of one byte. Each character corresponds to an integer (determined by ASCII code), for example, `B` corresponds to integer `66`.

The default range for character types varies across different computers. Some systems default to `-128` to `127`, while others default to `0` to `255`. Both ranges cover the ASCII character range from `0` to `127`.

As long as it is within the range of the character type, integers can be interchanged with characters and assigned to character type variables.

```c
char c = 66;
// Equivalent to
char c = 'B';
```

In the example above, the variable `c` is of character type and is assigned the integer value 66. This has the same effect as assigning the character `B`.

Two character type variables can be used in mathematical operations.

```c
char a = 'B'; // Equivalent to char a = 66;
char b = 'C'; // Equivalent to char b = 67;

printf("%d\n", a + b); // Output 133
```

In the example above, adding character type variables `a` and `b` is treated as adding two integers. The placeholder `%d` represents the output as a decimal integer, so the result is 133.

Single quotes themselves are characters. To represent this character constant, a backslash escape is needed.

```c
char t = '\'';
```

In the example above, the variable `t` is a single quote character. Since character constants must be enclosed in single quotes, the internal single quote must be escaped with a backslash.

This escape notation is mainly used to represent non-printable control characters defined by ASCII codes, which also belong to character type values.

-   `\a`: Alert, which makes the terminal emit a sound or flash, or both.
-   `\b`: Backspace, moves the cursor back one character without deleting the character.
-   `\f`: Form feed, moves the cursor to the next page. On modern systems, this has no effect and behaves like `\v`.
-   `\n`: Newline.
-   `\r`: Carriage return, moves the cursor to the beginning of the same line.
-   `\t`: Tab, moves the cursor to the next horizontal tab stop, usually the next multiple of 8.
-   `\v`: Vertical tab, moves the cursor to the next vertical tab stop, usually the same column on the next line.
-   `\0`: Null character, representing no content. Note that this value is not equal to the digit 0.

Escape sequences can also use octal and hexadecimal representations for a character.

-   `\nn`: Octal representation of a character, where `nn` is the octal value.
-   `\xnn`: Hexadecimal representation of a character, where `nn` is the hexadecimal value.

```c
char x = 'B';
char x = 66;
char x = '\102'; // Octal
char x = '\x42'; // Hexadecimal
```

The four representations in the example above are equivalent.

## Integer Types

### Overview

Integer types are used to represent large integers, and the type declaration uses the `int` keyword.

```c
int a;
```

The example above declares an integer variable `a`.

The size of the `int` type varies across different computers. Commonly, an `int` is stored in 4 bytes (32 bits), but it may also be 2 bytes (16 bits) or 8 bytes (64 bits). The ranges they can represent are as follows:

-   16-bit: -32,768 to 32,767.
-   32-bit: -2,147,483,648 to 2,147,483,647.
-   64-bit: -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.

### signed, unsigned

C language uses the `signed` keyword to indicate that a type has a sign and includes negative values; the `unsigned` keyword indicates that the type has no sign and can only represent zero and positive integers.

For `int` type, it is signed by default, meaning `int` is equivalent to `signed int`. Since this is the default, the `signed` keyword is generally omitted, but including it is not incorrect.

```c
signed int a;
// Equivalent to
int a;
```

The `int` type can also be unsigned, representing only non-negative integers. In this case, the `unsigned` keyword must be used.

```c
unsigned int a;
```

The advantage of declaring an integer variable as `unsigned` is that the maximum integer value representable in the same amount of memory is doubled. For example, a 16-bit `signed int` has a maximum value of 32,767, while an `unsigned int` has a maximum value of 65,535.

The `int` in `unsigned int` can be omitted, so the above declaration can also be written as:

```c
unsigned a;
```

The `char` type can also be declared as `signed` or `unsigned`.

```c
signed char c; // Range -128 to 127
unsigned char c; // Range 0 to 255
```

Note that C language specifies whether the `char` type is signed or unsigned by the current system. This means that `char` is not equivalent to `signed char`; it could be either `signed char` or `unsigned char`. This is different from `int`, which is equivalent to `signed int`.

### Integer Subtypes

If the `int` type uses 4 or 8 bytes to represent an integer, it wastes space for small integers. On the other hand, some situations require even larger integers, and 8 bytes may not be enough. To address these issues, C language provides three integer subtypes in addition to `int`. This helps to more precisely specify the range of integer variables and better express the intent of the code.

-   `short int` (abbreviated as `short`): Takes up no more space than `int`, typically 2 bytes (range -32,768 to 32,767).
-   `long int` (abbreviated as `long`): Takes up no less space than `int`, at least 4 bytes.
-   `long long int` (abbreviated as `long long`): Takes up more space than `long`, at least 8 bytes.

```c
short int a;
long int b;
long long int c;
```

The code above declares variables of three integer subtypes.

By default, `short`, `long`, and `long long` are signed (i.e., the `signed` keyword is omitted). They can also be declared as unsigned, which doubles the maximum value they can represent.

```c
unsigned short int a;
unsigned long int b;
unsigned long long int c;
```

C language allows omitting `int`, so variable declarations can also be written as follows.

```c
short a;
unsigned short a;

long b;
unsigned long b;

long long c;
unsigned long long c;
```

Different computers have different byte lengths for data types. If a 32-bit integer is needed, use `long` instead of `int` to ensure at least 4 bytes; if a 64-bit integer is needed, use `long long` to ensure at least 8 bytes. Conversely, for space-saving, use `short` for 16-bit integers and `char` for 8-bit integers.

### Limits of Integer Types

Sometimes it is necessary to check the maximum and minimum values of different integer types on the current system. C language provides corresponding constants in the header file `<limits.h>`, such as `SCHAR_MIN` representing the minimum value of `signed char` (-128) and `SCHAR_MAX` representing the maximum value (127).

To ensure code portability, use these constants when checking the limits of integer types.

-   `SCHAR_MIN`, `SCHAR_MAX`: Minimum and maximum values of `signed char`.
-   `UCHAR_MAX`: Maximum value of `unsigned char`.
-   `SHRT_MIN`, `SHRT_MAX`: Minimum and maximum values of `short`.
-   `USHRT_MAX`: Maximum value of `unsigned short`.
-   `INT_MIN`, `INT_MAX`: Minimum and maximum values of `int`.
-   `UINT_MAX`: Maximum value of `unsigned int`.
-   `LONG_MIN`, `LONG_MAX`: Minimum and maximum values of `long`.
-   `ULONG_MAX`: Maximum value of `unsigned long`.
-   `LLONG_MIN`, `LLONG_MAX`: Minimum and maximum values of `long long`.
-   `ULLONG_MAX`: Maximum value of `unsigned long long`.

### Summary

#### Integer Types

-   `char` : Used to represent characters, actually an integer type that can store an 8-bit integer.

    ```
    char a = 'A'; // Or char a = 65;
    ```

-   `short` : Short integer, typically a 16-bit integer.

    ```
    short b = 32767;
    ```

-   `int` : Integer, typically a 32-bit integer.

    ```
    int c = 2147483647;
    ```

-   `long` : Long integer, typically a 32-bit or 64-bit integer.

    ```
    long d = 2147483647L; // Use L suffix
    ```

-   `long long` : Long long integer, typically a 64-bit integer.

    ```
    long long e = 9223372036854775807LL; // Use LL suffix
    ```

-   `unsigned` : Unsigned integer, which can be combined with the above types, such as `unsigned int`, to represent only non-negative integers.

    ```
    unsigned int f = 4294967295U; // Use U suffix
    ```

#### Floating-Point Types

-   `float` : Single-precision floating-point type, typically 32-bit.

    ```
    float g = 3.14f; // Use f suffix
    ```

-   `double` : Double-precision floating-point type, typically 64-bit.

    ```
    double h = 3.141592653589793;
    ```

-   `long double` : Extended precision floating-point type, typically extended precision (depends on implementation, might be 80, 96, or 128 bits).

    ```
    long double i = 3.141592653589793238462643383279L; // Use L suffix
    ```

#### Type Specifiers

You can add `unsigned` or `signed` (default is `signed`) before the above types, for example:

-   `unsigned short`
-   `signed long`
-   `unsigned char`

### Integer Bases

By default, integers in C language are decimal. To represent octal and hexadecimal numbers, specific notations must be used.

Octal numbers use `0` as a prefix, such as `017`, `0377`.

```c
int a = 012; // Octal, equivalent to decimal 10
```

Hexadecimal numbers use `0x` or `0X` as a prefix, such as `0xf`, `0X10`.

```c
int a = 0x1A2B; // Hexadecimal, equivalent to decimal 6699
```

Some compilers use `0b` prefix to represent binary numbers, but this is not standard.

```c
int x = 0b101010;
```

Note that different bases are just representations of integers and do not affect how integers are stored. All integers are stored in binary form, regardless of the representation. Different bases can be mixed, for example, `10 + 015 + 0x20` is a valid expression.

The `%printf()` format specifiers for bases are as follows:

-   `%o`: Octal integer.
-   `%d`: Decimal integer.
-   `%x`: Hexadecimal integer.
-   `%#o`: Octal integer with `0` prefix.
-   `%#x`: Hexadecimal integer with `0x` prefix.
-   `%#X`: Hexadecimal integer with `0X` prefix.

```c
int x = 100;
printf("dec = %d\n", x); // 100
printf("octal = %o\n", x); // 144
printf("hex = %x\n", x); // 64
printf("octal = %#o\n", x); // 0144
printf("hex = %#x\n", x); // 0x64
printf("hex = %#X\n", x); // 0X64
```

## Floating-Point Types

Any value with a decimal point is interpreted by the compiler as a floating-point number. A "floating-point number" is stored in the form \( m \times b^e \), where `m` is the mantissa, `b` is the base (usually 2), and `e` is the exponent. This form combines precision and range to represent very large or very small numbers.

The floating-point type is declared using the `float` keyword, which can be used to declare floating-point variables.

```c
float c = 10.5;
```

In the example above, the variable `c` is of floating-point type.

The `float` type occupies 4 bytes (32 bits), with 8 bits for the exponent's value and sign, and the remaining 24 bits for the mantissa's value and sign. The `float` type can provide at least 6 decimal digits of precision, with the exponent ranging from -37 to 37, i.e., values ranging from \( 10^{-37} \) to \( 10^{37} \).

Sometimes, 32-bit floating-point precision or range is insufficient. C provides two larger floating-point types:

- `double`: Occupies 8 bytes (64 bits), providing at least 13 decimal digits of precision.
- `long double`: Typically occupies 16 bytes.

Note that due to precision limitations, floating-point numbers are only approximate, and their calculations are not exact. For example, in C, `0.1 + 0.2` does not equal `0.3`, but has a small error.

```c
if (0.1 + 0.2 == 0.3) // false
```

C allows floating-point numbers to be represented in scientific notation, using the letter `e` to separate the mantissa and the exponent.

```c
double x = 123.456e+3; // 123.456 x 10^3
// Equivalent to
double x = 123.456e3;
```

In the example above, if there is a `+` sign after `e`, it can be omitted. Note that there should be no spaces around `e` in scientific notation.

Additionally, if the mantissa in scientific notation is in the form `0.x` or `x.0`, the `0` can be omitted.

```c
0.3E6
// Equivalent to
.3E6

3.0E6
// Equivalent to
3.E6
```

## Boolean Type

C originally did not have a separate type for boolean values and used the integer `0` to represent false, with all non-zero values representing true.

```c
int x = 1;
if (x)
{
  printf("x is true!\n");
}
```

In the example above, if `x` is equal to `1`, C treats this value as true and executes the code inside the if statement.

The C99 standard introduced the `_Bool` type for boolean values. However, this type is essentially an alias for integer types, with `0` representing false and `1` representing true. Here is an example.

```c
_Bool isNormal;

isNormal = 1;
if (isNormal)
  printf("Everything is OK.\n");
```

The header file `<stdbool.h>` defines another type alias `bool`, and defines `true` as `1` and `false` as `0`. By including this header file, these keywords can be used.

```c
#include <stdbool.h>

bool flag = false;
```

In the example above, after including the `<stdbool.h>` header file, you can use `bool` to define boolean values, and `false` and `true` to represent false and true.

## Literal Types

A literal refers to values directly appearing in the code.

```c
int x = 123;
```

In the above code, `x` is a variable, and `123` is a literal.

At compile time, literals are also written to memory, so the compiler must specify a data type for literals, just as it must for variables.

Typically, decimal integer literals (e.g., `123`) are specified as `int` by the compiler. If a number is too large to be represented by `int`, the compiler will specify it as `long int`. If it exceeds `long int`, it will be specified as `unsigned long`. If still not enough, it will be specified as `long long` or `unsigned long long`.

Decimals (e.g., `3.14`) will be specified as `double`.

## Literal Suffixes

Sometimes, programmers want to specify a different type for a literal. For example, if the compiler specifies an integer literal as `int`, but the programmer wants it to be `long`, a suffix `l` or `L` can be added to the literal, and the compiler will know to specify the literal as `long`.

```c
int x = 123L;
```

In the code above, the literal `123` has the suffix `L`, so the compiler specifies it as `long`. The literal `123L` can also be written as `123l`, but it is recommended to use `L` because the lowercase `l` can be confused with the digit `1`.

Octal and hexadecimal values can also use the suffixes `l` and `L` to specify `long` type, such as `020L` and `0x20L`.

```c
int y = 0377L;
int z = 0x7fffL;
```

To specify `unsigned int`, the suffixes `u` or `U` can be used.

```c
int x = 123U;
```

`L` and `U` can be combined to represent `unsigned long` type. The case and order of `L` and `U` are irrelevant.

```c
int x = 123LU;
```

For floating-point numbers, the compiler defaults to `double` type. If you want to specify another type, you need to add the suffix `f` (for float) or `l` (for long double) after the decimal point.

Scientific notation can also use suffixes.

```c
1.2345e+10F
1.2345e+10L
```

To summarize, common literal suffixes include:

- `f` and `F`: `float` type.
- `l` and `L`: For integers, `long int` type; for decimals, `long double` type.
- `ll` and `LL`: `long long` type, e.g., `3LL`.
- `u` and `U`: `unsigned int`, e.g., `15U`, `0377U`.

`u` can also be combined with other integer suffixes, and can be placed at the beginning or end, e.g., `10UL`, `10ULL`, and `10LLU` are all valid.

Here are some examples.

```c
int           x = 1234;
long int      x = 1234L;
long long int x = 1234LL;

unsigned int           x = 1234U;
unsigned long int      x = 1234UL;
unsigned long long int x = 1234ULL;

float x       = 3.14f;
double x      = 3.14;
long double x = 3.14L;
```

## Overflow

Each data type has a range of values it can store. If a value exceeds this range (either below the minimum or above the maximum), overflow occurs, requiring more binary bits to store. Values exceeding the maximum are called overflow; values below the minimum are called underflow.

In general, compilers do not report overflow errors but will execute code normally, ignoring the extra binary bits and only retaining the remaining bits, which can lead to unexpected results. Thus, overflow should be avoided.

```c
unsigned char x = 255;
x = x + 1;

printf("%d\n", x); // 0
```

In the example above, when `x` is incremented by `1`, the result is not `256`, but `0`. Since `x` is of type `unsigned char`, with a maximum value of `255` (binary `11111111`), adding `1` causes overflow, and the highest bit of `256` (binary `100000000`) is discarded, leaving the value `0`.

Consider the following example.

```c
unsigned int ui = UINT_MAX;  // 4,294,967,295
ui++;
printf("ui = %u\n", ui); // 0
ui--;
printf("ui = %u\n", ui); // 4,294,967,295
```

In the example above, `UINT_MAX` is the maximum value for `unsigned int`. Adding `1` causes overflow, resulting in `0`. Since `0` is the minimum value for this type, subtracting `1` returns `UINT_MAX`.

Overflow is easy to overlook, and since the compiler does not report it, caution is necessary.

```c
for (unsigned int i = n; i >= 0; --i) // Error
```

The code above seems correct, but the loop variable `i` is of type `unsigned int`, with a minimum value of `0`. When `i` is `0` and decremented, it does not return `-1`, but the maximum value of `unsigned int`, causing an infinite loop.

To avoid overflow, it’s best to compare the result with the type's limit values.

```c
unsigned int ui;
unsigned int sum;

// Incorrect
if (sum + ui > UINT_MAX) too_big();
else sum = sum + ui;

// Correct
if (ui > UINT_MAX - sum) too_big();
else sum = sum + ui;
```

In the example above, both `sum` and `ui` are of type `unsigned int`, and their sum is also of this type, which can cause overflow. However, you cannot determine overflow by checking if `sum + ui` exceeds `UINT_MAX` because `sum + ui` will always return the overflowed result. The correct approach is to compare `UINT_MAX - sum` with `ui`.

Here is another incorrect approach.

```c
unsigned int i = 5;
unsigned int j = 7;

if (i - j < 0) // Error
  printf("negative\n");
else
  printf("positive\n");
/* Unlike integer type operations below, unsigned int is greater than int, so in comparisons, it will not automatically convert to int type. For unsigned char and unsigned short, automatic conversion to int type avoids this error. */
```

In this example, the output will be `positive` because `i` and `j` are both `unsigned int`. The result of `i - j` is also of this type, with a minimum value of `0`, so it cannot be less than `0`. The correct approach is:

```c
if (j > i) // ....
```

## sizeof Operator

`sizeof` is an operator in C that returns the number of bytes occupied by a data type or a value. Its argument can be a data type keyword, a variable name, or a specific value.

```c
// Argument is a data type
int x = sizeof(int);

// Argument is a variable
int i;
sizeof(i);

// Argument is a value
sizeof(3.14);
```

In the first example, it returns the number of bytes occupied by the `int` type (usually `4` or `8`). The second example returns the number of bytes occupied by an integer variable, which is the same as the previous example. The third example returns the number of bytes occupied by the floating-point number `3.14`. Since floating-point literals are always stored as `double`, it returns `8`, as `double` occupies 8 bytes.

The return value of the `sizeof` operator is an unsigned integer, but C language does not specify the exact type, leaving it to the system to decide. The return type may be `unsigned int`, `unsigned long`, or `unsigned long long`, with corresponding `printf()` placeholders `%u`, `%lu`, and `%llu`. This affects portability.

To address this, C provides a type alias `size_t` to represent the `sizeof` return type consistently. Defined in the `<stddef.h>` header file (automatically included with `<stdio.h>`), `size_t` corresponds to the system's `sizeof` return type and could be `unsigned int`, `unsigned long`, etc.

C also provides a constant `SIZE_MAX`, representing the maximum integer `size_t` can hold. Hence, the range of integers that `size_t` can represent is `[0, SIZE_MAX]`.

`printf()` has specific placeholders `%zd` or `%zu` for `size_t` values.

```c
printf("%zd\n", sizeof(int));
```

In the code above, `%zd` (or `%zu`) can correctly output the `sizeof` return value regardless of its type.

If `%zd` or `%zu` is not supported, `%u` (unsigned int) or `%lu` (unsigned long int) can be used as alternatives.

## Type Automatic Conversion

In certain cases, C language automatically converts the type of a value.

### Assignment Operations

The assignment operator automatically converts the value on the right side to the type of the variable on the left side.

(1) Assigning a floating-point number to an integer variable

When assigning a floating-point number to an integer variable, C language simply discards the fractional part, not rounding it.

```c
int x = 3.14;
```

In the example above, the variable `x` is of integer type. The compiler automatically converts `3.14` to `int`, discarding the fractional part, so `x` is `3`.

This automatic conversion can lead to data loss (the fractional part of `3.14` is lost), so it is best to avoid cross-type assignment and ensure that variables and values are of the same type.

Note that when discarding the fractional part, it is not rounded but completely discarded.

```c
int x = 12.99;
```

In the example above, `x` is `12`, not rounded to `13`.

(2) Assigning an integer to a floating-point variable

When assigning an integer to a floating-point variable, it is automatically converted to a floating-point number.

```c
float y = 12 * 2;
```

In the example above, the value of `y` is not `24`, but `24.0`, because the integer on the right side of the equation is automatically converted to a floating-point number.

(3) Assigning a narrow type to a wide type

When assigning an integer type with a smaller byte width to a variable with a larger byte width, type promotion occurs, meaning the narrow type is automatically converted to the wide type.

For example, assigning a `char` or `short` type to an `int` type will automatically promote to `int`.

```c
char x = 10;
int i = x + y;
```

In the example above, the variable `x` is of type `char`, and when assigned to `int`, it is automatically promoted to `int`.

(4) Assigning a wide type to a narrow type

When assigning a type with a larger byte width to a variable with a smaller byte width, type demotion occurs, automatically converting to the latter type. This may lead to truncation, where extra binary bits are discarded, resulting in unpredictable outcomes.

```c
int i = 321;
char ch = i; // ch's value is 65 (remainder of 321 % 256)
```

In the example above, the variable `ch` is of type `char`, with 8 binary bits. The variable `i` is of type `int`. When assigning `i` to `ch`, the latter can only accommodate the last eight bits of `i` (binary `101000001`, 9 bits total), and the extra bits are discarded. The remaining eight bits become `01000001` (decimal 65, equivalent to character `A`).

Assigning a floating-point number to an integer type also causes truncation, where the fractional part of the floating-point number is discarded.

```c
double pi = 3.14159;
int i = pi; // i's value is 3
```

In the example above, `i` is `3`, with the fractional part of `pi` discarded.

### Mixed-Type Operations

When performing mixed-type calculations, values must be converted to the same type before computation. Conversion rules are as follows:

(1) When mixing integers and floating-point numbers, integers are converted to floating-point type, matching the type of the other operand.

```c
3 + 1.2 // 4.2
```

In the example above, mixing `int` and `float` types, the `int` value `3` is first converted to `float` (`3.0`), then the calculation yields `4.2`.

(2) When mixing different floating-point types, the smaller-width type is converted to the larger-width type, e.g., `float` to `double`, `double` to `long double`.

(3) When mixing different integer types, the smaller-width type is promoted to the larger-width type, e.g., `short` to `int`, `int` to `long`. Sometimes, signed types are also converted to unsigned types.

The execution result of the following example might be surprising:

```c
int a = -5;
if (a < sizeof(int))
  do_something();
```

In the example above, `a` is a signed integer, while `sizeof(int)` is of type `size_t`, which is an unsigned integer. According to the rules, `signed int` is automatically converted to `unsigned int`, so `a` is converted to an unsigned integer `4294967291` (the conversion rule is `-5` plus the maximum value of the unsigned integer plus 1), leading to a failed comparison and `do_something()` will not execute.

Thus, it is best to avoid mixing signed and unsigned integers in operations (comparisons, arithmetic operations, conditional operations, and mixed-type array indexing, as shown in the following example).

```c
#include <stdio.h>

int main() 
{
    int array[10];
    int index = -1;

    array[index] = 1; // index is promoted to unsigned integer

    printf("array[%d] = %d\n", index, array[index]);
    return 0;
}
```

In this case, C language automatically converts `signed int` to `unsigned int`, which might not yield the expected result.

### Integer Type Operations

When performing operations on two integers of the same type, or a single integer operation, the result is generally of the same type. However, there is an exception: if the type width is less than `int`, the result will automatically promote to `int`.

```c
unsigned char a = 66;

if ((-a) < 0) printf("negative\n");
else printf("positive\n");
```

In the example above, the variable `a` is of `unsigned char` type, which cannot be less than 0. However, `-a` is not of `unsigned char` type but is automatically converted to `int`, leading to the output `negative`.

Consider the following example:

```c
unsigned char a = 1;
unsigned char b = 255;
unsigned char c = 255;

if ((a - 5) < 0) do_something();
if ((b + c) > 300) do_something();
```

In the example above, expressions `a - 5` and `b + c` are automatically converted to `int`, so the function `do_something()` is executed twice.

### Functions

Function parameters and return values are automatically converted to the types specified in the function definition.

```c
int dostuff(int, unsigned char);

char m = 42;
unsigned short n = 43;
long long int c = dostuff(m, n);
```

In the example above, parameters `m` and `n` are automatically converted to the types defined in the `dostuff()` function.

Here's an example of automatic type conversion for return values:

```c
char func(void) 
{
  int a = 42;
  return a;
}
```

In this example, even though the internal variable `a` is of type `int`, the return type of the function is `char`, so the value returned is of type `char`.

## Explicit Type Conversion

It is generally advisable to avoid automatic type conversions to prevent unexpected results. C provides explicit type conversion, allowing manual type conversion.

You can convert a value or variable to a specified type by placing the type in parentheses before the value or variable, known as "type casting."

```c
(unsigned char) ch
```

In the example above, the variable `ch` is converted to an unsigned character type.

```c
long int y = (long int) 10 + 12;
```

In this example, `(long int)` explicitly converts `10` to `long int`. This explicit conversion is actually unnecessary here because the assignment operator automatically converts the value on the right side to the type of the left side variable.

## Portable Types

Integer types in C (short, int, long) may have different byte widths on different computers, so the exact number of bytes they occupy is not always known in advance.

Sometimes programmers need to control the exact byte width for better portability. The `<stdint.h>` header file defines several new type aliases.

(1) **Exact-width types**: Guarantee that an integer type has a specific width.

-   `int8_t`: 8-bit signed integer.
-   `int16_t`: 16-bit signed integer.
-   `int32_t`: 32-bit signed integer.
-   `int64_t`: 64-bit signed integer.
-   `uint8_t`: 8-bit unsigned integer.
-   `uint16_t`: 16-bit unsigned integer.
-   `uint32_t`: 32-bit unsigned integer.
-   `uint64_t`: 64-bit unsigned integer.

These are type aliases, and the compiler will map them to underlying types. For example, if `int` is 32 bits on a system, `int32_t` will be mapped to `int`; if `long` is 32 bits, `int32_t` will be mapped to `long`.

Example:

```c
#include <stdio.h>
#include <stdint.h>

int main(void) 
{
  int32_t x32 = 45933945;
  printf("x32 = %d\n", x32);
  return 0;
}
```

In this example, the variable `x32` is declared as `int32_t`, ensuring it is 32 bits wide.

(2) **Minimum-width types**: Ensure an integer type has at least a specified width.

-   `int_least8_t`
-   `int_least16_t`
-   `int_least32_t`
-   `int_least64_t`
-   `uint_least8_t`
-   `uint_least16_t`
-   `uint_least32_t`
-   `uint_least64_t`

These types guarantee a minimum width of bytes. For example, `int_least8_t` represents the smallest type that can hold an 8-bit signed integer.

(3) **Fastest minimum-width types**: Provide the fastest integer calculations for a specified width.

-   `int_fast8_t`
-   `int_fast16_t`
-   `int_fast32_t`
-   `int_fast64_t`
-   `uint_fast8_t`
-   `uint_fast16_t`
-   `uint_fast32_t`
-   `uint_fast64_t`

These types ensure the fastest computation speed while meeting the specified byte width. For example, `int_fast8_t` represents the fastest type for 8-bit signed integer operations. Some machines perform arithmetic operations faster with specific data widths, e.g., 32-bit operations are faster on 32-bit machines.

(4) **Types for storing pointers**:

-   `intptr_t`: Signed integer type capable of storing a pointer (memory address).
-   `uintptr_t`: Unsigned integer type capable of storing a pointer.

(5) **Maximum-width integer types**: Used to store the largest integers.

-   `intmax_t`: Can store any valid signed integer type.
-   `uintmax_t`: Can store any valid unsigned integer type.

These types have a width greater than `long long` and `unsigned long`.

# 7. Pointers

Pointers are one of the most important and also one of the most difficult concepts in C language.

## Introduction

What is a pointer? Firstly, it is a value that represents a memory address, so a pointer is like a signpost pointing to a certain memory address.

The character `*` denotes a pointer and is usually placed after the type keyword, indicating the type of value the pointer points to. For example, `char*` represents a pointer to a character, and `float*` represents a pointer to a `float` type value.

```c
int* intPtr;
```

The above example declares a variable `intPtr`, which is a pointer pointing to an integer stored at a memory address.

The asterisk `*` can be placed anywhere between the variable name and the type keyword; the following notations are all valid.

```c
int   *intPtr;
int * intPtr;
int*  intPtr;
```

This book uses the notation with the asterisk immediately following the type keyword (i.e., `int* intPtr;`) because it reflects that a pointer variable is just a regular variable, except that its value is a memory address.

One thing to note about this notation is that if two pointer variables are declared on the same line, it should be written as follows.

```c
// Correct
int * foo, * bar;

// Incorrect
int* foo, bar;
```

In the above example, the second line's result is that `foo` is an integer pointer variable, while `bar` is an integer variable, meaning `*` only applies to the first variable.

A pointer might point to another pointer, which is indicated by using two asterisks `**`.

```c
int** foo;
```

The above example indicates that the variable `foo` is a pointer pointing to another pointer, and the second pointer points to an integer.

## * Operator

The `*` symbol, besides representing a pointer, can also be used as an operator to retrieve the value at the memory address pointed to by the pointer variable.

```c
void increment(int* p) {
  *p = *p + 1;
}
```

In the above example, the function `increment()` has a parameter that is an integer pointer `p`. Inside the function body, `*p` represents the value pointed to by the pointer `p`. Assigning a value to `*p` changes the value at the memory address pointed to by the pointer.

The function's purpose is to increment the parameter value by `1`. This function does not return a value because the address is passed in, and operations on the value at that address will affect the external value, so no return value is needed. In fact, passing values to the external scope through pointers is a common method in C language.

Passing the address of a variable rather than its value to a function has another advantage. For large variables that require significant storage space, copying the variable value into the function is time-consuming and space-wasting; passing the pointer is more efficient.

## & Operator

The `&` operator is used to retrieve the memory address of a variable.

```c
int x = 1;
printf("x's address is %p\n", &x);
```

In the above example, `x` is an integer variable, and `&x` is the memory address of `x`. The `%p` in `printf()` is a placeholder for memory addresses and can print out the memory address.

The function from the previous section, which adds `1` to the parameter value, can be used as follows.

```c
void increment(int* p) 
{
  *p = *p + 1;
}

int x = 1;
increment(&x);
printf("%d\n", x); // 2
```

In the above example, after calling the `increment()` function, the value of variable `x` is increased by `1` because the function was passed the address `&x`.

The `&` operator and the `*` operator are inverse operations, and the following expression always holds true.

```c
int i = 5;

if (i == *(&i)) // Correct
```

## Pointer Variable Initialization

After declaring a pointer variable, the compiler allocates memory space for the pointer variable itself, but the value in this memory space is random, meaning the pointer variable points to a random value. At this point, you should not read or write the address pointed to by the pointer variable, as the address is random and could lead to serious consequences.

```c
int* p;
*p = 1; // Incorrect
```

The above code is incorrect because the address pointed to by `p` is random, and writing `1` to this random address will result in unexpected outcomes.

The correct approach is to initialize the pointer variable by making it point to an allocated address before reading or writing, which is called pointer variable initialization.

```c
int* p;
int i;

p = &i;
*p = 13;
```

In the above example, `p` is a pointer variable. After declaring this variable, `p` will point to a random memory address. You should point it to an allocated memory address by declaring another integer variable `i`, and the compiler will allocate a memory address for `i`, then make `p` point to `i`'s memory address (`p = &i;`). After initialization, you can assign a value to the address pointed to by `p` (`*p = 13;`).

To avoid reading or writing uninitialized pointer variables, it is a good practice to set uninitialized pointer variables to `NULL`.

```c
int* p = NULL;
```

`NULL` in C language is a constant representing a memory space with address `0`, which is unusable. Reading or writing this address will result in an error.

## Pointer Arithmetic

Pointers are essentially unsigned integers representing memory addresses. They can perform arithmetic operations, but the rules are not the same as integer arithmetic.

#### (1) Pointer and Integer Addition/Subtraction

Arithmetic operations between pointers and integers represent pointer movement.

```c
short* j;
j = (short*)0x1234;
j = j + 1; // 0x1236
```

In the above example, `j` is a pointer pointing to the memory address `0x1234`. Since `0x1234` is of integer type (`int`) and incompatible with `j`'s type (`short*`), we use type casting to convert `0x1234` to `short*`. You might think `j + 1` equals `0x1235`, but the correct answer is `0x1236`. This is because `j + 1` means moving the pointer to a higher memory address by one unit, where one unit for `short` type is two bytes, so it moves up by two bytes. Similarly, `j - 1` results in `0x1232`.

The movement unit of the pointer depends on the data type it points to. The number of bytes occupied by the data type determines how many bytes the pointer moves.

#### (2) Pointer and Pointer Addition

Pointers can only perform addition or subtraction with integer values; adding two pointers is illegal.

```c
unsigned short* j;
unsigned short* k;
x = j + k; // Illegal
```

The above example shows adding two pointers, which is illegal.

#### (3) Pointer and Pointer Subtraction

Subtraction of pointers of the same type is allowed and returns the distance between them, i.e., how many data units they are apart.

Subtracting a higher address from a lower address returns a positive value; subtracting a lower address from a higher address returns a negative value.

The result of subtraction is of type `ptrdiff_t`, which is a signed integer type alias, and its exact type depends on the system. This type is defined in the header file `stddef.h`.

```c
short* j1;
short* j2;

j1 = (short*)0x1234;
j2 = (short*)0x1236;

ptrdiff_t dist = j2 - j1;
printf("%td\n", dist); // 1
```

In the above example, `j1` and `j2` are two pointers to `short` type. The variable `dist` is the distance between them, of type `ptrdiff_t`, and its value is `1` because they are 2 bytes apart, which is exactly the size of a `short` type value.

#### (4) Pointer and Pointer Comparison

Pointer comparison operations compare the memory addresses of the pointers to determine which is greater, returning `1` (true) or `0` (false).

# 8. Functions

## Introduction

A function is a block of code that can be executed repeatedly. It can accept different parameters and perform corresponding operations. The following example is a function.

```c
int plus_one(int n) 
{
  return n + 1;
}
```

The above code declares a function `plus_one()`.

The syntax of function declaration includes the following points to note:

1. **Return Type**: When declaring a function, you first need to specify the return type. In the example, it is `int`, meaning the function `plus_one()` returns an integer.

2. **Parameters**: The parentheses following the function name must declare the types and names of the parameters. `plus_one(int n)` indicates that this function has one integer parameter `n`.

3. **Function Body**: The function body is written inside curly braces, and no semicolon is needed after the closing brace. The starting position of the curly braces can be on the same line as the function name or on a new line. This book uses the same line notation.

4. **`return` Statement**: The `return` statement provides the function's return value. The program exits the function body and ends the function call when it reaches this line. If the function does not return a value, you can omit the `return` statement or write `return;`.

To call a function, simply add parentheses after the function name, placing actual arguments within the parentheses, as shown below.

```c
int a = plus_one(13);
// a equals 14
```

When calling a function, the number of arguments must match the number of parameters defined. Passing too many or too few arguments will cause an error.

```c
int plus_one(int n)
{
  return n + 1;
}

plus_one(2, 2); // Error
plus_one();  // Error
```

In the above example, the function `plus_one()` can only accept one argument, and passing two or zero arguments will cause an error.

Functions must be declared before use, otherwise, it will cause an error. This means you must declare the function before using `plus_one()`. If written like this, it will result in a compilation error.

```c
int a = plus_one(13);

int plus_one(int n)
{
  return n + 1;
}
```

In the above example, declaring the function `plus_one()` after calling it will result in a compilation error.

The C language standard specifies that functions can only be declared at the top level of a source file and cannot be declared inside other functions.

Functions that do not return a value use the `void` keyword to indicate the return type. For functions with no parameters, `void` should also be used to indicate the parameter type.

```c
void myFunc(void) 
{
  // ...
}
```

The above `myFunc()` function has no return value and does not require parameters when called.

Functions can call themselves, which is called recursion. The following is an example of the Fibonacci sequence.

```c
unsigned long Fibonacci(unsigned n) 
{
  if (n > 2)
    return Fibonacci(n - 1) + Fibonacci(n - 2);
  else
    return 1;
}
```

In the above example, the function `Fibonacci()` calls itself, greatly simplifying the algorithm.

## main()

The C language specifies that `main()` is the entry point of the program, meaning every program must include a `main()` function. The program always starts execution from this function, and without it, the program cannot start. Other functions are accessed through it.

The syntax of `main()` is the same as other functions, requiring a return type and parameter types, as shown below.

```c
int main(void) 
{
  printf("Hello World\n");
  return 0;
}
```

In the example above, the final `return 0;` indicates the function ends execution and returns `0`.

In C language conventions, a return value of `0` indicates the function executed successfully. If a non-zero integer is returned, it indicates failure, and there is a problem with the code. The system uses `main()`'s return value as the return value of the entire program to determine if the program ran successfully.

Normally, if `return 0` is omitted from `main()`, the compiler automatically adds it, making the default return value of `main()` `0`. Therefore, writing it as follows has the same effect.

```c
int main(void)
{
  printf("Hello World\n");
}
```

Since C language only adds a default return value for `main()`, and not for other functions, it's recommended to always keep the `return` statement to maintain a consistent coding style.

## Pass-by-Value

If a function's parameter is a variable, what is passed during the call is a copy of the variable's value, not the variable itself.

```c
void increment(int a) 
{
  a++;
}

int i = 10;
increment(i);

printf("%d\n", i); // 10
```

In the example above, after calling `increment(i)`, the variable `i` itself does not change and remains `10`. This is because the function receives a copy of `i`, not `i` itself, and changes to the copy do not affect the original variable. This is called "pass-by-value."

Therefore, if the parameter variable changes, it's best to return it as a result.

```c
int increment(int a) 
{
  a++;
  return a;
}

int i = 10;
i = increment(i);

printf("%d\n", i); // 11
```

In the following example, the `Swap()` function is used to swap two variables' values. Due to pass-by-value, the following code will not work.

```c
void Swap(int x, int y) 
{
  int temp;
  temp = x;
  x = y;
  y = temp;
}

int a = 1;
int b = 2;
Swap(a, b); // Ineffective
```

The above code will not produce a swap of variable values because the variables passed in are copies of the original variables `a` and `b`, and any operations within the function do not affect the original variables.

To pass the actual variables, the only way is to pass the address of the variables.

```c
void Swap(int* x, int* y)
{
  int temp;
  temp = *x;
  *x = *y;
  *y = temp;
}

int a = 1;
int b = 2;
Swap(&a, &b);
```

In the example above, by passing the addresses of variables `x` and `y`, the function can directly manipulate these addresses, thus swapping the values of the two variables.

Although unrelated to parameter passing, it's worth noting that functions should not return pointers to internal variables.

```c
int* f(void) 
{
  int i;
  // ...
  return &i;
}
```

In the example above, returning a pointer to an internal variable `i` is incorrect. When the function finishes running, the internal variable disappears, making the address pointing to `i` invalid. Using this address afterward is very dangerous.

## Function Pointers

A function is essentially a piece of code located in memory, and C language allows functions to be accessed through pointers.

```c
void print(int a) 
{
  printf("%d\n", a);
}

void (*print_ptr)(int) = &print;
```

In the example above, the variable `print_ptr` is a function pointer pointing to the address of the `print()` function. The address of the function `print()` can be obtained using `&print`. Note that `(*print_ptr)` must be enclosed in parentheses; otherwise, the function parameter `(int)` has higher precedence than `*`, making the whole expression `void* print_ptr(int)`. Here's another example:

```c
#include <stdio.h>

int add_2(int i)
{
	return i + 2;
}

// Here we replace the function with a function pointer since a function pointer is the function itself
int (*add_2_ptr)(int) = &add_2;

int main() 
{
	int x = 1;
	printf("%d", (*add_2_ptr)(x));
}
```

With a function pointer, you can also call functions through it.

```c
(*print_ptr)(10);
// Equivalent to
print(10);
```

A special case is that in C, the function name itself is a pointer to the function code. In other words, `print` and `&print` are the same.

```c
if (print == &print) // true
```

Thus, the `print_ptr` is equivalent to `print`.

```c
void (*print_ptr)(int) = &print;
// Or
void (*print_ptr)(int) = print;

if (print_ptr == print) // true
```

So, for any function, there are five ways to call it.

```c
// Way 1
print(10)

// Way 2
(*print)(10)

// Way 3
(&print)(10)

// Way 4
(*print_ptr)(10)

// Way 5
print_ptr(10)
```

For simplicity and readability, typically, the `*` and `&` are omitted before the function name.

One application of this feature is that if a function's parameter or return value is also a function, the function prototype can be written as follows.

```c
int compute(int (*myfunc)(int), int, int);
```

The example above clearly indicates that the first parameter of `compute()` is also a function. A specific application scenario is as follows:

```c
#include <stdio.h>

// Define two simple functions
int add(int a) 
{
    return a + a;
}

int multiply(int a) 
{
    return a * a;
}

// Define the compute function that takes a function pointer and two integers as parameters
int compute(int (*myfunc)(int), int x, int y) 
{
    return myfunc(x) + myfunc(y);
}

int main()
{
    int x = 3, y = 4;

    // Use add function as a parameter
    int result1 = compute(add, x, y);
    std::cout << "Result of compute with add: " << result1 << std::endl; // Outputs 14 (3+3 + 4+4)

    // Use multiply function as a parameter
    int result2 = compute(multiply, x, y);
    std::cout << "Result of compute with multiply: " << result2 << std::endl; // Outputs 25 (3*3 + 4*4)

    return 0;
}
```

-   ## Function Prototypes

    As mentioned earlier, functions must be declared before use. Since the `main()` function is always executed first, all other functions must be declared before `main()`.

    ```c
    void func1(void)
    {
    }
    
    void func2(void)
    {
    }
    
    int main(void) 
    {
      func1();
      func2();
      return 0;
    }
    ```

    In the code above, the `main()` function must be declared last; otherwise, warnings will occur during compilation, indicating that `func1()` or `func2()` declarations are missing.

    However, `main()` is the entry point of the program and contains the main logic, so it is better to place it first. On the other hand, for programs with many functions, ensuring the correct order of each function can become cumbersome.

    C language provides a solution: by providing function prototypes at the beginning of the program, functions can be used before their full declaration. A function prototype is a declaration that informs the compiler of each function's return type and parameter types. Other details and the function body can be added later.

    ```c
    int twice(int);
    
    int main(int num) 
    {
      return twice(num);
    }
    
    int twice(int num) 
    {
      return 2 * num;
    }
    ```

    In the example above, the implementation of the `twice()` function is placed after `main()`, but the function prototype is provided at the top, so it compiles correctly. As long as the function prototype is provided in advance, the specific location of the function implementation does not matter.

    Function prototypes can include parameter names as well, though this is unnecessary for the compiler but may help in understanding the function's intent.

    ```c
    int twice(int);
    
    // Equivalent to
    int twice(int num);
    ```

    In the example above, the parameter name `num` in the `twice` function can be included or omitted in the prototype.

    Note that function prototypes must end with a semicolon.

    Generally, the top of each source file will include prototypes for all functions used in that file.

    ## exit()

    The `exit()` function terminates the entire program. Once this function is executed, the program ends immediately. The prototype of `exit()` is defined in the header file `stdlib.h`.

    `exit()` can return a value to the program's external environment, which is the return value of the program. Typically, two constants are used as its arguments: `EXIT_SUCCESS` (equivalent to 0) indicates successful program execution, and `EXIT_FAILURE` (equivalent to 1) indicates an abnormal termination. These constants are also defined in `stdlib.h`.

    ```c
    // Program runs successfully
    // Equivalent to exit(0);
    exit(EXIT_SUCCESS);
    
    // Program terminates abnormally
    // Equivalent to exit(1);
    exit(EXIT_FAILURE);
    ```

    In the `main()` function, `exit()` is equivalent to using the `return` statement. Using `exit()` in other functions terminates the entire program, with no additional effects.

    C language also provides an `atexit()` function to register additional functions to be executed when `exit()` is called, useful for cleanup tasks when the program exits. This function's prototype is also defined in the header file `<stdlib.h>`.

    ```c
    // Note: The argument must be a pointer to a function with no parameters and no return value!!!
    int atexit(void (*func)(void));
    ```

    The parameter of `atexit()` is a function pointer. Note that the parameter function (e.g., `print` in the example) must not accept parameters or have a return value.

    ```c
    void print(void) 
    {
      printf("something wrong!\n");
    }
    
    atexit(print);
    exit(EXIT_FAILURE);
    ```

    In the example above, when `exit()` is executed, it first calls the `print()` function registered with `atexit()`, then terminates the program. Therefore, `atexit` functions are generally used for cleanup, as shown in the example:

    ```c
    #include <stdio.h>
    #include <stdlib.h>
    
    // Functions to be called when the program terminates
    void cleanup1(void) 
    {
        printf("Cleanup function 1 called.\n");
    }
    
    void cleanup2(void)
    {
        printf("Cleanup function 2 called.\n");
    }
    
    int main() 
    {
        // Register cleanup functions
        if (atexit(cleanup1) != 0) 
        {
            fprintf(stderr, "Unable to register cleanup1\n");
            return 1;
        }
    
        if (atexit(cleanup2) != 0)
        {
            fprintf(stderr, "Unable to register cleanup2\n");
            return 1;
        }
    
        printf("Main function is running.\n");
    
        // Registered cleanup functions will be called in reverse order after the main function ends
        return 0;
    }
    ```

    Note:

    **1. The Purpose of Cleanup Functions:**

    - **Resource Release:** Functions handle the release of resources like memory, file handles, network connections, etc., that were allocated during program execution to prevent resource leaks.
    - **Common Actions:** Includes closing files, freeing memory, disconnecting network connections, flushing buffers, etc.

    **2. Reverse Order of Calls:**

    - **Ensures Proper Resource Release:** The system calls cleanup functions in reverse order to ensure resources are released correctly according to dependencies. For example, dependent resources are released before the resources they depend on, avoiding issues where dependent resources are already released but still in use.

    **3. Registering Cleanup Functions:**

    - **Concept:** Registering cleanup functions means adding them to an internal list, which the system will automatically call when the program ends.
    - **Implementation:** For example, the `atexit` function registers cleanup functions. When the program ends normally, the registered cleanup functions are called in sequence.

## Specifiers

C language provides specifiers to make function usage more explicit.

### extern Specifier

The English translation of `extern`: external; outside;

In multi-file projects, source files may use functions declared in other files. In this case, the current file needs to provide the prototype of the external function and use `extern` to indicate that the function's definition comes from another file.

```c
extern int foo(int arg1, char arg2);

int main(void) 
{
  int a = foo(2, 3);
  // ...
  return 0;
}
```

In the example above, the function `foo()` is defined in another file, and `extern` tells the compiler that the current file does not contain the definition of this function.

However, since function prototypes are `extern` by default, omitting `extern` has the same effect.

The `extern` specifier is not limited to functions. Here’s a detailed explanation:

1. **Variable Usage**

   When declaring a variable in a file, using the `extern` specifier indicates that the variable is defined in another source file, not in the default one. For example:

   ```c
   // file1.c
   int globalVar = 10; // Variable definition

   // file2.c
   extern int globalVar; // Variable declaration
   ```

   In `file1.c`, `globalVar` is defined and memory is allocated for it. In `file2.c`, using the `extern` specifier declares `globalVar`, allowing `file2.c` to access the `globalVar` defined in `file1.c`.

2. **Function Usage**

   When declaring functions, the `extern` specifier is usually implicit, so it can be omitted. For example:

   ```c
   // file1.c
   void myFunction(); // Function declaration, default is extern

   // file2.c
   extern void myFunction(); // Function declaration
   ```

   In `file1.c`, `myFunction` is defined, and in `file2.c`, `extern` is used to declare `myFunction`, indicating it is defined in another file.

3. **Resolving Naming Conflicts, Comparison with C++**

   C++ uses namespaces to avoid naming conflicts, for example:

   ```cpp
   // file1.cpp
   namespace MyNamespace 
   {
       int myVar = 10;
   }
   
   // file2.cpp
   namespace MyNamespace
   {
       void myFunction() 
       {
           // Implementation
       }
   }
   ```

   Both C and C++ can use the `static` keyword to define variables or functions that are visible only within the current source file, thus avoiding global naming conflicts. For example:

   ```c
   // file1.c
   static int myVar = 10;
   
   static void myFunction()
   {
       // Implementation
   }
   
   // file2.c
   static int myVar = 20;  // No conflict with myVar in file1.c
   ```

### `static` Specifier

By default, every time a function is called, its internal variables are reinitialized and do not retain the values from the previous call. The `static` specifier can alter this behavior.

When `static` is used to declare a variable inside a function, it means that the variable only needs to be initialized once and does not need to be reinitialized on each call. In other words, its value remains unchanged between calls.

```c
#include <stdio.h>

void counter(void) 
{
  static int count = 1;  // Initialized only once
  printf("%d\n", count);
  count++;
}

int main(void) 
{
  counter();  // 1
  counter();  // 2
  counter();  // 3
  counter();  // 4
}
```

In the example above, the internal variable `count` of the function `counter()` is modified with the `static` specifier, indicating that this variable is initialized only once. Each subsequent call uses the previous value, resulting in an incrementing effect.

Note that a `static` variable can only be initialized with a constant, not with another variable.

```c
int i = 3;
static int j = i; // Error
```

In the example above, `j`, being a static variable, cannot be initialized with another variable `i`.

Also, in block scope, variables declared with `static` have a default value of `0`.

```c
static int foo;
// Equivalent to
static int foo = 0;
```

`static` can also be used to modify the function itself.

```c
static int Twice(int num) 
{
  int result = num * 2;
  return(result);
}
```

In the example above, the `static` keyword indicates that the function can only be used within the current file. Without this keyword, other files could also use this function (by declaring its prototype).

`static` can also be used in parameters to modify array parameters.

```c
int sum_array(int a[static 3], int n) 
{
  // ...
}
```

In the example above, `static` does not affect the program's behavior but informs the compiler that the array's length is at least 3, which can improve performance in some cases. Note that for multidimensional arrays, `static` can only be used for the first dimension.

**Emphasis:**

The semantics of `static` in C and C++ are different:

In C, `static` is used for variables that are assigned only once and are visible only within the current file, and for functions that are only visible within the current file.

In C++, `static` is used for class-level shared variables that are assigned only once; for functions, it represents a class-wide feature, belonging to the class rather than instances of the class. It can be called through both the class and instances, though the latter is not recommended.

### `const` Specifier

The `const` specifier in function parameters indicates that the function must not modify the parameter variable.

```c
void f(int* p) 
{
  // ...
}
```

In the example above, the parameter of function `f()` is a pointer `p`, and the function might change the value `*p` it points to, affecting the external value.

To avoid this, you can add the `const` specifier before the pointer parameter in the function declaration, informing the compiler that the function cannot modify the value pointed to by the parameter.

```c
void f(const int* p) 
{
  *p = 0; // Error
}
```

In this example, the `const` specifies that the pointer `p` cannot modify the value it points to, so `*p = 0` results in an error.

However, this restricts only the modification of `*p`, and the address of `p` itself can be changed.

```c
void f(const int* p) 
{
  int x = 13;
  p = &x; // Allowed
}
```

In this example, the address `p` itself can be modified, and `const` only restricts the modification of `*p`.

To restrict the modification of both `p` and `*p`, you need to use two `const` specifiers.

```c
void f(const int* const p) 
{
  // ...
}
```

## Variable Arguments

Some functions have a variable number of arguments. When declaring such functions, you can use ellipses `...` to indicate a variable number of arguments.

```c
// The following printf() is the most illustrative example of this.
int printf(const char* format, ...);
```

In the example above, the prototype of the `printf()` function shows that, besides the first parameter, the number of other parameters is variable, depending on the number of placeholders in the format string. The `...` indicates a variable number of arguments.

Note that the `...` symbol must be placed at the end of the parameter list; otherwise, it will result in an error.

The header file `<stdarg.h>` defines some macros to handle variable arguments.

- `va_list`: A data type used to define a variable argument object. It must be used first when handling variable arguments.
- `va_start`: A function used to initialize the variable argument object. It takes two parameters: the first is the variable argument object, and the second is the parameter before the variable arguments in the original function, used to locate the variable arguments.
- `va_arg`: A function used to retrieve the current variable argument. Each call advances the internal pointer to the next variable argument. It takes two parameters: the first is the variable argument object, and the second is the type of the current variable argument.
- `va_end`: A function used to clean up the variable argument object.

Here is an example:

```c
double average(int i, ...) 
{
  double total = 0;
  va_list ap;
  va_start(ap, i);
  for (int j = 1; j <= i; ++j) 
  {
    total += va_arg(ap, double);
  }
  va_end(ap);
  return total / i;
}
```

In the example above, `va_list ap` defines `ap` as a variable argument object. `va_start(ap, i)` places the arguments after `i` into `ap`, `va_arg(ap, double)` retrieves one argument from `ap` and specifies it as a `double` type, and `va_end(ap)` cleans up the variable argument object. Here's a small usage example:

```c
#include <stdio.h>
#include <stdarg.h>

double average(int i, int j, ...);

int main(void)
{
	// Automatically converts int to double
	double a = 1;
	printf("auto: %f\n", a);											// auto: 1.000000

	// Does not automatically convert int to double
	printf("average: %f\n", average(2, 3, 1, 2, 1, 2, 3));				// average: 0.000000
	printf("average: %f\n", average(2, 3, 1.0, 2.0, 1.0, 2.0, 3.0));	// average: 3.500000

	/* Type Specification: In va_arg(args, int) and va_arg(args, double),
	   the second parameter (int and double) is the type specification, informing the compiler of the type of the current argument being retrieved.
	   This is necessary because va_list does not save type information. */
	/* Type Matching: You must ensure that the type used with va_arg matches the actual type of the arguments. Mismatches can lead to undefined behavior or incorrect data. */
	/* Order of Variable Arguments: Since va_list extracts arguments in order, you need to know the types and order of the arguments to use va_arg correctly. */
	
	return 0;
}

double average(int i, int j, ...)
{
	double total_1 = 0;
	double total_2 = 0;
	va_list args;
	va_start(args, j);

	for(int k = 1; k <= i; k++)
	{
		double val = va_arg(args, double);
		total_1 += val;
	}

	for(int k = 1; k <= j; k++)
	{
		total_2 += va_arg(args, double);
	}
    
	va_end(args);

	return (total_1 / i) + (total_2 / j);
}
```

# 9. Arrays

## Introduction

An array is a collection of values of the same type stored sequentially. Arrays are represented with the variable name followed by square brackets, where the number inside the brackets indicates the size of the array.

```c
int scores[100];
```

The example above declares an array `scores` with 100 elements, each of type `int`.

Note that when declaring an array, you must specify its size.

Array elements are indexed starting from `0`, so an array `scores[100]` has elements ranging from index 0 to 99, with the last element having an index that is one less than the array length.

You can access an element by using the index inside square brackets. You can also use this method to assign values.

```c
scores[0] = 13;
scores[99] = 42;
```

In the example above, values are assigned to the first and last positions of the `scores` array.

Note that referencing a non-existent array element (i.e., out-of-bounds access) does not result in an error, so you must be very careful.

```c
int scores[100];

scores[100] = 51;
```

In the example above, the array `scores` only has 100 elements, so the position `scores[100]` does not exist. However, referencing this position does not produce an error; it will run normally and assign a value to the memory area following `scores`, which actually belongs to other variables, leading to unintended modifications of other variables. This can easily cause errors and be difficult to detect.

Arrays can also be initialized using curly braces, assigning values to each element at declaration.

```c
int a[5] = {22, 37, 3490, 18, 95};
```

Note that when using curly braces to initialize an array, the values must be provided at the time of declaration, or it will cause a compilation error.

```c
int a[5];
a = {22, 37, 3490, 18, 95}; // Error
```

In the code above, initializing array `a` with curly braces after declaration causes an error.

The reason for the error is that in C, once an array variable is declared, its address cannot be modified. For the same reason, re-initializing an array with curly braces after assignment is also not allowed.

```c
int a[5] = {1, 2, 3, 4, 5};
a = {22, 37, 3490, 18, 95}; // Error
```

In the code above, re-assigning values to the `a` array using curly braces after initial assignment is not allowed.

When using curly braces for initialization, the number of values cannot exceed the array length, or it will result in a compilation error.

If the number of values in the curly braces is less than the number of elements in the array, the unassigned elements are automatically initialized to `0`.

```c
int a[5] = {22, 37, 3490};
// Equivalent to
int a[5] = {22, 37, 3490, 0, 0};
```

To set every element of an array to zero, the simplest way is as follows.

```c
int a[100] = {0};
```

During initialization, specific positions in the array can be assigned values.

```c
int a[15] = {[2] = 29, [9] = 7, [14] = 48};
```

In the example above, positions 2, 9, and 14 in the array are assigned values, while other positions are automatically set to `0`.

Assignments to specific positions can be made in any order, and the following is equivalent to the previous example.

```c
int a[15] = {[9] = 7, [14] = 48, [2] = 29};
```

Assignments to specific positions can be combined with sequential assignments.

```c
int a[15] = {1, [5] = 10, 11, [10] = 20, 21}
```

In the example above, positions 0, 5, 6, 10, and 11 are assigned values.

C allows omitting the number inside square brackets when declaring an array. In this case, the length of the array is automatically determined by the number of values inside the curly braces.

```c
int a[] = {22, 37, 3490};
// Equivalent to
int a[3] = {22, 37, 3490};
```

In the example above, the length of the array `a` is determined to be `3` based on the number of values in the curly braces.

When omitting the size and using specific position assignments, the array length will be the largest specified position plus one.

```c
int a[] = {[2] = 6, [9] = 12};
```

In the example above, the maximum specified position is `9`, so the length of the array is `10`.

## Array Length

The `sizeof` operator returns the size of the entire array in bytes.

```c
int a[] = {22, 37, 3490};
int arrLen = sizeof(a); // 12
```

In the example above, `sizeof` returns the byte size of the array `a`, which is `12`.

Since all elements in the array are of the same type and each element has the same byte size, you can determine the number of elements in the array by dividing the total byte size of the array by the byte size of one element.

```c
sizeof(a) / sizeof(a[0])
```

In the example above, `sizeof(a)` is the byte size of the entire array, and `sizeof(a[0])` is the byte size of one array element. Dividing these gives the number of elements in the array.

Note that the return type of `sizeof` is `size_t`, so the result of `sizeof(a) / sizeof(a[0])` is also of type `size_t`. In `printf()`, you should use the format specifier `%zd` or `%zu`.

```c
int x[12];

printf("%zu\n", sizeof(x));     // 48
printf("%zu\n", sizeof(int));   // 4
printf("%zu\n", sizeof(x) / sizeof(int)); // 12
```

In the example above, `sizeof(x) / sizeof(int)` gives the number of elements in the array, which is `12`.

## Multidimensional Arrays

C allows you to declare arrays with multiple dimensions. For each dimension, you use an additional pair of square brackets. For example, a two-dimensional array uses two pairs of square brackets.

```c
int board[10][10];
```

The example above declares a two-dimensional array with 10 elements in each dimension. This means the array has 100 elements in total (10 x 10).

A three-dimensional array is declared with three pairs of square brackets, and so on.

```c
int c[4][5][6];
```

When accessing elements of a two-dimensional array, you need to use two pairs of square brackets, specifying both dimensions.

```c
board[0][0] = 13;
board[9][9] = 13;
```

Note that `board[0][0]` cannot be written as `board[0, 0]`, because `0, 0` is a comma expression that evaluates to the second value, so `board[0, 0]` is equivalent to `board[0]`.

Just like with one-dimensional arrays, indexing for each dimension in a multidimensional array starts at `0`.

Multidimensional arrays can also be initialized using curly braces, assigning values to all elements at once.

```c
int a[2][5] = 
{
  {0, 1, 2, 3, 4},
  {5, 6, 7, 8, 9}
};
```

In the example above, `a` is a two-dimensional array. This initialization method assigns values to each element in the first dimension as an array. You don't need to assign values to every element; missing values are automatically set to `0`.

Multidimensional arrays can also be initialized with specified positions.

```c
int a[2][2] = {[0][0] = 1, [1][1] = 2};
```

In the example above, only the values at `[0][0]` and `[1][1]` are specified, with other positions automatically set to `0`.

Regardless of the number of dimensions, arrays are stored linearly in memory. For example, `a[0][0]` is followed by `a[0][1]`, and `a[0][1]` is followed by `a[1][0]`, and so on. Therefore, you can also use single-layer curly braces for initialization, and the following is equivalent to the previous initialization:

```c
int a[2][2] = {1, 0, 0, 2};
```

## Variable-Length Arrays (VLAs)

In C, arrays can be declared with a length determined at runtime rather than compile-time. This is known as a variable-length array (VLA).

```c
int n = x + y;
int arr[n];
```

In the example above, `arr` is a variable-length array because its size is determined by the value of the variable `n`, which is only known at runtime.

The key characteristic of a variable-length array is that its size can only be determined at runtime. This feature allows programmers to allocate an array with an exact length based on runtime values, avoiding the need to estimate and set a fixed size during development.

Any array whose size is determined at runtime is considered a variable-length array.

```c
int i = 10;

int a1[i];
int a2[i + 5];
int a3[i + k];
```

In the example above, the lengths of `a1`, `a2`, and `a3` are determined during program execution, making them variable-length arrays.

Variable-length arrays can also be used for multidimensional arrays.

```c
int m = 4;
int n = 5;
int c[m][n];
```

In the example above, `c[m][n]` is a two-dimensional variable-length array.

## Array Addresses

Arrays in C are a sequence of contiguous values of the same type. By obtaining the starting address (the address of the first element), you can calculate the addresses of other elements. Here’s an example:

```c
int a[5] = {11, 22, 33, 44, 55};
int* p;

p = &a[0];

printf("%d\n", *p);  // Prints "11"
```

In the example above, `&a[0]` is the address of the first element of the array `a`, and it also serves as the starting address of the entire array. Conversely, from this address (`*p`), you can obtain the value of the first element, which is `11`.

Since getting the starting address of an array is a common operation, the syntax `&array[0]` can be a bit cumbersome. C provides a convenient shorthand where the array name itself represents this starting address. Thus, the array name is essentially a pointer to the first element (`array[0]`).

```c
int a[5] = {11, 22, 33, 44, 55};

int* p = &a[0];
// Equivalent to
int* p = a;
```

In this example, `&a[0]` and the array name `a` are equivalent.

Therefore, if you pass an array name to a function, it is equivalent to passing a pointer variable. Inside the function, you can use this pointer to access the entire array.

Function prototypes for arrays can be written as follows:

```c
// Version one
int sum(int arr[], int len);
// Version two
int sum(int* arr, int len);
```

In these examples, passing an integer array is the same as passing an integer pointer. The array syntax `[]` and pointer syntax `*` are interchangeable. Here’s an example of summing array elements using a pointer:

```c
int sum(int* arr, int len) 
{
  int i;
  int total = 0;

  // Assuming the array has 10 elements
  for (i = 0; i < len; i++) 
  {
    total += arr[i];
  }
  return total;
}
```

In this example, a pointer `arr` (which is also the array name) and the array length are passed to the function. The function uses the pointer to access each element of the array and sum them.

The `*` and `&` operators can also be used with multidimensional arrays.

```c
int a[4][2];

// Access the value of a[0][0]
*(a[0]);
// Equivalent to
**a
```

In this example, since `a[0]` is itself a pointer pointing to the first element of the second dimension (`a[0][0]`), `*(a[0])` retrieves the value of `a[0][0]`. `**a` is essentially performing two dereferences: the first dereference gets `a[0]`, and the second dereference gets `a[0][0]`. Similarly, `&a[0][0]` is equivalent to `*a`.

**Note**: The address to which an array name points cannot be changed. When declaring an array, the compiler automatically allocates a memory address for the array, which is bound to the array name and cannot be altered. Therefore, the following code will result in an error:

```c
int ints[100];
ints = NULL; // Error
```

In this example, reassigning a value to the array name changes the original memory address, which results in an error.

This also means that you cannot assign one array name to another:

```c
int a[5] = {1, 2, 3, 4, 5};

// Version one
int b[5] = a; // Error

// Version two
int b[5];
b = a; // Error
```

Both methods attempt to change the address of the array `b`, which is not allowed and results in an error.

## Array Pointer Arithmetic

In C, you can perform addition and subtraction operations on array pointers, which correspond to moving between elements in the array. For example, `a + 1` returns the address of the next element, and `a - 1` returns the address of the previous element.

```c
int a[5] = {11, 22, 33, 44, 55};

for (int i = 0; i < 5; i++) 
{
  printf("%d\n", *(a + i));
}
```

In the example above, traversing the array using pointer arithmetic, `a + i` points to the address of the `i`-th element in each iteration, and `*(a + i)` retrieves the value at that address, which is equivalent to `a[i]`. For the first element, `*(a + 0)` (or `*a`) is equivalent to `a[0]`.

Since the array name is equivalent to a pointer to the first element, the following equality always holds:

```c
a[b] == *(a + b)
```

Here, `a[b]` and `*(a + b)` are two ways to access an array element.

If a pointer variable `p` points to an element of an array, `p++` is equivalent to pointing to the next element. This method is commonly used to traverse an array.

```c
int a[] = {11, 22, 33, 44, 55, 999};

int* p = a;

while (*p != 999) 
{
  printf("%d\n", *p);
  p++;
}
```

In the example above, `p++` moves the pointer `p` to the next element.

**Note**: The address pointed to by an array name cannot be changed, so you cannot increment the array name itself, such as `a++`. Instead, you must assign the address of the array to a pointer variable `p` and then increment `p`.

Array traversal can generally be done by comparing the length of the array, but it can also be done by comparing the starting and ending addresses of the array.

```c
int sum(int* start, int* end) 
{
  int total = 0;

  // The reason for < instead of <= is that end points to arr + 5
  while (start < end) 
  {
    total += *start;
    start++;
  }

  return total;
}

int arr[5] = {20, 10, 5, 39, 4};
printf("%i\n", sum(arr, arr + 5));
```

In this example, `arr` is the starting address, and `arr + 5` is the ending address. As long as the starting address is less than the ending address, it indicates that the end of the array has not been reached.

Conversely, you can determine the number of elements between two addresses by subtracting them. Here’s an example of how to implement a function that calculates the length of an array.

```c
int arr[5] = {20, 10, 5, 39, 88};
int* p = arr;

while (*p != 88)
  p++;

printf("%i\n", p - arr); // 4
```

In this example, subtracting the starting address of the array from the address of a particular element gives the number of elements between them.

For multidimensional arrays, pointer arithmetic has different meanings depending on the dimension.

```c
int arr[4][2];

// Pointer to arr[1]
arr + 1;

// Pointer to arr[0][1]
arr[0] + 1;
```

In this example, `arr` is a two-dimensional array. `arr + 1` moves the pointer to the next element of the first dimension, which is `arr[1]`. Since each element of the first dimension is itself an array, `arr[0] + 1` moves the pointer to the next element of the second dimension, which is `arr[0][1]`.

When subtracting pointers to different elements within the same array, the result is the number of elements between them.

```c
int* p = &a[5];
int* q = &a[1];

printf("%d\n", p - q); // 4
printf("%d\n", q - p); // -4
```

In this example, the pointers `p` and `q` point to the 5th and 1st positions of the array, respectively. The result of `p - q` is 4, and `q - p` is -4.

## Array Copy

Since the array name is a pointer, copying an array cannot be simply done by copying the array name.

```c
int* a;
int b[3] = {1, 2, 3};

a = b;
```

In the above code, the result is not copying the array `b` to `a`, but making `a` and `b` point to the same array.

The simplest way to copy an array is still using a loop to copy each element of the array one by one.

```c
for (i = 0; i < N; i++)
  a[i] = b[i];
```

In the above example, the array `b` is copied to array `a` by copying each element one by one.

Another method is to use the `memcpy()` function (defined in the header file `string.h`), which directly copies the memory segment of the array.

```c
memcpy(a, b, sizeof(b));
```

In the above example, the memory segment of array `b` is copied to array `a`. This method is faster than copying array elements one by one.

## As Function Parameters

### Declaring Array Parameters

When an array is used as a function parameter, both the array name and the array length are usually passed.

```c
int sum_array(int a[], int n) 
{
  // ...
}

int a[] = {3, 5, 7, 3};
int sum = sum_array(a, 4);
```

In the above example, the first parameter of the function `sum_array()` is the array itself, which is the array name, and the second parameter is the array length.

Since the array name is essentially a pointer, if only the array name is passed, the function only knows the starting address of the array and not the ending address, which is why the array length also needs to be passed.

If the function parameter is a multidimensional array, in addition to passing the length of the first dimension as a parameter to the function, the lengths of other dimensions need to be written in the function definition.

```c
int sum_array(int a[][4], int n) 
{
  // ...
}

int a[2][4] = 
{
  {1, 2, 3, 4},
  {8, 9, 10, 11}
};
int sum = sum_array(a, 2);
```

In the above example, the parameter of the function `sum_array()` is a two-dimensional array. The first parameter is the array itself (`a[][4]`), and the length of the first dimension can be omitted because it will be passed as the second parameter, but the length of the second dimension `4` must be specified.

This is because what the function receives is only the starting address `a` of the array and the number of elements in the first dimension `2`. To correctly calculate the end address of the array, the byte length of each member in the first dimension must be known. By writing it as `int a[][4]`, the compiler knows that each member of the first dimension is also an array containing 4 integers, so the byte length of each member is `4 * sizeof(int)`.

### Variable-Length Arrays as Parameters

When using variable-length arrays as function parameters, the syntax is slightly different.

```c
int sum_array(int n, int a[n]) 
{
  // ...
}

int a[] = {3, 5, 7, 3};
int sum = sum_array(4, a);
```

In the above example, the array `a[n]` is a variable-length array whose length depends on the value of `n`, which is only known at runtime. Therefore, when passing the variable `n` as a parameter, it must come before the variable-length array so that the length of `a[n]` can be determined at runtime; otherwise, it will result in an error.

Since the function prototype can omit the parameter names, the variable-length array prototype can use `*` to replace the variable name or omit the variable name altogether.

```c
int sum_array(int, int [*]);
int sum_array(int, int []);
```

Both of these variable-length function prototypes are valid.

A benefit of using variable-length arrays as function parameters is that the dimensions of multidimensional arrays can have their later dimensions omitted.

```c
// Original syntax
int sum_array(int a[][4], int n);

// Variable-length array syntax
int sum_array(int n, int m, int a[n][m]);
```

In the above example, the function `sum_array()` has a multidimensional array parameter. In the original syntax, the length of the second dimension must be declared. However, using the variable-length array syntax, the length of the second dimension does not need to be declared because it can be passed as a parameter.

### Array Literals as Parameters

C allows array literals to be passed as function parameters.

```c
// Array variable as parameter
int a[] = {2, 3, 4, 5};
int sum = sum_array(a, 4);

// Array literal as parameter
int sum = sum_array((int []){2, 3, 4, 5}, 4);
```

In the above example, both approaches are equivalent. The second approach omits the array variable declaration and directly passes the array literal to the function. `{2, 3, 4, 5}` is an array literal, and `(int [])` acts like a type cast, instructing the compiler on how to interpret these values.

# 10. Strings

## Introduction

In C, there is no separate string type; strings are treated as character arrays, i.e., arrays of type `char`. For example, the string "Hello" is treated as the array `{'H', 'e', 'l', 'l', 'o'}`.

The compiler allocates a contiguous block of memory for the array, with all characters stored in adjacent memory units. At the end of the string, C automatically adds a byte filled with binary `0`, written as the `\0` character, to indicate the end of the string. The character `\0` is different from the character `0`; the former has an ASCII code of 0 (binary `00000000`), while the latter has an ASCII code of 48 (binary `00110000`). Thus, the string "Hello" is actually stored as the array `{'H', 'e', 'l', 'l', 'o', '\0'}`.

All strings end with the character `\0`. This approach allows C to read strings from memory without knowing their length; as soon as a `\0` character is encountered, the end of the string is recognized.

```c
char localString[10];
```

The above example declares a character array with 10 elements, which can be used as a string. Since one position must be reserved for `\0`, it can hold at most a 9-character string.

Writing strings as arrays is cumbersome. C provides a shorthand where characters within double quotes are automatically treated as a character array.

```c
{'H', 'e', 'l', 'l', 'o', '\0'}

// Equivalent to
"Hello"
```

The two string notations are equivalent, and the internal storage method is the same. For strings inside double quotes, you do not need to add the terminating `\0`; C will add it automatically.

Note that double quotes represent strings, while single quotes represent characters. They cannot be interchanged. If `Hello` is placed inside single quotes, the compiler will generate an error.

```c
// Error
'Hello'
```

On the other hand, even if a double-quoted string contains only one character (e.g., `"a"`), it is still treated as a string (stored as 2 bytes) rather than the character `'a'` (stored as 1 byte).

If a string contains double quotes, they need to be escaped with a backslash.

```c
"She replied, \"It does.\""
```

The backslash can also represent other special characters, such as newline (`\n`), tab (`\t`), etc.

```c
"Hello, world!\n"
```

If a string is too long, you can split it across multiple lines by ending a line with a backslash (`\`).

```c
"hello \
world"
```

In the above example, the backslash at the end of the first line splits the string into two lines.

This method has a drawback: the second line must start at the beginning of the line. If you want to include indentation, it will be included in the string. To solve this, C allows concatenation of multiple string literals, as long as there is no space or only spaces between them; C will automatically concatenate them.

```c
char greeting[50] = "Hello, ""how are you ""today!";
// Equivalent to
char greeting[50] = "Hello, how are you today!";
```

This new notation supports multi-line string concatenation.

```c
char greeting[50] = "Hello, "
  "how are you "
  "today!";
```

`printf()` uses the placeholder `%s` to output strings.

```c
printf("%s\n", "hello world")
```

## String Variable Declarations

String variables can be declared as a character array or as a pointer to a character array.

```c
// Method 1
char s[14] = "Hello, world!";

// Method 2
char* s = "Hello, world!";
```

Both methods declare a string variable `s`. With the first method, the length of the character array can be omitted as the compiler can determine it automatically.

```c
char s[] = "Hello, world!";
```

In this example, the compiler sets the length of the array `s` to 14, which exactly fits the string.

The length of the character array can be greater than the actual length of the string.

```c
char s[50] = "hello";
```

In this example, the character array `s` has a length of 50, but the actual length of the string "hello" is only 6 (including the terminating `\0`), so the remaining 44 positions are initialized to `\0`.

The length of the character array cannot be less than the actual length of the string.

```c
char s[5] = "hello";
```

In this example, the array `s` has a length of 5, which is less than the actual length of the string "hello" (6). This will result in a compiler error because only the first 5 characters are written, omitting the terminating `\0`, which can lead to errors in subsequent string-related code.

Character pointers and character arrays are mostly equivalent in declaring string variables, but there are two differences.

The first difference is that a string pointed to by a pointer is treated as a constant in C, and the string itself cannot be modified.

```c
char* s = "Hello, world!";
s[0] = 'z'; // Error
```

The code above declares a string variable with a pointer and then attempts to modify the first character of the string. This is incorrect and may lead to unpredictable results or errors at runtime.

If a string variable is declared as an array, there is no such issue, and any element of the array can be modified.

```c
char s[] = "Hello, world!";
s[0] = 'z';
```

Why can't a string declared as a pointer be modified, while one declared as an array can? The reason is that the system stores string literals in a read-only section of memory, which cannot be modified by users. When declared as a pointer, the pointer variable holds an address pointing to this read-only section, so modifications are not allowed. However, when declared as an array, the compiler allocates a separate block of memory for the array, where the string literal is interpreted as a character array and written into this writable memory.

To remind users that a string declared as a pointer should not be modified, you can use the `const` qualifier in the declaration to ensure the string is read-only.

```c
const char* s = "Hello, world!";
```

In the example above, using the `const` qualifier ensures that the string cannot be modified, and the compiler will generate an error if modification is attempted.

The second difference is that a pointer variable can point to another string.

```c
char* s = "hello";
s = "world";
```

In this example, the character pointer can point to another string.

However, a character array variable cannot point to another string.

```c
char s[] = "hello";
s = "world"; // Error
```

In this example, the character array's name always points to the address of the initialized string and cannot be changed.

For the same reason, a character array cannot be directly assigned a new string.

```c
char s[10];
s = "abc"; // Error
```

In this example, you cannot directly assign a new string to a character array variable. The reason is that the variable name for the character array is bound to the address allocated for it, and this binding cannot be changed. C specifies that array variables are non-modifiable lvalues, meaning they cannot be reassigned using the assignment operator.

To reassign, you must use the `strcpy()` function provided by C to copy the string.

```c
char s[10];
strcpy(s, "abc");
```

In this example, the `strcpy()` function copies the string `abc` to the variable `s`. This function's detailed usage will be introduced later.

## strlen()

The `strlen()` function returns the byte length of a string, excluding the terminating null character `\0`. Its prototype is as follows:

```c
// string.h
size_t strlen(const char* s);
```

Its parameter is a string variable, and it returns an unsigned integer of type `size_t`. Generally, it can be treated as an `int` type, unless dealing with extremely long strings. Here is an example of usage:

```c
char* str = "hello";
int len = strlen(str); // 5
```

The prototype of `strlen()` is defined in the standard library header file `string.h`. You need to include `string.h` when using it.

```c
#include <stdio.h>
#include <string.h>

int main(void) 
{
  char* s = "Hello, world!";
  printf("The string is %zd characters long.\n", strlen(s));
}
```

Note that string length (`strlen()`) and string variable length (`sizeof()`) are two different concepts.

```c
char s[50] = "hello";
printf("%d\n", strlen(s));  // 5
printf("%d\n", sizeof(s));  // 50
```

In the example above, the string length is 5, and the string variable length is 50.

If you don't use this function, you can compute the string length yourself by checking for the ending `\0`.

```c
int my_strlen(char *s) 
{
  int count = 0;
  while (s[count] != '\0')
    count++;
  return count;
}
```

## strcpy()

String copying cannot use the assignment operator to directly assign one string to a character array variable.

```c
char str1[10];
char str2[10];

str1 = "abc"; // Error
str2 = str1;  // Error
```

Both methods above are incorrect because array variable names are fixed addresses and cannot be changed to point to another address.

For character pointers, the assignment operator (`=`) only copies the address of one pointer to another pointer, not the string itself.

```c
char* s1;
char* s2;

s1 = "abc";
s2 = s1;
```

The code above works, and the result is that both pointer variables `s1` and `s2` point to the same string, rather than copying the content of string `s1` to `s2`.

The C language provides the `strcpy()` function to copy the contents of one string to another, essentially performing a string assignment. Its prototype is defined in the `string.h` header file.

```c
strcpy(char dest[], const char source[])
```

`strcpy()` takes two parameters: the first parameter is the destination string array, and the second parameter is the source string array. Before copying the string, you must ensure that the length of the first parameter is not smaller than the second parameter; otherwise, although there won't be an error, it will overflow the boundary of the first string variable, causing unpredictable results. The `const` qualifier for the second parameter indicates that this function will not modify the second string.

```c
#include <stdio.h>
#include <string.h>

int main(void) 
{
  char s[] = "Hello, world!";
  char t[100];

  strcpy(t, s);

  t[0] = 'z';
  printf("%s\n", s);  // "Hello, world!"
  printf("%s\n", t);  // "zello, world!"
}
```

In the example above, the value of variable `s` is copied to variable `t`, resulting in two different strings. Modifying one will not affect the other. Additionally, the length of variable `t` is greater than `s`, and the extra positions (after the null terminator `\0`) are filled with random values.

`strcpy()` can also be used for character array assignment.

```c
char str[10];
strcpy(str, "abcd");
```

In the example above, the character array variable is assigned the string "abcd".

The return value of `strcpy()` is a string pointer (i.e., `char*`) pointing to the first parameter.

```c
char* s1 = "beast";
char s2[40] = "Be the best that you can be.";
char* ps;

ps = strcpy(s2 + 7, s1);

puts(s2); // Be the beast
puts(ps); // beast
```

In the example above, the string `beast` is copied starting from position 7 of `s2`, leaving the preceding content unchanged. This results in truncating the content after `beast` because the null character is copied as well. `strcpy()` returns a pointer to the start of the copy.

Another use of `strcpy()` return value is for assigning multiple character arrays consecutively.

```c
strcpy(str1, strcpy(str2, "abcd"));
```

The example above calls `strcpy()` twice to assign two string variables.

Additionally, the first parameter of `strcpy()` is best declared as an already declared array, not an uninitialized character pointer.

```c
char* str;
strcpy(str, "hello world"); // Error
```

The above code has issues. `strcpy()` assigns a string to pointer variable `str`, but `str` is not initialized and points to a random location, so the string may be copied to an arbitrary place.

If not using `strcpy()`, you can implement string copying yourself using the following code.

```c
char* strcpy(char* dest, const char* source) 
{
  char* ptr = dest;
  while (*dest++ = *source++);
  return ptr;
}

int main(void) 
{
  char str[25];
  strcpy(str, "hello world");
  printf("%s\n", str);
  return 0;
}
```

In the code above, the key line is `while (*dest++ = *source++)`, which is a loop that sequentially assigns each character of `source` to `dest` and then moves to the next position until encountering `\0`, at which point the loop exits. Here, the expression `*dest++` is equivalent to `*(dest++)`, meaning it returns the address `dest` first, then increments it to move to the next position, and `*dest` assigns to the current position.

The `strcpy()` function has security risks because it does not check if the destination string length is sufficient to hold the copy of the source string, potentially leading to buffer overflow. If you cannot guarantee no overflow, consider using the `strncpy()` function instead.

## strncpy()

`strncpy()` is used exactly like `strcpy()`, but with an additional third parameter to specify the maximum number of characters to copy, preventing overflow of the destination string variable.

```c
char* strncpy(char* dest, 
  			  char* src, 
  			  size_t n
			  );
```

In the prototype above, the third parameter `n` defines the maximum number of characters to copy. If the maximum number is reached and the source string is not fully copied, copying will stop, and the destination string will not have a terminating `\0`. This must be noted. If the source string has fewer characters than `n`, `strncpy()` behaves exactly like `strcpy()`.

```c
strncpy(str1, str2, sizeof(str1) - 1);
str1[sizeof(str1) - 1] = '\0';
```

In the example above, `str2` is copied to `str1`, but the copy length is at most `str1`'s length minus 1. The last position of `str1` is used to write the string's ending marker `\0`. This is because `strncpy()` does not add `\0` automatically; if the copied segment does not include the end marker, it needs to be added manually.

`strncpy()` can also be used to copy a portion of a string.

```c
char s1[40];
char s2[12] = "hello world";

strncpy(s1, s2, 5);
s1[5] = '\0';

printf("%s\n", s1); // hello
```

In the example above, only the first 5 characters are copied.

## strcat()

The `strcat()` function is used to concatenate strings. It takes two strings as parameters and appends a copy of the second string to the end of the first string. This function modifies the first string but does not change the second string.

The function prototype is defined in the `string.h` header file.

```c
char* strcat(char* s1, const char* s2);
```

The return value of `strcat()` is a string pointer pointing to the first parameter.

```c
char s1[12] = "hello";
char s2[6] = "world";

strcat(s1, s2);
puts(s1); // "helloworld"
```

In the example above, after calling `strcat()`, the value of the string `s1` changes.

Note that the length of the first parameter of `strcat()` must be sufficient to accommodate the concatenation of the second parameter string. Otherwise, the concatenated string will overflow the boundary of the first string, potentially writing to adjacent memory cells, which is dangerous. It is recommended to use `strncat()` instead.

## strncat()

`strncat()` is used to concatenate two strings, functioning exactly like `strcat()`, but with an additional third parameter to specify the maximum number of characters to add. During concatenation, once the specified number of characters is reached or the source string encounters a null character `\0`, no further characters are added. Its prototype is defined in the `string.h` header file.

```c
char* strncat(const char* dest,
  			  const char* src,
  			  size_t n
			  );
```

`strncat()` returns the first parameter, i.e., the destination string pointer.

To ensure that the concatenated string does not exceed the length of the destination string, `strncat()` is usually written like this:

```c
strncat(str1, 
  		str2, 
  		sizeof(str1) - strlen(str1) - 1
		);
```

`strncat()` always automatically adds a null character `\0` at the end of the concatenated result, so the maximum value of the third parameter should be the length of `str1` minus the length of the existing string in `str1`, minus 1. Here is an example.

```c
char s1[10] = "Monday";
char s2[8] = "Tuesday";

strncat(s1, s2, 3);
puts(s1); // "MondayTue"
```

In the example above, the length of `s1` is 10, and its character length is 6. Subtracting these values and then subtracting 1 gives 3, indicating that `s1` can add up to three more characters, resulting in `MondayTue`.

## strcmp()

To compare two strings, you can't directly use comparison operators; you must compare them character by character. The C language provides the `strcmp()` function.

The `strcmp()` function is used to compare the content of two strings. Its prototype is defined in the `string.h` header file.

```c
int strcmp(const char* s1, const char* s2);
```

According to dictionary order, if the two strings are identical, the return value is `0`; if `s1` is less than `s2`, `strcmp()` returns a value less than 0; if `s1` is greater than `s2`, the return value is greater than 0.

Here is an example:

```c
// s1 = Happy New Year
// s2 = Happy New Year
// s3 = Happy Holidays

strcmp(s1, s2) // 0
strcmp(s1, s3) // Greater than 0
strcmp(s3, s1) // Less than 0
```

Note that `strcmp()` is used to compare strings, not characters. Since characters are small integers, you can compare them directly with the equality operator (`==`). Therefore, do not pass character values (`char`) into `strcmp()`.

## strncmp()

Since `strcmp()` compares the entire strings, C also provides the `strncmp()` function to compare up to a specified position.

This function adds a third parameter to specify the number of characters to compare. Its prototype is defined in the `string.h` header file.

```c
int strncmp(const char* s1,
  			const char* s2, 
  			size_t n
			);
```

The return value is the same as for `strcmp()`. If the two strings are identical up to `n` characters, the return value is `0`; if `s1` is less than `s2`, `strncmp()` returns a value less than 0; if `s1` is greater than `s2`, the return value is greater than 0.

Here is an example:

```c
char s1[12] = "hello world";
char s2[12] = "hello C";

if (strncmp(s1, s2, 5) == 0) 
{
  printf("They all have hello.\n");
}
```

In the example above, only the first 5 characters of the two strings are compared.

## sprintf(), snprintf()

The `sprintf()` function is similar to `printf()`, but it writes data to a string instead of the display. Its prototype is defined in the `stdio.h` header file.

```c
int sprintf(char* s, const char* format, ...);
```

The first parameter of `sprintf()` is a string pointer variable. The remaining parameters are the same as `printf()`, where the second parameter is the format string and the subsequent parameters are the variables to be written.

```c
char first[6] = "hello";
char last[6] = "world";
char s[40];

sprintf(s, "%s %s", first, last);

printf("%s\n", s); // hello world
```

In the above example, `sprintf()` combines the output into "hello world" and places it into the variable `s`.

The return value of `sprintf()` is the number of characters written to the variable (excluding the terminating null character `\0`). If an error occurs, it returns a negative value.

`sprintf()` has significant security risks because if the written string is too long and exceeds the length of the destination string, `sprintf()` will still write it, leading to overflow. To control the length of the written string, C provides another function, `snprintf()`.

`snprintf()` adds one more parameter `n` to control the length of the string written to the variable, ensuring it does not exceed `n - 1` characters, leaving one position for the null character `\0`. Here is its prototype.

```c
int snprintf(char* s, size_t n, const char* format, ...);
```

`snprintf()` always automatically writes the string terminator. If you attempt to write more characters than the specified maximum, `snprintf()` will write `n - 1` characters, leaving the last position for the null character.

Here is an example.

```c
snprintf(s, 12, "%s %s", "hello", "world");
```

In the above example, the second parameter of `snprintf()` is 12, which means the maximum length of the written string is 12 (including the null terminator).

The return value of `snprintf()` is the number of characters written to the format string (excluding the null terminator `\0`). If `n` is large enough, the return value should be less than `n`. However, if the length of the format string exceeds `n`, the return value may be greater than `n`, but only `n - 1` characters are actually written to the variable. If an error occurs, a negative value is returned. Therefore, the return value can only confirm that the entire format string was written to the variable if it is non-negative and less than `n`.

## String Arrays

If an array contains multiple strings, a two-dimensional character array is used. Each string is itself a character array, and multiple strings form an array.

```c
char weekdays[7][10] = 
{
  "Monday",
  "Tuesday",
  "Wednesday",
  "Thursday",
  "Friday",
  "Saturday",
  "Sunday"
};
```

In the above example, the string array contains 7 strings, so the length of the first dimension is 7. The longest string length is 10 (including the terminating null character `\0`), so the length of the second dimension is uniformly set to 10.

Since the length of the first dimension can be automatically computed by the compiler, it can be omitted.

```c
char weekdays[][10] = 
{
  "Monday",
  "Tuesday",
  "Wednesday",
  "Thursday",
  "Friday",
  "Saturday",
  "Sunday"
};
```

In the above example, the length of the first dimension of the two-dimensional array can be automatically calculated by the compiler based on the values provided, so it can be omitted.

The second dimension's length of 10 can be wasteful because most members are shorter than 10. A solution is to change the second dimension from a character array to character pointers.

```c
char* weekdays[] = 
{
  "Monday",
  "Tuesday",
  "Wednesday",
  "Thursday",
  "Friday",
  "Saturday",
  "Sunday"
};
```

In this string array, it is essentially a one-dimensional array with 7 character pointers, each pointing to a string (character array).

To traverse the string array:

```c
for (int i = 0; i < 7; i++) 
{
  printf("%s\n", weekdays[i]);
}
```

# 11. Memory Management

## Introduction

Memory management in C is divided into two parts. One part is managed by the system, and the other part is managed manually by the user.

System-managed memory mainly refers to variables within functions (local variables). These variables enter memory when the function runs and are automatically unloaded from memory when the function ends. This area where these variables are stored is called the "stack," and the memory of the "stack" is automatically managed by the system.

User-managed memory mainly refers to variables that exist throughout the entire execution of the program (global variables). These variables need to be manually released from memory by the user. If forgotten, they will continue to occupy memory until the program exits, which is known as a "memory leak." This memory area is called the "heap," and the memory of the "heap" is manually managed by the user.

## void Pointer

As discussed in previous chapters, every block of memory has an address, and a pointer variable can access the memory block at a specified address. Pointer variables must have a type; otherwise, the compiler cannot know how to interpret the binary data stored in the memory block. However, when requesting memory from the system, sometimes the type of data to be written to memory is not known in advance. Memory is obtained first, and the data type to be written is determined later.

To meet this requirement, C provides a type of pointer called a void pointer. It only contains the address of the memory block without type information. When using this block of memory, the data type needs to be  specified to the compiler.

On the other hand, a void pointer is equivalent to an untyped pointer and can point to any type of data but cannot interpret the data. A void pointer and any other type of pointer can be converted to each other. Any type of pointer can be converted to a void pointer, and a void pointer can also be converted to any type of pointer.

```c
int x = 10;

void* p = &x; 	// Integer pointer implicitly converted to void pointer and assigned to p
int* q = p; 	// Void pointer implicitly converted to integer pointer and assigned to q
```

The example above demonstrates how integer pointers and void pointers can be converted to each other. `&x` is an integer pointer, `p` is a void pointer, and during assignment, the address of `&x` is automatically interpreted as void type. Similarly, when `p` is assigned to the integer pointer `q`, the address of `p` is automatically interpreted as an integer pointer.

Note that because the type of value a void pointer points to is unknown, the `*` operator cannot be used to retrieve the value it points to.

```c
char a = 'X';
void* p = &a;

printf("%c\n", *p); // Error
```

In the above example, `p` is a void pointer, so it is not possible to use `*p` to retrieve the value pointed to by the pointer.

The importance of the void pointer lies in the fact that many memory-related functions return a void pointer, providing only the address of the memory block, which is why it is introduced first.

## malloc()

The `malloc()` function is used to allocate memory. It requests a block of memory from the system, which is then allocated from the "heap." Its prototype is defined in the header file `stdlib.h`. (`malloc` stands for "memory allocation")

```c
void* malloc(size_t size)
```

It takes a non-negative integer as an argument, representing the number of bytes of memory to be allocated, and returns a void pointer pointing to the allocated memory block. This is reasonable because `malloc()` does not know what type of data will be stored in the memory block, so it can only return a type-less void pointer.

You can use `malloc()` to allocate memory for any data type. A common practice is to use the `sizeof()` function to determine the number of bytes required for a data type and then pass this length to `malloc()`.

```c
int* p = malloc(sizeof(int));

*p = 12;
printf("%d\n", *p); // 12
```

In the example above, memory is first allocated for an integer type, and then the integer `12` is placed into this memory. This example does not strictly require `malloc()` because C automatically provides memory for integers (in this case, `12`).

Sometimes, to improve code readability, you might cast the pointer returned by `malloc()`.

```c
int* p = (int*) malloc(sizeof(int));
```

The code above casts the void pointer returned by `malloc()` to an integer pointer.

Since the argument to `sizeof()` can be a variable, the above example can also be written as:

```c
int* p = (int*) malloc(sizeof(*p));
```

`malloc()` may fail to allocate memory, in which case it returns the constant `NULL`. `NULL` is a value of 0, representing a non-readable, non-writable memory address, essentially a pointer that does not point anywhere. It is defined in multiple header files including `stdlib.h`, so it can be used wherever `malloc()` is used. Because allocation may fail, it's best to check if `malloc()` was successful.

```c
int* p = malloc(sizeof(int));

if (p == NULL) 
{
  // Memory allocation failed
}

// or
if (!p) 
{
  //...
}
```

In the example above, by checking if the returned pointer `p` is `NULL`, you can determine whether `malloc()` was successful.

The most common use of `malloc()` is to allocate memory for arrays and custom data structures.

```c
int* p = (int*) malloc(sizeof(int) * 10);

for (int i = 0; i < 10; i++)
	p[i] = i * 5;
```

In the example above, `p` is an integer pointer pointing to a block of memory capable of holding 10 integers, so it can be used as an array.

The advantage of using `malloc()` to create arrays is that it allows for dynamic arrays, i.e., arrays of different sizes based on the number of elements.

```c
int* p = (int*) malloc(n * sizeof(int));
```

In the example above, `malloc()` dynamically allocates different sizes of arrays based on the variable `n`.

Note that `malloc()` does not initialize the allocated memory, meaning the content of the allocated memory is not set to any particular value and may contain garbage values.; it still contains the previous values. If the memory is used without initialization, it may read the old values. It is the programmer's responsibility to initialize it, for example, by using the `strcpy()` function for strings.

```c
char* p = malloc(4);
strcpy(p, "abc");
```

In the example above, the character pointer `p` points to a 4-byte memory block, and `strcpy()` copies the string "abc" into this memory, initializing it.

## free()

The `free()` function is used to release memory allocated by `malloc()`, returning the memory to the system for reuse. Otherwise, the memory block will remain occupied until the program ends. Its prototype is defined in the header file `stdlib.h`.

```c
void free(void* block)
```

In the code above, the parameter for `free()` is the memory address returned by `malloc()`. Here is an example of its usage.

```c
int* p = (int*) malloc(sizeof(int));

*p = 12;
free(p);
```

Note that once a memory block is freed, it should not be accessed again, nor should `free()` be called a second time on the same address.

A common mistake is to allocate memory within a function but not use `free()` to release it when the function ends.

```c
void gobble(double arr[], int n) 
{
  double* temp = (double*) malloc(n * sizeof(double));
  // ...
}
```

In the example above, the function `gobble()` allocates memory but does not include `free(temp)`. This results in the memory block remaining occupied after the function ends. If `gobble()` is called multiple times, multiple memory blocks will be left behind. Moreover, since the pointer `temp` is no longer accessible, these memory blocks cannot be freed again.

## calloc()

The `calloc()` function is similar to `malloc()` in that it also allocates memory bloc  ks. Its prototype is defined in the header file `stdlib.h`.(`calloc` stands for "contiguous allocation")

The differences between `calloc()` and `malloc()` are:

1. `calloc()` takes two parameters: the number of elements of a certain data type and the size in bytes of each data type.

```c
void* calloc(size_t n, size_t size);
```

`calloc()` also returns a void pointer. If allocation fails, it returns `NULL`.

2. `calloc()` initializes the allocated memory to `0`. `malloc()` does not initialize the memory; to initialize it to `0`, you would need to use the `memset()` function separately.

```c
int* p = calloc(10, sizeof(int));

// Equivalent to
int* p = malloc(sizeof(int) * 10);
memset(p, 0, sizeof(int) * 10);
```

In the example above, `calloc()` is essentially `malloc() + memset()`.

Memory allocated by `calloc()` should also be freed using `free()`.

## realloc()

The `realloc()` function is used to modify the size of an already allocated memory block. It can increase or decrease the size and returns a pointer to the new memory block. If allocation fails, it returns `NULL`. Its prototype is defined in the header file `stdlib.h`.(`realloc()` means "re-allocate")

```c
void* realloc(void* block, size_t size)
```

It takes two parameters:

- `block`: A pointer to the already allocated memory block (produced by `malloc()`, `calloc()`, or `realloc()`).
- `size`: The new size of the memory block in bytes.

`realloc()` may return a completely new address (with data automatically copied over) or the same address as before. `realloc()` prefers to shrink the memory block in place if possible, so it usually returns the original address. If the new memory block is smaller than the original, the  part is discarded; if it is larger, the additional part is not initialized (programmers can use `memset()` to initialize it).

Here is an example where `b` is an array pointer, and `realloc()` dynamically adjusts its size.

```c
int* b;

b = malloc(sizeof(int) * 10);
b = realloc(b, sizeof(int) * 2000);
```

In the example above, the pointer `b` initially points to an array of 10 integers, which is resized to 2000 integers using `realloc()`. This is the advantage of manually allocating array memory, as you can adjust the array length at runtime.

The first parameter of `realloc()` can be `NULL`, which is equivalent to creating a new pointer.

```c
char* p = realloc(NULL, 3490);
// Equivalent to
char* p = malloc(3490);
```

If the second parameter of `realloc()` is `0`, it will free the memory block.

Since allocation might fail, it's best to check if the return value of `realloc()` is `NULL`. If allocation fails, the data in the original memory block remains unchanged.

```c
float* new_p = realloc(p, sizeof(*p) * 40);

if (new_p == NULL) 
{
  printf("Error reallocing\n");
  return 1;
}
```

Note that `realloc()` does not initialize the memory block.

## restrict Keyword

When declaring pointer variables, you can use the `restrict` keyword to inform the compiler that the memory area pointed to by the pointer can only be accessed through this pointer, and not by any other pointer. This type of pointer is known as a "restricted pointer."(`restrict` is a type qualifier)

```c
int* restrict p;
p = malloc(sizeof(int));
```

In the example above, the pointer variable `p` is declared with the `restrict` keyword, making `p` a restricted pointer. This means that the memory area pointed to by `p` should only be accessed through `p` and not through any other pointer.

```c
int* restrict p;
p = malloc(sizeof(int));

int* q = p;
*q = 0; // Undefined behavior
```

In the example above, another pointer `q` is pointing to the same memory area as the restricted pointer `p`. This violates the promise made to the compiler, and accessing the memory area through `*q` results in undefined behavior.

## memcpy()

The `memcpy()` function is used to copy a block of memory from one location to another. Its prototype is defined in the header file `string.h`.

```c
void* memcpy(void* restrict dest, 
  			 const void* restrict source, 
  			 size_t n
			 );
```

In the code above, `dest` is the destination address, `source` is the source address, and `n` is the number of bytes to copy. For example, to copy 10 elements of type `double`, `n` would be `10 * sizeof(double)`, not just `10`. The function copies `n` bytes from `source` to `dest`.

Both `dest` and `source` are `void` pointers, meaning that there is no restriction on the type of pointers; different types of data can be copied. The `restrict` keyword indicates that these two memory blocks should not overlap.

`memcpy()` returns a pointer to the destination address.

Since `memcpy()` only copies the value of a memory block to another memory block, it does not need to know the type of data within the memory. Here is an example of copying a string:

```c
#include <stdio.h>
#include <string.h>

int main(void) 
{
  char s[] = "Goats!";
  char t[100];

  memcpy(t, s, sizeof(s));  // Copy 7 bytes, including the null terminator

  printf("%s\n", t);  // "Goats!"

  return 0;
}
```

In the example above, the memory containing the string `s` is copied to the memory containing the character array `t`.

`memcpy()` can replace `strcpy()` for string copying, and it is a better choice as it is both safer and faster since it does not check for the null-terminator character.

```c
char* s = "hello world";

size_t len = strlen(s) + 1;
char *c = malloc(len);

if (c) 
{
  // Method 1
  // Using strcpy()
  strcpy(c, s);

  // 
  // Using memcpy()
  memcpy(c, s, len);
}
```

In the example above, both methods achieve the same result, but `memcpy()` is preferred over `strcpy()`.

You can also define your own memory copy function using `void` pointers.

```c
void* my_memcpy(void* dest, const void* src, size_t byte_count) 
{
  // Ensure byte-tobyte copying
  char* s = (char*) src;
  char* d = (char*) dest;

  // Traverse the byte_count for copying
  while (byte_count--) 
  {
    *d++ = *s++;
  }

  return dest;
}
```

In the example above, regardless of the types of `dest` and `src`, they are cast to `char` pointers for byte-by-byte copying. The statement `*d++ = *s++` first copies the value of the source byte to the destination byte, then moves to the next byte. Finally, the function returns the copied `dest` pointer for further use.

## memmove()

The `memmove()` function is used to copy a block of memory from one location to another, allowing for overlapping memory regions. If the memory regions overlap, `memmove()` ensures that the source region is correctly handled, whereas `memcpy()` does not guarantee this behavior.

Its prototype is defined in the header file `string.h`.

```c
void* memmove(void* dest, 
  			  const void* source, 
  			  size_t n
			  );
```

In the code above, `dest` is the destination address, `source` is the source address, and `n` is the number of bytes to move. Both `dest` and `source` are `void` pointers, which means they can be used for any type of memory data. Unlike `memcpy()`, `memmove()` can handle overlapping memory regions.

`memmove()` returns a pointer to the destination address.

Here is an example:

```c
int a[100];
// ...
memmove(&a[0], &a[1], 99 * sizeof(int));
```

In the example above, 99 elements from the array starting at `a[1]` are moved one position forward, effectively removing the first element of the array.

Another example:

```c
char x[] = "Home Sweet Home";

// Outputs: Sweet Home Home
printf("%s\n", (char *) memmove(x, &x[5], 10));

Home Sweet Home
     ^
012345
    
Sweet Home Home 
         ^
1234567890
```

In this example, the 10 bytes starting from position 5 in the string `x`, which is "Sweet Home", are moved to the start of the string. As a result, `x` becomes "Sweet Home Home".

## memcmp()

The `memcmp()` function is used to compare two blocks of memory. Its prototype is defined in `string.h`.

```c
int memcmp(const void* s1,
  		   const void* s2,
  		   size_t n
		   );
```

It takes three parameters:
- `s1` and `s2` are the pointers to the memory regions to be compared.
- `n` is the number of bytes to compare.

The return value is an integer:
- If the memory regions are equal, it returns 0.
- If `s1` is greater than `s2`, it returns a positive integer.
- If `s1` is less than `s2`, it returns a negative integer.

Here is an example:

```c
char* s1 = "abc";
char* s2 = "acd";
int r = memcmp(s1, s2, 3); // Less than 0
```

In this example, `memcmp()` compares the first three bytes of `s1` and `s2`. Since `s1` is less than `s2`, `r` is a negative integer, typically -1.

Another example:

```c
char s1[] = {'b', 'i', 'g', '\0', 'c', 'a', 'r'};
char s2[] = {'b', 'i', 'g', '\0', 'c', 'a', 't'};

if (memcmp(s1, s2, 3) = = 0) // true
if (memcmp(s1, s2, 4) == 0) // true
if (memcmp(s1, s2, 7) == 0) // false
```

In this example, `memcmp()` compares the memory regions with different lengths. It demonstrates that `memcmp()` can be used to compare memory regions that include null terminators `\0` in strings.

# 12. Structure

## Introduction

In C language, apart from the basic primitive types, only arrays are composite types, which can hold multiple values but only of the same type. This is often not sufficient for practical use.

In practice, there are two main scenarios where a more flexible and powerful composite type is needed:

- Complex objects require multiple variables for description, and these variables are related, ideally needing a mechanism to link them.
- Certain functions require multiple parameters, and passing them one by one in sequence is cumbersome. It’s better to combine them into a single composite structure.

To address these issues, C provides the `struct` keyword, allowing custom composite data types that combine different types of values. This not only facilitates programming but also enhances code readability. While C does not have the concept of objects and classes like other languages, `struct` provides much of the functionality of objects and classes.

Here is an example of a custom data type using `struct`:

```c
struct fraction 
{
  int numerator;
  int denominator;
};
```

The above example defines a data type `struct fraction` for a fraction, containing two attributes: `numerator` and `denominator`.

Note that as a custom data type, its type name must include the `struct` keyword, such as `struct fraction` in the example. The standalone `fraction` has no meaning and could lead to confusion if a variable named `fraction` is defined elsewhere. Additionally, the semicolon at the end of the `struct` statement is mandatory to avoid errors.

Once a new data type is defined, variables of that type can be declared in the same way as other types.

```c
struct fraction f1;

f1.numerator = 22;
f1.denominator = 7;
```

In the example above, a variable `f1` of type `struct fraction` is declared. The compiler allocates memory for `f1`, and its different attributes can be assigned values. The attributes of the `struct` are accessed using the dot (`.`) operator, e.g., `f1.numerator`.

Remember to use the `struct` keyword when declaring custom type variables, i.e., `struct fraction f1`, not just `fraction f1`.

Attributes can also be assigned using curly braces, initializing all attributes at once.

```c
struct car 
{
  char* name;
  float price;
  int speed;
};

struct car saturn = {"Saturn SL/2", 16000.99, 175};
```

In the example above, the variable `saturn` is of type `struct car`, and its three attributes are initialized simultaneously using curly braces. If the number of values inside the curly braces is fewer than the number of attributes, the missing attributes are automatically initialized to `0`.

The order of values inside the curly braces must match the order of attributes declared in the `struct` type. Otherwise, each value must specify the attribute name.

```c
struct car saturn = {.speed=172, .name="Saturn SL/2"};
```

In this example, fewer attributes are initialized than declared, so the remaining attributes are set to `0`.

After declaring a variable, the value of a particular attribute can be modified.

```c
struct car saturn = {.speed=172, .name="Saturn SL/2"};
saturn.speed = 168;
```

In the example above, the `speed` attribute is updated to `168`.

The `struct` type declaration and variable declaration can be combined into one statement.

```c
struct book 
{
  char title[500];
  char author[100];
  float value;
} b1;
```

The above statement declares both the data type `book` and a variable `b1` of that type. If the type identifier `book` is used only in this instance, it can be omitted.

```c
struct 
{
  char title[500];
  char author[100];
  float value;
} b1;
```

In this example, an anonymous data type is declared using `struct`, and then a variable `b1` of this type is declared.

As with other variable declarations, variables can be initialized at the same time they are declared.

```c
struct 
{
  char title[500];
  char author[100];
  float value;
} b1 = {"Harry Potter", "J. K. Rowling", 10.0},
  b2 = {"Cancer Ward", "Aleksandr Solzhenitsyn", 7.85};
```

In the example above, variables `b1` and `b2` are declared and initialized simultaneously.

The `typedef` command introduced in the next chapter can create an alias for the `struct`, making usage simpler.

```c
typedef struct cell_phone 
{
  int cell_no;
  float minutes_of_charge;
} phone;

phone p = {5551234, 5};
```

In the example above, `phone` is an alias for `struct cell_phone`.

Pointer variables can also point to `struct` structures.

```c
struct book 
{
  char title[500];
  char author[100];
  float value;
}* b1;

// Or written as two statements
struct book 
{
  char title[500];
  char author[100];
  float value;
};
struct book* b1;
```

In the example above, `b1` is a pointer to an instance of `struct book`.

`struct` structures can also be used as array members.

```c
struct fraction numbers[1000];

numbers[0].numerator = 22;
numbers[0].denominator = 7;
```

In the example above, an array `numbers` with 1000 members is declared, where each member is an instance of the custom type `fraction`.

The storage space occupied by a `struct` is not simply the sum of the space for each attribute but is aligned to the largest attribute’s storage size. This alignment improves read and write efficiency.

```c
struct foo 
{
  int a;
  char* b;
  char c;
};
printf("%d\n", sizeof(struct foo)); // 24
```

In the example above, `struct foo` has three attributes. On a 64-bit computer, the storage space for `struct foo` is 24 bytes: `int a` takes 4 bytes, `char* b` takes 8 bytes, and `char c` takes 1 byte. The total is 13 bytes (4 + 8 + 1), but `struct foo` actually occupies 24 bytes due to alignment requirements, where the largest attribute (`char* b`) determines the alignment, causing other attributes to align to 8 bytes.

The extra space is filled with padding to achieve proper alignment, resulting in the real structure:

```c
struct foo 
{
  int a;        // 4
  char pad1[4]; // 4 bytes padding
  char *b;      // 8
  char c;       // 1
  char pad2[7]; // 7 bytes padding
};
printf("%d\n", sizeof(struct foo)); // 24
```

This alignment reduces memory access time by aligning memory blocks, facilitating quick access to each attribute’s starting address.

To save space, define `struct` attributes in increasing order of their storage sizes when necessary.

```c
struct foo 
{
  char c;
  int a;
  char* b;
};
printf("%d\n", sizeof(struct foo)); // 16
```

In the example above, the smallest attribute `char c` is placed first, followed by `int a`, and the largest `char* b` is last. This arrangement reduces the `struct foo`’s memory usage from 24 bytes to 16 bytes.

## Copying `struct`

`struct` variables can be copied to another variable using the assignment operator (`=`), creating a completely new copy. The system allocates a new memory space of the same size as the original variable and copies each attribute, essentially creating a duplicate. This differs from array copying, so be cautious.

```c
struct cat { char name[30]; short age; } a, b;

strcpy(a.name, "Hula");
a.age = 3;

b = a;
b.name[0] = 'M';

printf("%s\n", a.name); // Hula
printf("%s\n", b.name); // Mula
```

In the example above, `b` is a copy of `a`. The values of the two variables are independent; changing `b.name` does not affect `a.name`.

This example assumes that the `struct` attributes are defined as character arrays for copying data. If the attributes are defined as character pointers, the result is different.

```c
struct cat { char* name; short age; } a, b;

a.name = "Hula";
a.age = 3;

b = a;
```

In this example, with `name` as a character pointer, assigning `a` to `b` makes `b.name` point to the same address as `a.name`, meaning the two pointers share the same address. The `struct` now holds a pointer, not an array, so the copy is of the pointer, not the string itself. Moreover, you cannot modify the string since the character pointer points to a read-only string.

In summary, the assignment operator (`=`) copies each attribute’s value exactly, creating a duplicate `struct` variable. This is different from arrays, where assignment does not copy the data but shares the address.

Note that assignment requires the two variables to be of the same type; `struct` variables of different types cannot be assigned to each other.

Additionally, C does not provide a way to compare two custom data structures for equality; comparison operators (e.g., `==` and `!=`) cannot be used to compare whether two structures are equal or not.

## `struct` Pointers

When a `struct` variable is passed to a function, the function receives a copy of the original value.

```c
#include <stdio.h>

struct turtle 
{
  char* name;
  char* species;
  int age;
};

void happy(struct turtle t) 
{
  t.age = t.age + 1;
}

int main() 
{
  struct turtle myTurtle = 
  {
      "MyTurtle", "sea turtle", 99
  };
  happy(myTurtle);
  printf("Age is %i\n", myTurtle.age); // Output: 99
  return 0;
}
```

In the example above, the `happy()` function receives a copy of the `struct` variable `myTurtle`. The increment operation inside the function does not affect the `age` attribute outside the function because the function works with a copy of the original data.

Typically, developers want to pass the same data to a function, where changes made within the function reflect outside the function. Passing the same data also improves program performance. To achieve this, you need to pass a pointer to the `struct` variable, allowing modification of the `struct` attributes that will affect the original data.

Here’s how to pass a `struct` pointer to a function:

```c
void happy(struct turtle* t) 
{
}

happy(&myTurtle);
```

In the code above, `t` is a pointer to the `struct` type. When calling the function, you pass the pointer with `&myTurtle`. Unlike arrays, the `struct` type itself is not a pointer, so you must use `&myTurtle` to pass the address.

Inside the function, you need to use `(*t).age` to access the `struct` members from the pointer.

```c
void happy(struct turtle* t) 
{
  (*t).age = (*t).age + 1;
}
```

In this example, `(*t).age` should not be written as `*t.age` because the dot operator (`.`) has higher precedence than the dereference operator (`*`). Writing `*t.age` would interpret `t.age` as a pointer and dereference it, leading to unpredictable results.

To make it easier to work with `struct` pointers, C provides the arrow operator (`->`), which allows direct access to `struct` attributes from a pointer, improving code readability.

```c
void happy(struct turtle* t) 
{
  t->age = t->age + 1;
}
```

In summary, use the dot operator (`.`) to access attributes of a `struct` variable and the arrow operator (`->`) to access attributes of a `struct` pointer. For a variable `myStruct`, if `ptr` is its pointer, the following three expressions are equivalent:

```c
// ptr == &myStruct
myStruct.prop == (*ptr).prop == ptr->prop
```

## Nested `struct`

A `struct` can have members that are other `struct` types.

```c
struct species 
{
  char* name;
  int kinds;
};

struct fish 
{
  char* name;
  int age;
  struct species breed;
};
```

In the example above, the `breed` attribute of `fish` is another `struct` type called `species`.

There are multiple ways to assign values to nested `struct`:

```c
// Method 1
struct fish shark = {"shark", 9, {"Selachimorpha", 500}};

// Method 2
struct species myBreed = {"Selachimorpha", 500};
struct fish shark = {"shark", 9, myBreed};

// Method 3
struct fish shark = 
{
  .name = "shark",
  .age = 9,
  .breed = {"Selachimorpha", 500}
};

// Method 4
struct fish shark = 
{
  .name = "shark",
  .age = 9,
  .breed.name = "Selachimorpha",
  .breed.kinds = 500
};

printf("Shark's species is %s", shark.breed.name);
```

The example above shows four ways to assign values to nested `struct` types. Note that to access the nested attributes of `breed`, you need to use two dot operators (e.g., `shark.breed.name`).

Here’s another example of nested `struct`:

```c
struct name 
{
  char first[50];
  char last[50];
};

struct student 
{
  struct name name;
  short age;
  char sex;
} student1;

strcpy(student1.name.first, "Harry");
strcpy(student1.name.last, "Potter");

// or
struct name myname = {"Harry", "Potter"};
student1.name = myname;
```

In this example, the `name` attribute of the `student` type is another custom type. To access its attributes, use two dot operators, like `student1.name.first`. Additionally, use the `strcpy()` function to assign values to character arrays, as directly assigning to the array name will result in an error.

A `struct` can not only reference other `struct` types but also self-reference, meaning the `struct` can reference itself. For example, a linked list node can be defined as follows:

```c
struct node 
{
  int data;
  struct node* next;
};
```

In this example, the `next` attribute of `node` is a pointer to another `node` instance. Here’s how to use this `struct` to define a linked list:

```c
struct node 
{
  int data;
  struct node* next;
};

struct node* head;

// Create a list with three nodes: (11) -> (22) -> (33)
head = malloc(sizeof(struct node));

head->data = 11;
head->next = malloc(sizeof(struct node));

head->next->data = 22;
head->next->next = malloc(sizeof(struct node));

head->next->next->data = 33;
head->next->next->next = NULL;

// Traverse the list
for (struct node *cur = head; cur != NULL; cur = cur->next) {
  printf("%d\n", cur->data);
}
```

The above example shows a basic implementation of a linked list, and you can traverse it using a `for` loop.

## Bit Fields

A `struct` can also define a data structure composed of binary bits, known as "bit fields". This is useful for working with low-level binary data.

```c
struct 
{
  unsigned int ab:1;
  unsigned int cd:1;
  unsigned int ef:1;
  unsigned int gh:1;
} synth;

synth.ab = 0;
synth.cd = 1;
```

In the example above, the `:1` after each attribute specifies that these attributes occupy only one binary bit each. Thus, the entire structure is 4 binary bits wide.

Note that bit fields can only be of integer types within the structure.

When storing bit fields, C will allocate memory based on the size of an `int`. If there are remaining bits, you can use unnamed fields to fill those bits. You can also use fields with a width of 0 to occupy the remaining bits in the current byte, forcing the next field to start in the next byte.

```c
struct 
{
  unsigned int field1 : 1;
  unsigned int        : 2;  // Unnamed field of width 2
  unsigned int field2 : 1;
  unsigned int        : 0;  // Force alignment to next byte
  unsigned int field3 : 1;
} stuff;
```

In the example above, `stuff.field1` and `stuff.field2` are separated by a 2-bit unnamed field. `stuff.field3` will start in the next byte due to the unnamed field with a width of 0.

## Flexible Array Members

Sometimes, the number of elements in an array cannot be determined in advance. Declaring an array with a large fixed size can waste space. C provides a solution called flexible array members.

When the number of array members is not known in advance, you can define a `struct` with a flexible array member.

```c
struct vstring 
{
  int len;
  char chars[];
};
```

In this example, the `struct vstring` has two attributes. The `len` attribute keeps track of the length of the `chars` array, which does not have a predefined size.

The actual size of the `chars` array can be determined when allocating memory for `vstring`.

```c
struct vstring* str = malloc(sizeof(struct vstring) + n * sizeof(char));
str->len = n;
```

In this example, `n` is the number of elements in the `chars` array, which is determined at runtime. The memory allocated for `struct vstring` includes the space for the `struct` itself plus space for `n` `char` elements. The `len` attribute records the value of `n`.

This way, the `chars` array can have `n` elements without being fixed in advance, adapting to runtime needs.

Flexible array members have specific rules. First, the flexible member must be the last attribute of the `struct`. Additionally, the `struct` must have at least one other attribute besides the flexible array member.

# 13. `typedef` Command

## Introduction

The `typedef` command is used to create an alias for a type.

```c
typedef type name;
```

In the above code, `type` represents the type name, and `name` represents the alias.

```c
typedef unsigned char BYTE;

BYTE c = 'z';
```

In the example above, the `typedef` command creates an alias `BYTE` for the type `unsigned char`, and then you can use `BYTE` to declare variables.

`typedef` can specify multiple aliases at once.

```c
typedef int antelope, bagel, mushroom;
```

In the example above, three aliases are created for the `int` type in one go.

`typedef` can also create aliases for pointers.

```c
typedef int* intptr;

int a = 10;
intptr x = &a;
```

In the example above, `intptr` is an alias for `int*`. However, be careful when using it, as it may not be immediately clear that the variable `x` is a pointer type.

`typedef` can also create aliases for array types.

```c
typedef int five_ints[5];

five_ints x = {11, 22, 33, 44, 55};
```

In the example above, `five_ints` is an array type containing 5 integers.

The syntax for creating an alias for a function is as follows.

```c
typedef signed char (*fp)(void);
```

In the example above, the type alias `fp` is a pointer representing the function `signed char (*)(void)`.

## Main Benefits

The benefits of using `typedef` to create type aliases mainly include:

1. Better code readability.

```c
typedef char* STRING;

STRING name;
```

In the example above, the character pointer is given the alias `STRING`, making it easier to identify that the variable is a string when using `STRING`.

2. Creating aliases for complex data structures defined by `struct`, `union`, `enum`, etc., making them easier to reference.

```c
struct treenode 
{
  // ...
};

typedef struct treenode* Tree;
```

In the example above, `Tree` is an alias for `struct treenode*`.

`typedef` can also be used together with `struct` to define data types.

```c
typedef struct animal 
{
  char* name;
  int leg_count, speed;
} animal;
```

In the example above, when defining a custom data type, `typedef` is used to create an alias `animal` for `struct animal`.

In this case, C language allows omitting the type name after the `struct` command.

```c
typedef struct 
{
  char *name;
  int leg_count, speed;
} animal;
```

In the example above, an alias `animal` is created for an anonymous data type.

3. Facilitating future type changes for variables.

```c
typedef float app_float;

app_float f1, f2, f3;
```

In the example above, variables `f1`, `f2`, and `f3` are of type `float`. If you need to change their type in the future, you only need to modify the `typedef` statement.

```c
typedef long double app_float;
```

The above command changes the type of variables `f1`, `f2`, and `f3` to `long double`.

4. Portability

A certain value may have different types on different computers.

```c
int i = 100000;
```

The above code works fine on a 32-bit integer computer but may cause errors on a 16-bit integer computer.

The C language solution is to provide type aliases that are interpreted as different types on different computers, such as `int32_t`.

```c
int32_t i = 100000;
```

In the example above, the variable `i` is declared as `int32_t`, ensuring it is 32-bit wide on different computers, avoiding errors during code migration.

These types of aliases are defined using `typedef`. Here are similar examples.

```c
typedef long int ptrdiff_t;
typedef unsigned long int size_t;
typedef int wchar_t;
```

These integer type aliases are included in the `stdint.h` header file, so different computer architectures only need to modify this header file instead of changing the code.

Thus, `typedef` helps improve code portability to adapt to different computer architectures.

5. Simplifying type declarations

Some type declarations in C are quite complex, such as the following.

```c
char (*(*x(void))[5])(void);
```

`typedef` can simplify complex type declarations, making them easier to understand. First, create a type alias for the outermost layer.

```c
typedef char (*Func)(void);
Func (*x(void))[5];
```

This still seems a bit complex, so create another alias for the inner layer as well.

```c
typedef char (*Func)(void);
typedef Func Arr[5];
Arr* x(void);
```

The above code is easier to interpret.

- `x` is a function that returns a pointer to the `Arr` type.
- `Arr` is an array with 5 members, each of type `Func`.
- `Func` is a function pointer pointing to a function with no parameters, returning a character value.

# 14. Union Structure

Sometimes, a data structure is needed to represent different data types in different situations. For example, if a data structure is used to represent the "quantity" of fruit, it may need to be an integer (6 apples) or a floating-point number (1.5 kilograms of strawberries).

C provides the `union` structure to define a flexible data structure that can change. It contains various attributes, but all attributes share the same memory space, meaning these attributes interpret the same binary data, where only one interpretation is usually meaningful. Additionally, the later-written attribute will overwrite the earlier ones, meaning the same memory can be used first for one attribute and then for another. The main advantage is saving memory space.

```c
union quantity 
{
  short count;
  float weight;
  float volume;
};
```

In the example above, the `union` command defines a data type `quantity` with three attributes. Although it has three attributes, only one value can be written, and the three attributes interpret this value differently. The last assigned attribute is often the one that can have a meaningful value.

When using it, declare a variable of this type.

```c
// Method 1
union quantity q;
q.count = 4;

// Method 2
union quantity q = {.count=4};

// Method 3
union quantity q = {4};
```

The above code shows three ways to assign values to a union structure. The last method does not specify the attribute name and assigns the value to the first attribute.

After executing the above code, `q.count` will have a value, while the other two attributes will not have defined values.

```c
printf("count is %i\n", q.count); // count is 4
printf("weight is %f\n", q.weight); // Undefined behavior
```

To make the `q.weight` attribute have a value, it needs to be assigned first.

```c
q.weight = 0.5;
printf("weight is %f\n", q.weight); // weight is 0.5
```

Once another attribute is assigned, the previously valid `q.count` attribute will also change, making its use potentially meaningless. Apart from this, the other uses of the `union` structure are basically the same as those of the `struct` structure.

The `union` structure also supports the pointer operator `->`.

```c
union quantity 
{
  short count;
  float weight;
  float volume;
};

union quantity q;
q.count = 4;

union quantity* ptr;
ptr = &q;

printf("%d\n", ptr->count); // 4
```

In the example above, `ptr` is a pointer to `q`, so `ptr->count` is equivalent to `q.count`.

The `union` structure pointer relates to its attributes, meaning the pointer's data type is determined by the currently interpreted attribute.

```c
union foo 
{
  int a;
  float b;
} x;

int* foo_int_p = (int *)&x;
float* foo_float_p = (float *)&x;

x.a = 12;
printf("%d\n", x.a);           // 12
printf("%d\n", *foo_int_p);    // 12

x.b = 3.141592;
printf("%f\n", x.b);           // 3.141592
printf("%f\n", *foo_float_p);  // 3.141592
```

In the example above, `&x` is a pointer to the `foo` structure, and its data type is entirely determined by the currently assigned attribute.

The `typedef` command can create an alias for the `union` data type.

```c
typedef union 
{
  short count;
  float weight;
  float volume;
} quantity;
```

In the example above, the `union` command defines a data type with three attributes, and the `typedef` command creates an alias `quantity` for it.

The main benefit of the `union` structure is saving space. It reuses a memory space for different types of data. Although three attributes are defined, only one is used at a time, saving the space of the other two attributes. The memory length occupied by the `union` structure is equal to the length of its longest attribute.

# 15. Enum Type

When a data type has only a few possible values, each with its own meaning, you can define these values as an `enum` type to improve code readability.

```c
enum colors {RED, GREEN, BLUE};

printf("%d\n", RED); // 0
printf("%d\n", GREEN);  // 1
printf("%d\n", BLUE);  // 2
```

In the example above, the `enum` command defines an enumeration type `colors` with three possible values: `RED`, `GREEN`, and `BLUE`. These names automatically become integer constants with default values of `0`, `1`, and `2`, respectively. This is more readable than using raw integers like `0`.

Note that the constant names inside an `enum` follow identifier naming conventions but are usually written in uppercase.

You can declare a variable of the `enum` type like this:

```c
enum colors color;
```

In the code above, the variable `color` is of type `enum colors`, and its value can be one of the constants `RED`, `GREEN`, or `BLUE`.

```c
color = BLUE;
printf("%i\n", color); // 2
```

In this code, the value of `color` is set to `BLUE`, which is a constant with the value `2`.

The `typedef` command can create an alias for the `enum` type:

```c
typedef enum 
{
  SHEEP,
  WHEAT,
  WOOD,
  BRICK,
  ORE
} RESOURCE;

RESOURCE r;
```

In this example, `RESOURCE` is an alias for the `enum` type. You use this alias to declare variables.

There is also a less common syntax where you declare the `enum` type and assign values to variables on the same line:

```c
enum 
{
  SHEEP,
  WHEAT,
  WOOD,
  BRICK,
  ORE
} r = BRICK, s = WOOD;
```

Here, `r` is assigned the value `3`, and `s` is assigned the value `2`.

Sometimes the purpose of using an `enum` is not to define a data type but to declare a set of constants. In this case, you can use a simplified syntax:

```c
enum { ONE, TWO };

printf("%d %d", ONE, TWO);  // 0 1
```

In this example, `enum` is followed by a block where constants are declared. `ONE` and `TWO` are two `enum` constants.

Constants are separated by commas. The trailing comma after the last constant is optional.

```c
enum { ONE, TWO, };
```

`enum` automatically assigns consecutive values starting from `0` to constants. However, you can also specify values for `enum` constants:

```c
enum { ONE = 1, TWO = 2 };

printf("%d %d", ONE, TWO);  // 1 2
```

`enum` constants can have non-continuous values:

```c
enum { X = 2, Y = 18, Z = -2 };
```

`enum` constants can also have the same value:

```c
enum { X = 2, Y = 2, Z = 2 };
```

If some constants in a group have specified values while others do not, the unspecified constants will automatically increment from the last specified value:

```c
enum 
{
  A,    // 0
  B,    // 1
  C = 4,  // 4
  D,    // 5
  E,    // 6
  F = 3,   // 3
  G,    // 4
  H     // 5
};
```

The scope of an `enum` is similar to that of variables. If declared at the top level, it is valid throughout the file; if declared inside a block, it is valid only within that block. Compared to constants declared with `int`, `enum` provides a clearer way to express code intent.

# 16. Preprocessor

## Introduction

Before the C language compiler compiles a program, it first uses the preprocessor to process the code.

The preprocessor initially cleans up the code by removing comments and merging multi-line statements into a single logical line. Then it executes preprocessor directives, which begin with `#`. This chapter introduces C language preprocessor directives.

Preprocessor directives can appear anywhere in the program, but it is customary to place them at the beginning of the code.

Each preprocessor directive starts with `#` and appears at the beginning of a line, though it can be preceded by whitespace (such as spaces or tabs). There can also be spaces between the `#` and the rest of the directive, but to maintain compatibility with older compilers, it is generally not done.

All preprocessor directives are single lines, unless continued onto the next line with a backslash. No semicolon is needed at the end of directives.

## #define

`#define` is the most common preprocessor directive used to replace a specified term with another term. Its parameters are divided into two parts: the first parameter is the term to be replaced, and the remaining parameters are the replacement content. Each replacement rule is called a macro.

```c
#define MAX 100
```

In the example above, `#define` specifies that `MAX` in the source code should be replaced with `100`. `MAX` is called a macro.

Macro names cannot have spaces and must follow C language variable naming rules; they can only use letters, digits, and underscores (`_`), and the first character cannot be a digit.

Macros are replaced exactly as specified, with the replacement being an exact match.

```c
#define HELLO "Hello, world"

// Equivalent to printf("%s", "Hello, world");
printf("%s", HELLO);
```

In the example above, the macro `HELLO` is replaced exactly with `"Hello, world"`.

The `#define` directive can appear anywhere in the source file, and is valid from where it appears until the end of the file. It is customary to place `#define` at the top of the source file. Its main advantage is that it makes the program more readable and easier to modify.

The `#define` directive starts with `#` and continues until the newline character. If the directive is too long, it can be split over multiple lines using a backslash.

```c
#define OW "C programming language is invented \
in 1970s."
```

In the example above, the backslash at the end of the first line splits the `#define` directive into two lines.

`#define` allows multiple replacements, meaning one macro can include another macro.

```c
#define TWO 2
#define FOUR TWO*TWO
```

In the example above, `FOUR` is replaced with `2*2`.

Note that if a macro appears inside a string (i.e., within double quotes) or as part of another identifier, it will not be replaced.

```c
#define TWO 2

// Outputs TWO
printf("TWO\n");

// Outputs 22
const TWOs = 22;
printf("%d\n", TWOs);
```

In the example above, `TWO` inside double quotes and the identifier `TWOs` are not replaced.

Macros with the same name can be redefined as long as the definitions are the same. If the definitions differ, an error will occur.

```c
// Correct
#define FOO hello
#define FOO hello

// Error
#define BAR hello
#define BAR world
```

In the example above, the macro `FOO` has not changed, so it can be redefined. The macro `BAR`, however, has changed, which results in an error.

## Macros with Parameters

### Basic Usage

The power of macros lies in their ability to accept one or more parameters using parentheses after their name.

```c
#define SQUARE(X) X*X
```

In the example above, the macro `SQUARE` accepts one parameter `X`, replacing it with `X*X`.

Note that there should be no space between the macro name and the left parenthesis.

Here’s how this macro is used.

```c
// Replaced with z = 2*2;
z = SQUARE(2);
```

This usage resembles a function but is not a function; it performs a direct substitution, which can behave differently from a function.

```c
#define SQUARE(X) X*X

// Outputs 19
printf("%d\n", SQUARE(3 + 4));
```

In this example, if `SQUARE(3 + 4)` were a function, it would output 49 (`7*7`); however, since the macro performs a direct substitution, it becomes `3 + 4*3 + 4`, resulting in 19.

As you can see, direct substitution can lead to unexpected behavior. To avoid many issues, it’s advisable to use parentheses around macro parameters.

```c
#define SQUARE(X) ((X) * (X))
```

In the example above, `SQUARE(X)` with two layers of parentheses helps avoid many errors.

Macro parameters can also be empty.

```c
#define getchar() getc(stdin)
```

In this example, the macro `getchar()` has no parameters. The parentheses are optional but are included to make it appear more like a function.

Generally, macros with parameters are single-line. Here are two examples.

```c
#define MAX(x, y) ((x)>(y)?(x):(y))
#define IS_EVEN(n) ((n)%2==0)
```

If a macro is too long, you can use a backslash (`\`) to break it into multiple lines.

```c
#define PRINT_NUMS_TO_PRODUCT(a, b)\
{ \
  int product = (a) * (b); \
  for (int i = 0; i < product; i++) \
  { \
    printf("%d\n", i); \
  } \
}
```

In the example above, the replacement text is enclosed in braces to create a block scope and prevent macro-internal variables from affecting the outside.

Macros with parameters can also be nested, with one macro containing another.

```c
#define QUADP(a, b, c) ((-(b) + sqrt((b) * (b) - 4 * (a) * (c))) / (2 * (a)))
#define QUADM(a, b, c) ((-(b) - sqrt((b) * (b) - 4 * (a) * (c))) / (2 * (a)))
#define QUAD(a, b, c) QUADP(a, b, c), QUADM(a, b, c)
```

The example above shows macros for solving quadratic equations. Since there are two solutions, the `QUAD` macro first expands into the `QUADP` and `QUADM` macros, each providing a solution.

So, when should you use parameterized macros versus functions?

Generally, functions should be used first as they are more powerful and easier to understand. Macros can sometimes produce unexpected results and are often limited to single lines unless line breaks are escaped, which reduces readability.

The advantage of macros is their relative simplicity; they are essentially string replacements and do not involve data types like functions. Additionally, macros replace every instance with actual code, saving the overhead of function calls, which can be more efficient. Moreover, many older codes use macros, especially for simple mathematical operations, so understanding them is necessary to read legacy code.

### `#` Operator and `##` Operator

Since macros do not involve data types, they can be replaced with various types of values. If you want the replacement value to be a string, you can use the `#` operator before the macro parameter.

```c
#define STR(x) #x

// Equivalent to printf("%s\n", "3.14159");
printf("%s\n", STR(3.14159));
```

In the example above, `STR(3.14159)` is replaced with `"3.14159"`. Without the `#`, it would be interpreted as a floating-point number. With the `#`, it is converted to a string.

Here’s another example.

```c
#define XNAME(n) "x"#n

// Outputs x4
printf("%s\n", XNAME(4));
```

In this example, `#n` specifies that the parameter should be output as a string, combined with the preceding string to form `"x4"`. Without the `#`, this would be more complicated to achieve.

If the parameters need to be concatenated with other identifiers to form a new identifier, you can use the `##` operator. It serves to concatenate the parameters into a single identifier.

```c
#define MK_ID(n) i##n
```

In the example above, `n` is the macro parameter that needs to be concatenated with the identifier `i` using `##`. Here’s how the macro is used.

```c
int MK_ID(1), MK_ID(2), MK_ID(3);
// Replaced with
int i1, i2, i3;
```

In this example, the replaced text `i1`, `i2`, `i3` are three identifiers, where the parameter `n` is part of the identifier. This shows that the `##` operator is mainly used for generating variable names and identifiers in bulk.

### Variadic Macros

Macro parameters can also be of variable length (i.e., an uncertain number of parameters), denoted by `...`.

```c
#define X(a, b, ...) (10*(a) + 20*(b)), __VA_ARGS__
```

In the example above, `X(a, b, ...)` indicates that `X()` has at least two parameters, with additional parameters represented by `...`. In the replacement text, `__VA_ARGS__` represents the additional parameters (separated by commas). Here’s an example.

```c
X(5, 4, 3.14, "Hi!", 12)
// Replaced with
(10*(5) + 20*(4)), 3.14, "Hi!", 12
```

Note that `...` can only replace parameters at the end of the macro, not in the middle.

```c
// Error
#define WRONG(X, ..., Y) #X #__VA_ARGS__ #Y
```

In this example, `...` replaces parameters in the middle, which is not allowed and will result in an error.

Adding a `#` before `__VA_ARGS__` can turn the output into a string.

```c
#define X(...) #__VA_ARGS__

printf("%s\n", X(1,2,3));  // Prints "1, 2, 3"
```

## `#undef`

The `#undef` directive is used to cancel a macro previously defined with `#define`.

```c
#define LIMIT 400
#undef LIMIT
```

In this example, the `undef` directive cancels the previously defined macro `LIMIT`, allowing you to redefine `LIMIT` later.

If you want to redefine a macro but are unsure if it was previously defined, you can use `#undef` to cancel it first and then define it. If the macro name does not exist, `#undef` does not produce an error.

The GCC `-U` option can cancel macro definitions from the command line, equivalent to `#undef`.

```c
$ gcc -ULIMIT foo.c
```

In the example above, the `-U` option cancels the `LIMIT` macro, similar to using `#undef LIMIT` in the source file.

## `#include`

The `#include` directive is used to load other source files into the current file during compilation. It has two forms.

```c
// Form 1
#include <foo.h> // Load system-provided file

// Form 2
#include "foo.h" // Load user-provided file
```

Form 1 uses angle brackets to indicate that the file is provided by the system, usually a standard library file, and does not require a path. The compiler will search for these files in the system's standard directories.

Form 2 uses double quotes to indicate that the file is user-provided. The specific path depends on the compiler settings, which might be the current directory or the project's working directory. If the file is located elsewhere, you need to specify the path, for example:

```c
#include "/usr/local/lib/foo.h"
```

The GCC compiler's `-I` option can also be used to specify the include path for user files.

```c
$ gcc -Iinclude/ -o code code.c
```

In this command, `-Iinclude/` specifies that user files are loaded from the `include` subdirectory of the current directory.

The most common use of `#include` is to load header files containing function prototypes (with `.h` extensions), as described in the "Multi-file Compilation" section. The order of multiple `#include` directives is not important, and including the same header file multiple times is legal.

## `#if...#endif`

The `#if...#endif` directive is used for conditional preprocessing. If the condition is met, the enclosed lines are compiled; otherwise, they are ignored by the compiler.

```c
#if 0
  const double pi = 3.1415; // Will not be executed
#endif
```

In the example above, `#if` followed by `0` means the condition is false. Thus, the internal variable definition is ignored by the compiler. `#if 0` is commonly used as a form of comment, placing unnecessary code inside `#if 0`.

The condition after `#if` is usually an expression. If the value of the expression is not `0`, the condition is true, and the internal statements are compiled; if the value is `0`, the condition is false, and the statements are ignored.

`#if...#endif` can also include `#else` to specify statements to be compiled if the condition is not met.

```c
#define FOO 1

#if FOO
  printf("defined\n");
#else
  printf("not defined\n");
#endif
```

In this example, if the macro `FOO` is defined, it will be replaced with `1`, resulting in the output `defined`; otherwise, the output will be `not defined`.

If there are multiple conditions, `#elif` can be used for additional checks.

```c
#if HAPPY_FACTOR == 0
  printf("I'm not happy!\n");
#elif HAPPY_FACTOR == 1
  printf("I'm just regular\n");
#else
  printf("I'm extra happy!\n");
#endif
```

In this example, `#elif` provides a second condition check. Note that `#elif` must come before `#else`. If none of the conditions are met, the `#else` part is executed.

An undefined macro is treated as `0`. Therefore, if `UNDEFINED` is an undefined macro, `#if UNDEFINED` is false, while `#if !UNDEFINED` is true.

A common application of `#if` is to enable (or disable) debug mode.

```c
#define DEBUG 1

#if DEBUG
printf("value of i : %d\n", i);
printf("value of j : %d\n", j);
#endif
```

In this example, setting `DEBUG` to `1` enables debug mode and outputs debugging information.

The GCC `-D` option can specify the value of a macro at compile time, making it easy to toggle debugging switches.

```c
$ gcc -DDEBUG=1 foo.c
```

In this example, the `-D` option sets the `DEBUG` macro to `1`, equivalent to `#define DEBUG 1` in the code.

## `#ifdef...#endif`

The `#ifdef...#endif` directive is used to check if a macro is defined.

Sometimes source files might include the same library multiple times. To avoid this, an empty macro can be defined within the library file to check if the library has been loaded.

```c
#define EXTRA_HAPPY
```

In this example, `EXTRA_HAPPY` is an empty macro.

Then, the source file uses `#ifdef...#endif` to check if this macro is defined.

```c
#ifdef EXTRA_HAPPY
  printf("I'm extra happy!\n");
#endif
```

In this example, `#ifdef` checks if the `EXTRA_HAPPY` macro is defined. If it exists, indicating that the library file has been loaded, it will print a message.

`#ifdef` can be combined with `#else`.

```c
#ifdef EXTRA_HAPPY
  printf("I'm extra happy!\n");
#else
  printf("I'm just regular\n");
#endif
```

In this example, if the `EXTRA_HAPPY` macro is not defined, the `#else` part will be executed.

`#ifdef...#else...#endif` can be used for conditional inclusion.

```c
#ifdef MAVIS
  #include "foo.h"
  #define STABLES 1
#else
  #include "bar.h"
  #define STABLES 2
#endif
```

In this example, different header files are included based on whether the `MAVIS` macro is defined.

## `defined` Operator

The `#ifdef` directive from the previous section is equivalent to `#if defined`.

```c
#ifdef FOO
// Equivalent to
#if defined FOO
```

In this example, `defined` is a preprocessor operator. If its argument is a defined macro, it returns 1; otherwise, it returns 0.

This syntax can be used for multiple checks.

```c
#if defined FOO
  x = 2;
#elif defined BAR
  x = 3;
#endif
```

One application of this operator is to include different header files for different architectures.

```c
#if defined IBMPC
  #include "ibmpc.h"
#elif defined MAC
  #include "mac.h"
#else
  #include "general.h"
#endif
```

In this example, different macros are defined for different architectures, and the code includes the corresponding header files based on these macros.

## `#ifndef...#endif`

The `#ifndef...#endif` directive is the opposite of `#ifdef...#endif`. It is used to check if a macro is not defined and, if so, perform the specified actions.

```c
#ifdef EXTRA_HAPPY
  printf("I'm extra happy!\n");
#endif

#ifndef EXTRA_HAPPY
  printf("I'm just regular\n");
#endif
```

In this example, `#ifdef` and `#ifndef` are used to specify different code sections based on whether the `EXTRA_HAPPY` macro is defined or not.

`#ifndef` is commonly used to prevent multiple inclusions. For example, to prevent the `myheader.h` header file from being included multiple times, you can wrap it in `#ifndef...#endif`.

```c
#ifndef MYHEADER_H
  #define MYHEADER_H
  #include "myheader.h"
#endif
```

In this example, the macro `MYHEADER_H` corresponds to the filename `myheader.h` in uppercase. As long as `#ifndef` finds that the macro is not defined, it means that the header file has not been included before. Therefore, it includes the contents of the file and defines the macro `MYHEADER_H` to prevent re-inclusion.

`#ifndef` is equivalent to `#if !defined`.

```c
#ifndef FOO
// Equivalent to
#if !defined FOO
```

## Predefined Macros

C provides several predefined macros that can be used directly:

- `__DATE__`: The date of compilation in the format "Mmm dd yyyy" (e.g., Nov 23 2021).
- `__TIME__`: The time of compilation in the format "hh:mm:ss".
- `__FILE__`: The name of the current file.
- `__LINE__`: The current line number.
- `__func__`: The name of the currently executing function. This predefined macro must be used within the function scope.
- `__STDC__`: If set to 1, it indicates that the compiler adheres to the C standard.
- `__STDC_HOSTED__`: If set to 1, it indicates that the compiler provides a complete standard library; otherwise, it is set to 0 (embedded systems often have incomplete standard libraries).
- `__STDC_VERSION__`: The version of the C language being used for compilation, formatted as a long integer, with C99 being "199901L", C11 being "201112L", and C17 being "201710L".

Here's an example that prints the values of these predefined macros:

```c
#include <stdio.h>

int main(void) 
{
  printf("This function: %s\n", __func__);
  printf("This file: %s\n", __FILE__);
  printf("This line: %d\n", __LINE__);
  printf("Compiled on: %s %s\n", __DATE__, __TIME__);
  printf("C Version: %ld\n", __STDC_VERSION__);
}

/* Output:

This function: main
This file: test.c
This line: 7
Compiled on: Mar 29 2021 19:19:37
C Version: 201710

*/
```

## `#line`

The `#line` directive is used to override the predefined macro `__LINE__`, setting it to a custom line number. Subsequent lines will be numbered starting from this new value.

```c
// Set the line number for the next line to 300
#line 300
```

In this example, the line number of the line immediately following `#line 300` will be set to 300, and subsequent lines will increment from this number.

The `#line` directive can also be used to change the predefined macro `__FILE__`, setting it to a custom filename.

```c
#line 300 "newfilename"
```

In this example, the line number is set to `300`, and the filename is set to `newfilename`.

## `#error`

The `#error` directive is used to produce a compilation error and stop the compilation process.

```c
#if __STDC_VERSION__ != 201112L
  #error Not C11
#endif
```

In this example, if the compiler is not using the C11 standard, the compilation will stop, and GCC will produce an error message like this:

```sh
$ gcc -std=c99 newish.c
newish.c:14:2: error: #error Not C11
```

This indicates that GCC is compiling with the C99 standard, and the error directive has been triggered.

```c
#if INT_MAX < 100000
  #error int type is too small
#endif
```

In this example, the compilation will be stopped if the maximum value of the `int` type is less than `100,000`.

The `#error` directive can also be used in `#if...#elif...#else` blocks.

```c
#if defined WIN32
  // ...
#elif defined MAC_OS
  // ...
#elif defined LINUX
  // ...
#else
  #error NOT support the operating system
#endif
```

This example uses `#error` to generate an error if none of the defined macros match, indicating that the operating system is not supported.

## `#pragma`

The `#pragma` directive is used to modify compiler properties and behaviors.

```c
// Use C99 standard
#pragma c9x on
```

This example instructs the compiler to use the C99 standard. Note that `#pragma` directives are compiler-specific, and the exact syntax and available pragmas can vary between different compilers.

# 17. I/O Functions

C provides several functions for communication with external devices, known as input/output functions, abbreviated as I/O functions. Input refers to acquiring external data, while output refers to transmitting data to the external environment.

## Buffering and Byte Streams

Strictly speaking, I/O functions do not communicate directly with external devices but do so indirectly through buffering. This section explains what buffering is.

Ordinary files are usually stored on disk, and compared to the CPU, disk operations for reading or writing data are much slower. Therefore, directly reading and writing to disk is impractical; each command could potentially take a long time to execute. C's solution is to set up a buffer in memory for a file as soon as it is opened.

When the program writes data to a file, it first puts the data into the buffer, and when the buffer is full, it writes the data to the disk file all at once. At this point, the buffer is empty, and the program can then place new data into the buffer and repeat the process.

When the program reads data from a file, the file first puts a portion of the data into the buffer, then the program retrieves the data from the buffer. Once the buffer is empty, the disk file puts new data into the buffer, repeating the process.

Memory read/write speeds are much faster than disk speeds, and buffering reduces the number of disk read/write operations, significantly improving the program's execution efficiency. Additionally, moving large chunks of data at once is much faster than moving small chunks multiple times.

This read/write pattern resembles a flow of water (stream) for the program; data is not read or written all at once but rather in a continuous process. First, a portion of the data is handled, and once the buffer processes this portion, the next portion is processed. This process is called byte stream operations.

Since the buffer is emptied once read, byte stream reading can only be done once, and subsequent reads are not possible. This is quite different from reading files.

In C, I/O functions involving file read/write operations are all byte stream operations. Input functions get data from files and handle input streams; output functions write data to files and handle output streams.

## printf()

`printf()` is the most commonly used output function for screen output, defined in the header file `stdio.h`, as detailed in the chapter on "Basic Syntax."

## scanf()

### Basic Usage

The `scanf()` function is used to read user input from the keyboard. When the program reaches this statement, it pauses and waits for the user to input data from the keyboard. After the user inputs data and presses Enter, `scanf()` processes the input and stores it in variables. Its prototype is defined in the header file `stdio.h`.

The syntax of `scanf()` is similar to `printf()`.

```c
scanf("%d", &i);
```

The first parameter is a format string that contains placeholders (similar to those in `printf()`) which tell the compiler how to interpret the user's input and what type of data to extract. This is because C data types are specific, and `scanf()` must know the data type in advance to process it. The remaining parameters are variables where the user input will be stored. The number of placeholders in the format string determines how many variables are needed.

In the example above, the first parameter `%d` indicates that the user input should be an integer. `%d` is a placeholder where `%` is the marker and `d` represents an integer. The second parameter `&i` indicates that the integer input by the user should be stored in the variable `i`.

Note that the variable must be preceded by the `&` operator (except for pointer variables) because `scanf()` passes the address of the variable, not its value. If the variable is a pointer (e.g., a string variable), the `&` operator is not needed.

Here is an example of reading multiple variables from keyboard input:

```c
scanf("%d%d%f%f", &i, &j, &x, &y);
```

In the example above, the format string `%d%d%f%f` indicates that the first two inputs are integers and the last two are floating-point numbers, such as `1 -20 3.4 -4.0e3`. These four values are placed into the variables `i`, `j`, `x`, and `y` respectively.

`scanf()` automatically filters out whitespace characters, including spaces, tabs, and newline characters, when processing numerical placeholders. Therefore, multiple spaces between user inputs do not affect `scanf()`'s interpretation of the data. Additionally, user input spread across multiple lines does not affect interpretation.

```c
1
-20
3.4
-4.0e3
```

In the example above, user input spread across four lines produces the same result as if it were input on a single line. Each time Enter is pressed, `scanf()` begins to interpret the input. If the first line matches the first placeholder, the next Enter press will start interpreting from the second placeholder.

The principle of `scanf()` processing user input is that the input is first placed in a buffer. After pressing Enter, `scanf()` interprets the buffer according to the placeholders. When interpreting, `scanf()` starts from the first character remaining from the previous read and continues until the buffer is read or an invalid character is encountered.

```c
int x;
float y;

// User input: "    -13.45e12# 0"
scanf("%d", &x);
scanf("%f", &y);
```

In the example above, `scanf()` reads user input where the `%d` placeholder ignores leading spaces and starts reading from the `-` character, stopping at `-13` because the following `.` is not a valid integer character. Thus, `%d` reads `-13`.

On the second call to `scanf()`, it continues from where it left off. The first character is `.`, and since the placeholder is `%f`, it reads `.45e12`, a scientific notation float. The trailing `#` is not a valid float character, so it stops there.

Since `scanf()` can process multiple placeholders in sequence, the example can also be written as:

```c
scanf("%d%f", &x, &y);
```

The return value of `scanf()` is an integer representing the number of successfully read variables. If no items were read or a match fails, it returns `0`. If the end of the file is reached, it returns the constant EOF.

### Placeholders

Common placeholders for `scanf()` are as follows, and they are mostly consistent with those used in `printf()`:

- `%c`: Character.
- `%d`: Integer.
- `%f`: `float` type floating-point number.
- `%lf`: `double` type floating-point number.
- `%Lf`: `long double` type floating-point number.
- `%s`: String.
- `%[]`: Specifies a set of matching characters in square brackets (e.g., `%[0-9]`), stopping the match when a character not in the set is encountered.

Of these placeholders, all except `%c` automatically ignore leading whitespace characters. `%c` does not ignore whitespace and always returns the current first character, regardless of whether it is a space. To skip whitespace characters before `%c`, use `scanf(" %c", &ch)`, where a space before `%c` indicates that zero or more whitespace characters should be skipped.

Special attention is needed for the `%s` placeholder. It does not simply represent a string but rather reads from the first non-whitespace character until it encounters a whitespace character (i.e., space, newline, tab, etc.). Since `%s` does not include whitespace characters, it cannot be used to read multiple words unless multiple `%s` are used together. This means `scanf()` is not suitable for reading strings that might contain spaces, such as book or song titles. Additionally, `scanf()` appends a null character `\0` to the end of the string variable.

When using `%s` to read a string into a character array, `scanf()` does not check if the string exceeds the array's length, which can lead to unexpected results due to buffer overflow. To prevent this, specify the maximum length of the string when using `%s` by writing `%[m]s`, where `[m]` is an integer indicating the maximum length of the string, with excess characters being discarded.

```c
char name[11];
scanf("%10s", name);
```

In the example above, `name` is a character array of length 11, and the `%10s` placeholder ensures that at most 10 characters are read from the user input, reducing the risk of buffer overflow.

### Assignment Suppression Character

Sometimes, user input might not match the expected format.

```c
scanf("%d-%d-%d", &year, &month, &day);
```

In the example above, if the user inputs `2020-01-01`, the year, month, and day will be correctly parsed. However, if the user inputs another format like `2020/01/01`, `scanf()` will fail to parse the data.

To handle such cases, `scanf()` provides an assignment suppression character `*`. By placing `*` after the percent sign in any placeholder, that placeholder will not return a value and will be discarded after parsing.

```c
scanf("%d%*c%d%*c%d", &year, &month, &day);
```

In the example above, `%*c` includes the assignment suppression character `*` after the percent sign, indicating that this placeholder does not correspond to a variable and should be discarded after parsing.

## sscanf()

The `sscanf()` function is similar to `scanf()`, except that `sscanf()` reads data from a string rather than from user input. Its prototype is defined in the `stdio.h` header file.

```c
int sscanf(const char* s, const char* format, ...);
```

The first parameter of `sscanf()` is a pointer to a string from which data is to be extracted. The other parameters are the same as those for `scanf()`.

`sscanf()` is mainly used to extract data from a string obtained from other input functions.

```c
fgets(str, sizeof(str), stdin);
sscanf(str, "%d%d", &i, &j);
```

In the example above, `fgets()` first reads a line of data from standard input (detailed in the next chapter) into the character array `str`. Then, `sscanf()` extracts two integers from the string `str` and stores them in variables `i` and `j`.

One advantage of `sscanf()` is that its data source is not stream data, so it can be reused multiple times, unlike `scanf()` which reads data from a stream and can only read once.

The return value of `sscanf()` is the number of successfully assigned variables. If extraction fails, it returns the constant EOF.

## getchar(), putchar()

**(1) `getchar()`**

The `getchar()` function returns a single character input by the user from the keyboard, with no parameters. The program pauses at this command, waiting for user input, similar to using `scanf()` to read a single character. Its prototype is defined in the `stdio.h` header file.

```c
char ch;
ch = getchar();

// Equivalent to
scanf("%c", &ch);
```

`getchar()` does not ignore leading whitespace characters and always returns the first character read, regardless of whether it is a space. If reading fails, it returns the constant EOF. Since EOF is usually `-1`, the return type should be `int` rather than `char`.

Since `getchar()` returns the read character, it can be used in loop conditions.

```c
while (getchar() != '\n')
  ;
```

In the example above, the loop continues until a newline character (`\n`) is read, commonly used to skip a line. The `while` loop body has no statements, meaning no operation is performed on that line.

The following example calculates the length of a line.

```c
int len = 0;
while(getchar() != '\n')
  len++;
```

In this example, `getchar()` increments the length variable `len` by 1 for each character read until a newline is encountered, at which point `len` represents the length of the line.

The following example skips space characters.

```c
while ((ch = getchar()) == ' ')
  ;
```

In this example, after the loop, the variable `ch` holds the first non-space character.

**(2) `putchar()`**

The `putchar()` function outputs its character parameter to the screen, equivalent to using `printf()` to output a single character. Its prototype is defined in the `stdio.h` header file.

```c
putchar(ch);
// Equivalent to
printf("%c", ch);
```

On success, `putchar()` returns the character output; otherwise, it returns the constant EOF.

**(3) Summary**

Since `getchar()` and `putchar()` are simpler and usually implemented as macros, they are generally faster than `scanf()` and `printf()`. If you are dealing with individual characters, it is recommended to use these functions.

## puts()

The `puts()` function displays a string on the screen (stdout) and automatically appends a newline character at the end of the string. Its prototype is defined in the `stdio.h` header file.

```c
puts("Here are some messages:");
puts("Hello World");
```

In the example above, `puts()` outputs two lines of content on the screen.

On successful write, `puts()` returns a non-negative integer; otherwise, it returns the constant EOF.

## gets()

The `gets()` function was used to read a full line of input from `stdin`, but it has been deprecated and is no longer recommended. It is still mentioned here for reference.

This function reads a line of user input, does not skip leading whitespace, and continues until a newline character is encountered. The function discards the newline character, stores the remaining characters in the parameter variable, and appends a null character `\0` at the end to form a string.

It is often used in conjunction with `puts()`.

```c
char words[81];

puts("Enter a string, please");
gets(words);
```

In the example above, `puts()` displays a prompt on the screen, and then `gets()` reads the user's input.

Due to the risk of buffer overflow, as `gets()` may exceed the maximum length of the character array, it is recommended to use `fgets()` instead.

# 18. File Operations

This chapter introduces how C language handles file operations.

## File Pointer

C language provides a FILE data structure that records the information needed to operate a file. This structure is defined in the header file `stdio.h`, and all file operation functions use this structure to obtain file information.

Before starting to operate on a file, a FILE pointer must be defined, which is like acquiring a memory area to store file information.

```c
FILE* fp;
```

The example above defines a FILE pointer `fp`.

Here is a complete example of reading a file.

```c
#include <stdio.h>

int main(void) 
{
  FILE* fp;
  char c;

  fp = fopen("hello.txt", "r");
  if (fp == NULL) 
  {
    return -1;
  }

  c = fgetc(fp);
  printf("%c\n", c);

  fclose(fp);

  return 0;
}
```

In the example above, after creating the file pointer `fp`, three file operation functions are used in sequence, divided into three steps. Other file operations are generally similar in steps.

The first step is to use `fopen()` to open the specified file and return a File pointer. If an error occurs, it returns NULL.

It associates the specified file information with the newly created file pointer `fp`, and records information in the FILE structure such as: the current read/write position within the file, error records for read/write operations, end-of-file indicator, pointer to the start of the buffer, file identifier, a counter (counting the number of bytes copied into the buffer), etc. Subsequent operations can use this pointer (instead of the file name) to handle the specified file.

At the same time, it establishes a buffer for the file. Because there is a buffer, it can also be said that `fopen()` function "opens a stream", and subsequent read/write operations are in stream mode.

The second step is to use read/write functions to read data from the file or write data to the file. The example uses `fgetc()` function to read a character from the already opened file.

When `fgetc()` is called, a block of file data is first copied to the buffer. Different computers have different buffer sizes, generally 512 bytes or multiples of it, such as 4096 or 16384. As computer hard disk capacities increase, buffer sizes also increase.

`fgetc()` reads data from the buffer, while moving the read/write position indicator in the file pointer to the next character after the read character. All file reading functions use the same buffer, so any subsequent reading function will start reading from the position indicated by the pointer, i.e., the position where the last reading function stopped.

When the reading function finds that all characters in the buffer have been read, it will request to copy the next block of data the size of the buffer from the file into the buffer. The reading function reads all the content of the file in this way until the end of the file. However, the example only reads one character from the buffer. When the function reads the last character in the buffer, it sets the end-of-file indicator in the FILE structure to true. Therefore, the next time a reading function is called, it will return the constant EOF. EOF is an integer value representing the end of the file, usually `-1`.

The third step is to use `fclose()` to close the file and clear the buffer.

The above process is for reading files, and writing files follows a similar approach, where data is first written to the buffer, and when the buffer is full, the buffer data is transferred to the file.

## fopen()

The `fopen()` function is used to open files. The first step in all file operations is to use `fopen()` to open the specified file. The prototype of this function is defined in the header file `stdio.h`.

```c
FILE* fopen(char* filename, char* mode);
```

It accepts two parameters. The first parameter is the file name (which can include the path), and the second parameter is the mode string that specifies the operation to perform on the file. For example, in the following example, `r` means opening the file in read mode.

```c
fp = fopen("in.dat", "r");
```

Upon successfully opening the file, `fopen()` returns a FILE pointer, which other functions can use to operate on the file. If the file cannot be opened (e.g., if it does not exist or permission is denied), it returns a NULL pointer. Therefore, it is best to check whether the file was opened successfully after calling `fopen()`.

```c
fp = fopen("hello.txt", "r");

if (fp == NULL) 
{
  printf("Can't open file!\n");
  exit(EXIT_FAILURE);
}
```

In the example above, if `fopen()` returns a NULL pointer, the program will report an error.

The mode string for `fopen()` can be one of the following:

- `r`: Read mode, only used for reading data. Returns NULL if the file does not exist.
- `w`: Write mode, only used for writing data. If the file exists, its length will be truncated to 0 and then written to; if the file does not exist, it will be created.
- `a`: Write mode, only used for appending data to the end of the file. If the file does not exist, it will be created.
- `r+`: Read and write mode. If the file exists, the pointer points to the beginning of the file, and data can be added at the start. If the file does not exist, it returns a NULL pointer.
- `w+`: Read and write mode. If the file exists, its length will be truncated to 0 and then written to. This mode effectively erases the data rather than reading it. If the file does not exist, it will be created.
- `a+`: Read and write mode. If the file exists, the pointer points to the end of the file, and content can be added at the end. If the file does not exist, it will be created.

As mentioned in the previous section, `fopen()` creates a buffer for the opened file. In read mode, a read buffer is created; in write mode, a write buffer is created; in read/write mode, both buffers are created. C language handles file I/O using these buffers in stream mode.

Data in files is stored in binary form. However, when reading, there are different interpretation methods: interpreting in the original binary form is called "binary stream"; converting binary data to text and interpreting it in text form is called "text stream." Writing operations are similar, divided into binary writing and text writing, with the latter including a text-to-binary conversion step.

The mode string for `fopen()` defaults to text stream reading/writing. Adding a `b` suffix (for binary) will handle it as a "binary stream." For example, `rb` is for reading binary data, and `wb` is for writing binary data.

The mode string can also have an `x` suffix for exclusive mode. If the file already exists, opening the file fails; if the file does not exist, it creates the file and disallows other programs or threads from accessing the file. For example, `wx` represents exclusive mode for writing to a file; if the file already exists, opening it fails.

## Standard Streams

Linux systems provide three pre-opened files by default, with the following file pointers:

- `stdin` (standard input): Default source is the keyboard, file pointer number is `0`.
- `stdout` (standard output): Default destination is the display, file pointer number is `1`.
- `stderr` (standard error): Default destination is the display, file pointer number is `2`.

In Linux, files are not limited to data files but can also be device files, which represent a device that can be read from or written to. The file pointer `stdin` defaults to treating the keyboard as a file, so reading from this file provides user keyboard input. Similarly, `stdout` and `stderr` default to treating the display as a file, writing the program's results to this file so the user can see the results. The difference is that `stdout` writes normal program output, while `stderr` writes error messages.

These three input and output channels are provided by default in Linux and are referred to as standard input (`stdin`), standard output (`stdout`), and standard error (`stderr`). Since their implementation is the same and they are all file streams, they are collectively known as "standard streams."

Linux allows changing the files that these three file pointers (streams) point to, which is known as redirection.

If standard input is not bound to the keyboard but to another file, you can place a less-than sign `<` before the file name after the program name. This is called "input redirection."

```c
$ demo < in.dat
```

In the example above, `stdin` in the `demo` program will point to the file `in.dat`, meaning data is read from `in.dat`.

If standard output is bound to another file instead of the display, you can place a greater-than sign `>` before the file name after the program name. This is called "output redirection."

```c
$ demo > out.dat
```

In the example above, `stdout` in the `demo` program will point to the file `out.dat`, meaning data is written to `out.dat`.

Output redirection `>` will first erase all existing content in `out.dat` and then write to it. If you want to append information to the end of `out.dat`, use the `>>` symbol.

```c
$ demo >> out.dat
```

In the example above, `stdout` in the `demo` program will write to the file `out.dat`, with the writing starting at the end of the file.

The redirection symbol for standard error is `2>`, where `2` represents the file pointer number, i.e., `2>` indicates redirecting the write operation of file pointer number 2 to `err.txt`. File pointer number 2 is standard error `stderr`.

```c
$ demo > out.dat 2> err.txt
```

In the example above, `stderr` in the `demo` program will write error messages to `err.txt`, while `stdout` will write to `out.dat`.

Input and output redirections can also be combined in a single command.

```c
$ demo < in.dat > out.dat

// or
$ demo > out.dat < in.dat
```

Another type of redirection is to point the standard output `stdout` of one program to the standard input `stdin` of another program, using the `|` symbol.

```c
$ random | sum
```

In the example above, the `stdout` of the `random` program will be read by the `stdin` of the `sum` program.

## fclose()

The `fclose()` function is used to close a file that was opened using `fopen()`. Its prototype is defined in `stdio.h`.

```c
int fclose(FILE* stream);
```

It takes a file pointer `fp` as a parameter. If the file is successfully closed, `fclose()` returns an integer `0`; if the operation fails (e.g., due to a full disk or an I/O error), it returns a special value EOF (see the next section).

```c
if (fclose(fp) != 0)
  printf("Something wrong.");
```

Files that are no longer in use should be closed using `fclose()` to release resources. Generally, systems have a limit on the number of files that can be opened simultaneously, so closing files promptly helps avoid exceeding this limit.

## EOF

In C, file operation functions are designed to return a special value when the end of the file is reached. When the program receives this special value, it knows that the end of the file has been reached.

The header file `stdio.h` defines a macro `EOF` (End of File) for this special value, which is generally `-1`. This is because, whether interpreted as an unsigned number or as an ASCII code, the binary value read from the file cannot be negative, so returning `-1` is safe and will not conflict with the file's data.

Note that, unlike the end of a string which stores the value `\0`, `EOF` is not stored at the end of the file. The file itself does not contain this value; it is merely returned by file operation functions when they detect the end of the file.

## freopen()

The `freopen()` function is used to open a new file and associate it with an already open file pointer. This allows for reusing file pointers. Its prototype is defined in `stdio.h`.

```c
FILE* freopen(char* filename, char* mode, FILE* stream);
```

It has a third parameter compared to `fopen()`, which specifies the file pointer to be reused. The other two parameters are the file name and the mode for opening.

```c
freopen("output.txt", "w", stdout);
printf("hello");
```

In the example above, the file `output.txt` is associated with `stdout`. Henceforth, any content written to `stdout` will go to `output.txt`. Since `printf()` by default writes to `stdout`, running this code will write `hello` to `output.txt`.

The return value of `freopen()` is its third parameter (file pointer). If the open operation fails (e.g., if the file does not exist), it will return a NULL pointer.

`freopen()` will automatically close the previously opened file. If the file pointer does not point to an already open file, `freopen()` behaves like `fopen()`.

Here is an example of `freopen()` used with `scanf()`:

```c
int i, i2;

scanf("%d", &i); 

freopen("someints.txt", "r", stdin);
scanf("%d", &i2);
```

In the example above, `scanf()` is called twice. The first call reads from the keyboard, then `freopen()` associates the `stdin` pointer with a file. The second call will read from that file.

Some systems allow using `freopen()` to change the open mode of a file. In this case, the first parameter of `freopen()` should be NULL.

```c
freopen(NULL, "wb", stdout);
```

In the example above, the open mode of `stdout` is changed from `w` to `wb`.

## fgetc() and getc()

`fgetc()` and `getc()` are used to read a single character from a file. They are similar to `getchar()`, but whereas `getchar()` reads from `stdin`, these two functions read from any specified file. Their prototypes are defined in `stdio.h`.

```c
int fgetc(FILE *stream);
int getc(FILE *stream);
```

`fgetc()` and `getc()` have the same usage, taking only a file pointer as a parameter. The difference is that `getc()` is generally implemented as a macro, whereas `fgetc()` is implemented as a function, so the former may have better performance. Note that although these functions return a character, their return type is `int`, not `char`, because they return `EOF` in case of failure, which is typically `-1`.

```c
#include <stdio.h>

int main(void) 
{
  FILE *fp;
  fp = fopen("hello.txt", "r");

  int c;
  while ((c = getc(fp)) != EOF)
    printf("%c", c);

  fclose(fp);
}
```

In the example above, `getc()` reads each character from the file into the variable `c` until it reaches the end of the file, returning `EOF` to terminate the loop. The variable `c` is of type `int` rather than `char` because it might hold a negative value, making `int` a better choice.

## fputc() and putc()

`fputc()` and `putc()` are used to write a single character to a file. They are similar to `putchar()`, but whereas `putchar()` writes to `stdout`, these functions write to a file. Their prototypes are defined in `stdio.h`.

```c
int fputc(int char, FILE *stream);
int putc(int char, FILE *stream);
```

`fputc()` and `putc()` function the same way, taking two parameters: the character to be written and the file pointer. The difference is that `putc()` is usually implemented as a macro, while `fputc()` is implemented as a function, so theoretically, `putc()` might be slightly faster.

On success, they return the character written; on failure, they return `EOF`.

## fprintf()

`fprintf()` is used to write formatted strings to a file, similar to `printf()`. The difference is that `printf()` always writes to `stdout`, while `fprintf()` writes to a specified file, and its first parameter must be a file pointer. Its prototype is defined in `stdio.h`.

```c
int fprintf(FILE* stream, const char* format, ...);
```

`fprintf()` can replace `printf()`.

```c
printf("Hello, world!\n");
fprintf(stdout, "Hello, world!\n");
```

In the example above, `fprintf()` writing to `stdout` is equivalent to calling `printf()`.

```c
fprintf(fp, "Sum: %d\n", sum);
```

In this example, a formatted string is written to the file pointer `fp`.

Here is an example of outputting error messages to `stderr`.

```c
fprintf(stderr, "Something number.\n");
```

## fscanf()

`fscanf()` is used to read data from a file according to a specified format, similar to `scanf()`. The difference is that while `scanf()` always reads from `stdin`, `fscanf()` reads from a specified file. Its prototype is defined in `stdio.h`, and the first parameter must be a file pointer.

```c
int fscanf(FILE* stream, const char* format, ...);
```

Here's an example:

```c
fscanf(fp, "%d%d", &i, &j);
```

In this example, `fscanf()` reads two integers from the file `fp` and stores them in the variables `i` and `j`.

When using `fscanf()`, it's essential to know the file's structure, as its placeholder parsing rules are identical to `scanf()`. `fscanf()` can read continuously until it reaches the end of the file or encounters an error (such as a read failure or a matching failure), so it's often used in a loop.

```c
while(fscanf(fp, "%s", words) == 1)
  puts(words);
```

In this example, `fscanf()` reads each word from the file and prints it line by line until the end of the file.

`fscanf()` returns the number of successfully assigned variables; if it fails to assign values, it returns `EOF`.

## fgets()

`fgets()` is used to read a specified length of string from a file. The first character of its name, `f`, stands for `file`. Its prototype is defined in `stdio.h`.

```c
char* fgets(char* str, int STRLEN, FILE* fp);
```

The first parameter `str` is a string pointer used to store the read content. The second parameter `STRLEN` specifies the length to read, and the third parameter is a `FILE` pointer pointing to the file to be read.

`fgets()` stops reading after `STRLEN - 1` characters or when it encounters a newline or the end of the file. It then appends a null character (`\0`) to the end of the read content to make it a valid string. Note that `fgets()` will store the newline character (`\n`) in the string if it is encountered.

If the third parameter of `fgets` is `stdin`, it reads from standard input, similar to `scanf()`.

```c
fgets(str, sizeof(str), stdin);
```

When successful, `fgets()` returns its first parameter, which is a pointer to the string; otherwise, it returns `NULL`.

`fgets()` can be used to read each line of a file. Here’s an example of reading all lines from a file:

```c
#include <stdio.h>

int main(void) 
{
  FILE* fp;
  char s[1024];  // Array must be large enough to hold a line
  int linecount = 0;

  fp = fopen("hello.txt", "r");

  while (fgets(s, sizeof s, fp) != NULL)
    printf("%d: %s", ++linecount, s);

  fclose(fp);
}
```

In this example, each line is read and printed with its line number.

Here’s an example of looping to read user input:

```c
char words[10];

puts("Enter strings (q to quit):");

while (fgets(words, 10, stdin) != NULL) 
{
  if (words[0] == 'q' && words[1] == '\n')
    break;

  puts(words);
}

puts("Done.");
```

In this example, if the user inputs a string longer than 9 characters, `fgets()` will read it multiple times until encountering `q` followed by the Enter key, at which point the loop will exit.

## fputs()

The `fputs()` function is used to write a string to a file. Unlike `puts()`, `fputs()` does not append a newline character at the end of the string. This is because `fgets()` retains newline characters, so `fputs()` omits them. `fputs()` is typically used in conjunction with `fgets()`.

Its prototype is defined in `stdio.h`.

```c
int fputs(const char* str, FILE* stream);
```

It takes two parameters:
- The first parameter is a string pointer to the content to be written.
- The second parameter is the file pointer indicating where to write the content.

If the second parameter is `stdout` (standard output), the content is written to the screen, similar to `printf()`.

```c
char words[14];

puts("Enter a string, please.");
fgets(words, 14, stdin);

puts("This is your string:");
fputs(words, stdout);
```

In this example, `fgets()` reads user input from `stdin`, and then `fputs()` writes the string to `stdout`.

On successful write, `fputs()` returns a non-negative integer; otherwise, it returns `EOF`.

## fwrite()

The `fwrite()` function is used to write large blocks of data at once, making it suitable for writing arrays or binary data to a file. Its prototype is defined in `stdio.h`.

```c
size_t fwrite(const void* ptr,
  			  size_t size,
  			  size_t nmemb,
  			  FILE* fp
			  );
```

It takes four parameters:
- `ptr`: Pointer to the array of data.
- `size`: Size of each element in bytes.
- `nmemb`: Number of elements.
- `fp`: File pointer to write the data to.

Note that the first parameter of `fwrite()` is of type `void*`, which is a generic pointer. The function does not know the type of data being pointed to, so you must specify the size of each element and the number of elements.

The return value of `fwrite()` is the number of successfully written elements (not bytes). Normally, this value equals the `nmemb` parameter, but if an error occurs, the return value may be smaller.

To write an entire array `arr` to a file, use:

```c
fwrite(arr,
  	   sizeof(arr[0]),
       sizeof(arr) / sizeof(arr[0]),
  	   fp
	   );
```

Here, `sizeof(arr[0])` is the size of each element, and `sizeof(arr) / sizeof(arr[0])` is the number of elements in the array.

Here’s an example of writing a 256-byte string to a file:

```c
char buffer[256];

fwrite(buffer, 1, 256, fp);
```

In this example, each element in the array `buffer` is 1 byte, and there are 256 elements. The same result can be achieved with `fwrite(buffer, 256, 1, fp)` due to contiguous memory copying.

`fwrite()` does not require writing the entire array; you can write part of it as well. Any type of data can be considered as an array of 1-byte elements, or as a single-element array, so `fwrite()` can write any type of data, not just arrays. For example, you can write a `struct` to a file:

```c
fwrite(&s, sizeof(s), 1, fp);
```

Here, `s` is a `struct` that can be viewed as a single-element array. Note that if the `struct` contains pointers, you need to be cautious, as storing pointers might not be meaningful, and the data they point to might not be restored correctly.

`fwrite()` and `fread()`, which will be discussed next, are suitable for reading and writing binary data because they do not interpret the data. Binary data might include null characters (`\0`), which are used as string terminators in C, so text I/O functions (like `fprintf()`) are not appropriate for binary file operations.

Here’s an example of writing a binary file:

```c
#include <stdio.h>

int main(void)
{
  FILE* fp;
  unsigned char bytes[] = {5, 37, 0, 88, 255, 12};

  fp = fopen("output.bin", "wb");
  fwrite(bytes, sizeof(char), sizeof(bytes), fp);
  fclose(fp);
  return 0;
}
```

In this example, when writing a binary file, `fopen()` uses the `wb` mode for binary writing. `fwrite()` can interpret the data as a contiguous byte array, so its second parameter is `sizeof(char)`, and the third parameter is the total number of bytes in the array.

The file `output.bin` written by the above example, when opened with a hex editor, will display:

```c
05 25 00 58 ff 0c
```

`fwrite()` can also be used to write data continuously to a file:

```c
struct clientData myClient = {1, 'foo bar'};

for (int i = 1; i <= 100; i++) 
{
  fwrite(&myClient, sizeof(struct clientData), 1, cfPtr);
}
```

In this example, `fwrite()` writes 100 records of data to a file.

## fread()

The `fread()` function is used to read large blocks of data from a file at once, making it suitable for reading binary data into an array. Its prototype is defined in `stdio.h`.

```c
size_t fread(void* ptr,
  			 size_t size,
  			 size_t nmemb,
  		     FILE* fp
			 );
```

It takes four parameters, similar to `fwrite()`:

- `ptr`: Address of the array where the data will be stored.
- `size`: Size of each array element in bytes.
- `nmemb`: Number of elements to read.
- `fp`: File pointer from which to read the data.

To read the contents of a file into an array `arr`, you can use the following code:

```c
fread(arr,
  	  sizeof(arr[0]),
  	  sizeof(arr) / sizeof(arr[0]),
  	  fp
	  );
```

In this example, the product of the size of each element (the second parameter) and the number of elements (the third parameter) equals the total amount of memory to be read. `fread()` reads this amount of data from the file (the fourth parameter) and stores it in the memory location pointed to by `ptr` (the first parameter).

Here is an example that reads the contents of a file into an array of 10 `double` values:

```c
double earnings[10];
fread(earnings, sizeof(double), 10, fp);
```

In this case, each array element is of size `sizeof(double)`, so `fread()` reads `sizeof(double) * 10` bytes from the file `fp`.

The return value of `fread()` is the number of elements successfully read. Normally, this value equals the third parameter `nmemb`, but if an error occurs or the end of the file is reached, the return value will be less. Therefore, it is crucial to check the return value of `fread()`.

`fread()` and `fwrite()` can be used together to save data to a file and later restore it. Here is an example of reading the binary file `output.bin` created in the previous section:

```c
#include <stdio.h>

int main(void) 
{
  FILE* fp;
  unsigned char c;

  fp = fopen("output.bin", "rb");
  while (fread(&c, sizeof(char), 1, fp) > 0)
    printf("%d\n", c);
  fclose(fp);
  return 0;
}
```

When run, this program will output:

```c
5
37
0
88
255
12
```

## feof()

The `feof()` function checks if the file's internal pointer is at the end of the file. Its prototype is defined in `stdio.h`.

```c
int feof(FILE *fp);
```

`feof()` takes a file pointer as a parameter. If the end of the file has been reached, it returns a non-zero value (true); otherwise, it returns `0` (false).

Functions like `fgetc()` that read from files may return `EOF` for two reasons: reaching the end of the file or encountering a read error. `feof()` can be used to distinguish between these cases.

Here is an example that uses `feof()` to determine if the end of the file has been reached and thus read the entire file:

```c
int num;
char name[50];

FILE* cfPtr = fopen("clients.txt", "r");

while (!feof(cfPtr)) 
{
  fscanf(cfPtr, "%d%s\n", &num, name);
  printf("%d %s\n", num, name);
}

fclose(cfPtr);
```

In this example, the loop checks `feof()` to see if the end of the file has been reached, thus enabling it to read and output the entire file contents.

When `feof()` returns true, you can use functions like `fseek()`, `rewind()`, or `fsetpos()` to reposition the file's internal read/write indicator and clear the end-of-file state.

## fseek()

The `fseek()` function is used to move the file pointer to a specified position within a file. It is useful for random access within a file. Its prototype is defined in `stdio.h`.

```c
int fseek(FILE* stream, long int offset, int whence);
```

It takes three parameters:

- `stream`: The file pointer.
- `offset`: The number of bytes to move relative to the position specified by `whence`. This value can be positive (to move forward), negative (to move backward), or zero (to remain in place). It is of type `long int`.
- `whence`: The reference position from which the offset is calculated. It can be one of the following three constants (defined in `stdio.h`):
  - `SEEK_SET`: Beginning of the file.
  - `SEEK_CUR`: Current position of the file pointer.
  - `SEEK_END`: End of the file.

Here are some examples:

```c
// Move to the beginning of the file
fseek(fp, 0L, SEEK_SET);

// Move to the end of the file
fseek(fp, 0L, SEEK_END);

// Move 2 bytes forward from the current position
fseek(fp, 2L, SEEK_CUR);

// Move to the 10th byte from the beginning of the file
fseek(fp, 10L, SEEK_SET);

// Move to the 10th byte from the end of the file
fseek(fp, -10L, SEEK_END);
```

In these examples, the `offset` must be specified as a `long` type, hence the suffix `L` is used to ensure the value is treated as `long`.

Here’s an example that outputs the bytes of a file in reverse order:

```c
for (count = 1L; count <= size; count++) 
{
  fseek(fp, -count, SEEK_END);
  ch = getc(fp);
  putchar(ch); // Output the character
}
```

Note that `fseek()` is best used with binary files. For text files, where characters may have different encodings and byte positions might not be easily determined, using `fseek()` can be problematic.

Normally, `fseek()` returns 0 on success. If an error occurs (such as trying to move beyond the file's boundaries), it returns a non-zero value (e.g., `-1`).

## ftell()

The `ftell()` function returns the current position of the file pointer within a file. Its prototype is defined in `stdio.h`.

```c
long int ftell(FILE* stream);
```

It takes one parameter:

- `stream`: The file pointer.

The return value is a `long int` representing the number of bytes from the beginning of the file to the current position. A return value of `0` indicates the beginning of the file. If an error occurs, `ftell()` returns `-1L`.

`ftell()` is often used with `fseek()` to record the current position and return to it later.

```c
long file_pos = ftell(fp);

// Perform a series of file operations
fseek(fp, file_pos, SEEK_SET);
```

Here’s an example that moves the file pointer to the end of the file and then obtains the size of the file:

```c
fseek(fp, 0L, SEEK_END);
size = ftell(fp);
```

In this example, `ftell()` is used to determine the size of the file by moving the file pointer to the end and then measuring the position.

## rewind()

The `rewind()` function returns the file's internal pointer to the beginning of the file. Its prototype is defined in `stdio.h`.

```c
void rewind(FILE* stream);
```

It takes a file pointer as its parameter.

`rewind(fp)` is essentially equivalent to `fseek(fp, 0l, SEEK_SET)`, with the only difference being that `rewind()` does not return a value and clears the current file's error indicator.

## fgetpos(), fsetpos()

A potential issue with `fseek()` and `ftell()` is that they limit the file size to the range that can be represented by a `long int`. This may seem large, but on a 32-bit system, a `long int` is 4 bytes long and can represent a maximum of 4GB. With storage devices growing rapidly, files are also getting larger and may exceed this range. To address this, C introduced two new functions for handling large files: `fgetpos()` and `fsetpos()`.

Their prototypes are defined in the header file `stdio.h`.

```c
int fgetpos(FILE* stream, fpos_t* pos);
int fsetpos(FILE* stream, const fpos_t* pos);
```

The `fgetpos()` function stores the current position of the file's internal pointer in the variable `pos`. It takes two parameters: the file pointer and the variable to store the pointer's position.

The `fsetpos()` function moves the file's internal pointer to the position specified by the variable `pos`. Note that `pos` must be obtained by calling `fgetpos()`. The parameters for `fsetpos()` must be the same as those for `fgetpos()`.

The pointer variable `pos` that records the file's internal pointer position has the type `fpos_t*` (short for file position type). It may not necessarily be an integer; it could also be a struct.

Here is an example usage.

```c
fpos_t file_pos;
fgetpos(fp, &file_pos);

// After a series of file operations
fsetpos(fp, &file_pos);
```

In the example above, `fgetpos()` retrieves the internal pointer position, and `fsetpos()` later restores the pointer's position.

On success, both `fgetpos()` and `fsetpos()` return `0`; otherwise, they return a non-zero value.

## ferror(), clearerr()

If a file operation function fails, it records the error status in the file pointer. Subsequent operations can check the error indicator to determine if the previous operation failed.

The `ferror()` function returns the status of the error indicator. It allows you to check if the previous file operation succeeded. Its prototype is defined in the header file `stdio.h`.

```c
int ferror(FILE *stream);
```

It takes a file pointer as its parameter. If the previous operation failed, `ferror()` returns a non-zero integer (true); otherwise, it returns `0`.

The `clearerr()` function resets the error indicator. Its prototype is defined in the header file `stdio.h`.

```c
void clearerr(FILE* fp);
```

It takes a file pointer as its parameter and does not return a value.

Here is an example.

```c
FILE* fp = fopen("file.txt", "w");
char c = fgetc(fp);

if (ferror(fp)) 
{
  printf("Error reading file: file.txt\n");
}

clearerr(fp);
```

In the example above, `fgetc()` attempts to read a file opened in "write mode", which will fail and return EOF. At this point, calling `ferror()` can determine that the previous operation failed. After handling it, use `clearerr()` to clear the error status.

If file operation functions execute normally, both `ferror()` and `feof()` return zero. If there is an issue, determine what went wrong.

```c
if (fscanf(fp, "%d", &n) != 1) 
{
  if (ferror(fp)) 
  {
    printf("I/O error\n");
  }
  if (feof(fp)) 
  {
    printf("End of file\n");
  }

  clearerr(fp);

  fclose(fp);
}
```

In the example above, when the `fscanf()` function reports an error, check `ferror()` and `feof()` to determine what went wrong. These indicators retain their state after they change, so use `clearerr()` to clear them; `clearerr()` can clear both indicators simultaneously.

## remove()

The `remove()` function is used to delete a specified file. Its prototype is defined in the header file `stdio.h`.

```c
int remove(const char* filename);
```

It takes the filename as a parameter. If the deletion is successful, `remove()` returns `0`; otherwise, it returns a non-zero value.

```c
remove("foo.txt");
```

The example above deletes the file `foo.txt`.

Note that the file must be closed before it can be deleted. If the file was opened with `fopen()`, it must be closed with `fclose()` before deletion.

## rename()

The `rename()` function is used to rename files and also to move files. Its prototype is defined in the header file `stdio.h`.

```c
int rename(const char* old_filename, const char* new_filename);
```

It takes two parameters: the current filename and the new filename. If the renaming is successful, `rename()` returns `0`; otherwise, it returns a non-zero value.

```c
rename("foo.txt", "bar.txt");
```

The example above renames `foo.txt` to `bar.txt`.

Note that the new filename must not match an existing file name. Additionally, if the file to be renamed is open, it must be closed first; renaming an open file will fail.

Here is an example of moving a file.

```c
rename("/tmp/evidence.txt", "/home/beej/nothing.txt");
```

# 19. Variable Specifiers

In C, you can add specific specifiers when declaring variables to provide additional information about the variable's behavior to the compiler. These specifiers primarily help the compiler optimize the code and can sometimes affect program behavior.

## const

The `const` specifier indicates that the variable is read-only and cannot be modified.

```c
const double PI = 3.14159;
PI = 3; // Error
```

In the example above, `const` means that the value of the variable `PI` should not change. If an attempt is made to change it, the compiler will generate an error.

For arrays, `const` means that the array elements cannot be modified.

```c
const int arr[] = {1, 2, 3, 4};
arr[0] = 5; // Error
```

In the example above, `const` makes the elements of the array `arr` immutable.

For pointer variables, `const` has two different meanings depending on its placement. If `const` is placed before the `*`, it means the value pointed to by the pointer cannot be modified.

```c
// const means the value pointed to by *x cannot be modified
int const * x
// or
const int * x
```

In the following example, modifying the value pointed to by `x` results in an error.

```c
int p = 1;
const int* x = &p;

(*x)++; // Error
```

If `const` is placed after the `*`, it means the pointer itself (the address it holds) cannot be modified.

```c
// const means the address held by x cannot be modified
int* const x
```

In the following example, modifying the pointer `x` results in an error.

```c
int p = 1;
int* const x = &p;

x++; // Error
```

Both usages of `const` can be combined.

```c
const char* const x;
```

In the example above, the pointer variable `x` points to a string. The two `const` specifiers mean that neither the address held by `x` nor the string pointed to by `x` can be modified.

One use of `const` is to prevent modification of function parameters within the function body. If a parameter will not be modified within a function, you can add the `const` specifier to the parameter in the function declaration. This way, users of the function will know from the prototype that the parameter array will remain unchanged before and after the function call.

```c
void find(const int* arr, int n);
```

In the example above, the `const` specifier in the function `find`'s parameter `arr` indicates that the array will remain unchanged within the function.

One important point to note is that if a pointer variable points to a `const` variable, the pointer variable itself should not be modified.

```c
const int i = 1;
int* j = &i;
*j = 2; // Error
```

In the example above, `j` is a pointer variable pointing to the variable `i`, meaning `j` and `i` point to the same address. Although `j` itself does not have the `const` specifier, `i` does. In this case, the value pointed to by `j` (which is `i`) cannot be modified.

## static

The `static` specifier has different meanings for global and local variables.

1. **For Local Variables (within block scope):**

   When used with local variables declared inside a function, `static` means that the variable's value is preserved between function calls. It is initialized only once, and subsequent function calls will use the last value assigned to the variable, similar to a global variable restricted to the function. This can improve execution speed by avoiding repeated initialization.

   ```c
   void func() 
   {
       static int count = 0; // Initialized once
       count++;
       printf("%d\n", count);
   }
   ```

2. **For Global Variables (outside block scope):**

   When used with global variables declared outside functions, `static` means that the variable is only accessible within the current file and cannot be referenced from other source files. This makes the variable non-linkable.

   A `static` variable must be initialized with a constant value, not with another variable.

   ```c
   int n = 10;
   static int m = 20; // Correct
   // static int m = n; // Error
   ```

   A function can also be declared `static` to restrict its use to the current file only, allowing other files to define functions with the same name.

   ```c
   static int g(int i);
   ```

## auto

The `auto` specifier indicates that the variable's storage is automatically allocated by the compiler and exists only within the scope in which it is defined. It is automatically released when exiting the scope.

Since non-`extern` variables are automatically allocated by the compiler, the `auto` specifier has no practical effect and is generally omitted.

```c
auto int a;
// Equivalent to
int a;
```

## extern

The `extern` specifier indicates that the variable is declared in another file and does not need space allocated in the current file. It is used to denote that the variable is shared across multiple files.

```c
extern int a;
```

In the code above, `a` is an `extern` variable, meaning it is defined and initialized in another file, and the current file does not allocate storage for it.

However, if a variable is declared with `extern` and initialized, the `extern` specifier is invalid.

```c
// extern invalid
extern int i = 0;

// Equivalent to
int i = 0;
```

In the code above, the `extern` declaration is invalid because `extern` cannot be used with initialized variables. This prevents multiple `extern` declarations from initializing the same variable multiple times.

When used within a function, `extern` means that the variable behaves as if it has static storage, and its value is retrieved from outside the function.

Functions are `extern` by default, meaning they can be shared with other files, so `extern` is usually omitted. To restrict a function to the current file, use `static` before the function definition.

```c
extern int f(int i);
// Equivalent to
int f(int i);
```

## register

The `register` specifier suggests to the compiler that the variable is frequently used and should be stored in a register for faster access. However, the compiler may ignore this suggestion.

```c
register int a;
```

In the code above, `register` suggests to the compiler that the variable `a` should be stored in a register for faster access.

The `register` specifier only applies to variables declared within a block scope.

Variables declared as `register` cannot have their address taken.

```c
register int a;
int *p = &a; // Error
```

In the code above, `&a` results in an error because `a` might be stored in a register and does not have a memory address.

Arrays cannot be declared as `register`, and their address cannot be obtained.

```c
register int a[] = {11, 22, 33, 44, 55};

int p = a;  // Error
int a = *(a + 2); // Error
```

Historically, CPU caches were called registers. Registers are much faster than memory, so using them can improve performance. However, modern compilers are highly optimized and may ignore the `register` specifier, making their own decisions about register usage.

## volatile

The `volatile` specifier indicates that a variable may change unexpectedly, often due to external factors beyond the control of the program, and thus should not be optimized by the compiler. The compiler should always fetch the variable’s value from its memory location.

```c
volatile int foo;
volatile int* bar;
```

The purpose of `volatile` is to prevent the compiler from optimizing away accesses to the variable. 

```c
int foo = x;
// Other statements, assuming x hasn't changed
int bar = x;
```

In the code above, since `foo` and `bar` are both set to `x`, and `x` hasn’t changed, the compiler might cache `x` and use this cached value for both `foo` and `bar`. If `x` is declared as `volatile`, the compiler will not cache `x` and will fetch its value from memory each time because `x` may be modified by external factors.

## restrict

The `restrict` specifier allows the compiler to optimize certain code by indicating that a pointer is the only way to access the data it points to.

```c
int* restrict pt = (int*) malloc(10 * sizeof(int));
```

In the code above, `restrict` means that `pt` is the only way to access the memory allocated by `malloc`.

The `restrict` specifier cannot be used with variables like `foo` in the following example.

```c
int foo[10];
int* bar = foo;
```

In the code above, the memory pointed to by `foo` can be accessed both through `foo` and `bar`, so `foo` cannot be declared as `restrict`.

When the compiler knows that a block of memory can only be accessed in one way, it can optimize the code better because it does not need to worry about other pointers modifying the value.

When used with function parameters, `restrict` indicates that the memory addresses of the parameters do not overlap.

```c
void swap(int* restrict a, int* restrict b) 
{
  int t;
  t = *a;
  *a = *b;
  *b = t;
}
```

In the code above, `restrict` in the function parameters means that the memory addresses of `a` and `b` do not overlap.

# 20. Introduction to Multi-file Projects

A software project often contains multiple source files, which need to be compiled together to produce an executable file.

Assume a project has two source files, `foo.c` and `bar.c`, where `foo.c` is the main file and `bar.c` is the library file. The "main file" refers to the entry file of the project that contains the `main()` function and will reference various functions defined in the library file.

```c
// File foo.c
#include <stdio.h>

int main(void) 
{
  printf("%d\n", add(2, 3));  // 5!
}
```

In the above code, the main file `foo.c` calls the function `add()`, which is defined in the library file `bar.c`.

```c
// File bar.c

int add(int x, int y) 
{
  return x + y;
}
```

Now, compile these two files together.

```c
$ gcc -o foo foo.c bar.c

# A more convenient way
$ gcc -o foo *.c
```

In the above command, gcc's `-o` parameter specifies the name of the generated binary executable file, in this case, `foo`.

After running this command, the compiler will issue a warning because, during the compilation of `foo.c`, the compiler encounters an unrecognized function `add()`. `foo.c` does not have a prototype or definition for this function. Therefore, it's best to modify `foo.c` to include the prototype of `add()` at the top of the file.

```c
// File foo.c
#include <stdio.h>

int add(int, int);

int main(void) 
{
  printf("%d\n", add(2, 3));  // 5!
}
```

Now, recompiling will not produce any warnings.

You might immediately think that if multiple files use the `add()` function, each file would need to include the function prototype. If the `add()` function needs to be modified (for example, changing the number of parameters), it would be very cumbersome to update each file individually. Therefore, the usual practice is to create a dedicated header file `bar.h` that contains the prototypes of all functions defined in `bar.c`.

```c
// File bar.h

int add(int, int);
```

Then use the `include` directive to include this header file `bar.h` in the source files that use this function.

```c
// File foo.c

#include <stdio.h>
#include "bar.h"

int main(void) 
{
  printf("%d\n", add(2, 3));  // 5!
}
```

In the above code, `#include "bar.h"` means including the header file `bar.h`. This file is not enclosed in angle brackets, indicating that it is user-provided; it does not have a path, meaning it is in the same directory as the current source file.

It is also a good practice to include this header file in `bar.c` to allow the compiler to verify that the function prototypes match the function definitions.

```c
// File bar.c
#include "bar.h"

int add(int a, int b) 
{
  return a + b;
}
```

Now, recompile to successfully obtain the binary executable file.

```c
$ gcc -o foo foo.c bar.c
```

## Repeated Inclusions

Header files can include other header files, which may lead to repeated inclusions. For example, if both `a.h` and `b.h` include `c.h`, and `foo.c` includes both `a.h` and `b.h`, this means `foo.c` will compile `c.h` twice.

It's best to avoid such repeated inclusions. While multiple definitions of the same function prototype do not cause errors, some statements, like multiple definitions of the same Struct data structure, will. A common method to handle repeated inclusions is to set a macro in the header file that prevents the file from being loaded more than once.

```c
// File bar.h
#ifndef BAR_H
  #define BAR_H
  int add(int, int);
#endif
```

In the example above, the header file `bar.h` uses `#ifndef` and `#endif` to set a conditional check. Each time this header file is included, this check is performed to see if the macro `BAR_H` has been defined. If it has been defined, it means the header file has already been included, so it will not be included again. Otherwise, the macro is defined and the function prototypes are included.

## `extern` Keyword

The current file can also use variables defined in other files, which is done using the `extern` keyword to declare that the variable is defined elsewhere.

```c
extern int myVar;
```

In the above example, the `extern` keyword tells the compiler that the variable `myVar` is declared in another file and does not require memory allocation here.

Since memory allocation is not required, when declaring arrays with `extern`, you do not need to specify the array length.

```c
extern int a[];
```

This declaration of shared variables can be written directly in the source file or placed in a header file to be included via `#include`.

## `static` Keyword

Normally, global variables in the current file can be accessed by other files. Sometimes, however, you may want a variable to be limited to the current file only and not accessible from other files.

In such cases, you can use the `static` keyword when declaring the variable, making it private to the current file.

```c
static int foo = 3;
```

In the above example, the variable `foo` can only be used within the current file and cannot be referenced from other files.

## Compilation Strategy

For projects with multiple source files, all files need to be compiled together. Even a single line modification requires a complete recompile, which can be very time-consuming.

To save time, a common approach is to split the compilation into two steps. First, use GCC's `-c` parameter to compile each source file into an object file. Second, link all object files together to create an executable file.

```c
$ gcc -c foo.c # generates foo.o
$ gcc -c bar.c # generates bar.o

# More convenient way
$ gcc -c *.c
```

The commands above generate object files `foo.o` and `bar.o` from source files `foo.c` and `bar.c`.

Object files are not executable files; they are intermediate products of the compilation process, with filenames similar to the source files but with a `.o` suffix.

After obtaining all the object files, use the `gcc` command again to link them and produce an executable file.

```c
$ gcc -o foo foo.o bar.o

# More convenient way
$ gcc -o foo *.o
```

In the future, if a source file is modified, only that file needs to be recompiled into an object file, while the other files remain unchanged. This approach significantly reduces compilation time since linking is much faster than compiling.

## `make` Command

For large projects, manually handling the compilation is cumbersome and error-prone. Typically, automated build tools like `make` are used.

`make` is a command-line tool that automatically searches for a configuration file named `makefile` (or `Makefile`) in the current directory. This file defines all compilation rules, with each rule corresponding to a build target. To create this build target, it needs to know two things:

- Dependencies (files needed to generate the build target)
- Build commands (commands to generate the build target)

For example, the object file `foo.o` is a build target with `foo.c` as its dependency and the command `gcc -c foo.c` to generate it. The corresponding rule is:

```c
foo.o: foo.c
  gcc -c foo.c
```

The rule consists of two lines: the first line specifies the build target and its dependencies, while the second line contains the build command.

Note that the second line must be indented with a Tab character; using spaces will result in an error.

A complete `makefile` contains multiple build rules and may look like this:

```c
foo: foo.o bar.o
  gcc -o foo foo.o bar.o

foo.o: bar.h foo.c
  gcc -c foo.c

bar.o: bar.h bar.c
  gcc -c bar.c
```

This example `makefile` contains three rules for building `foo.o`, `bar.o`, and `foo`. Each rule is separated by an empty line.

With a `makefile`, you can specify the build target with the `make` command to automatically invoke the corresponding build rules.

```c
$ make foo.o

# or
$ make bar.o

# or
$ make foo
```

The `make` command will generate different build targets based on the specified commands.

```c
$ make
```

If no build target is specified as above, `make` will execute the first rule in the `makefile`, which in this case is `make foo`. Since the goal is to produce the final executable file, it is recommended to place the rule for the final executable file at the beginning of the `makefile`. The `makefile` itself does not require an order for the rules.

The power of `make` lies in its ability to avoid unnecessary recompilation. It checks if a recompilation is needed by comparing timestamps of source files. If a file has changed since the last compilation, only those affected build targets are recompiled. Unchanged build targets remain as they are.

For example, if `foo.c` is modified but `bar.c` and `bar.h` are not, running `make foo` will cause `make` to skip recompiling `bar.o`, only recompiling `foo.o` and then linking it with `bar.o` to produce the new executable `foo`.

The main advantage of `make` is its automatic handling of the build process, recompiling only changed files, which significantly saves time.

# 21. Command Line Environment

## Command Line Arguments

C programs can receive arguments from the command line.

```c
$ ./foo hello world
```

In the example above, the program `foo` receives two command line arguments `hello` and `world`.

How does the program get the command line arguments? C language puts the command line input into an array. The `main()` function can receive this array through its parameters.

```c
#include <stdio.h>

int main(int argc, char* argv[]) 
{
  for (int i = 0; i < argc; i++) 
  {
    printf("arg %d: %s\n", i, argv[i]);
  }
}
```

In the example above, the `main()` function has two parameters `argc` (argument count) and `argv` (argument variable). The names of these parameters can be arbitrary, but commonly, these two terms are used.

The first parameter `argc` is the number of command line arguments, and since the program name is also counted, `argc` is strictly speaking the number of arguments + 1.

The second parameter `argv` is an array that holds all the command line inputs, where each member is a string pointer.

For example, with `./foo hello world`, `argc` is 3, representing three components of the command line input: `./foo`, `hello`, and `world`. The array `argv` is used to access these inputs: `argv[0]` is the program name `./foo`, `argv[1]` is `hello`, and `argv[2]` is `world`. Generally, `argv[1]` to `argv[argc - 1]` are all the command line arguments. `argv[argc]` is a null pointer.

Since string pointers can be considered as character arrays, the following two notations are equivalent.

```c
// Notation 1
int main(int argc, char* argv[])

// Notation 2
int main(int argc, char** argv)
```

On the other hand, each command line argument can be written either as an array `argv[i]` or as a pointer `*(argv + i)`.

By using `argc`, you can restrict the number of parameters the function can have.

```c
#include <stdio.h>

int main(int argc, char** argv) 
{
  if (argc != 3) 
  {
     printf("usage: mult x y\n");
     return 1;
  }

  printf("%d\n", atoi(argv[1]) * atoi(argv[2]));
  return 0;
}
```

In the example above, if `argc` is not equal to `3`, an error is reported, thus requiring the program to have exactly two parameters to run.

Additionally, the last member of the `argv` array is a NULL pointer (`argv[argc] == NULL`). Thus, iterating through the parameters can also be written as follows.

```c
for (char** p = argv; *p != NULL; p++) 
{
  printf("arg: %s\n", *p);
}
```

In the example above, the pointer `p` moves through each member of `argv` until it reaches the null pointer, indicating the end of the iteration. Since the address of `argv` is fixed and cannot be incremented (`argv++`), an intermediate variable `p` must be used to complete the iteration.

## Exit Status

The C language specifies that if the `main()` function does not have a `return` statement, it will default to adding a `return 0` when it ends, meaning it returns the integer `0`. This is why it is convention to return an integer value from `main()`, with `0` indicating that the program ran successfully. If a non-zero value is returned, it signifies that there was a problem during execution.

The Bash environment variable `$?` can be used to read the return value of the last command to determine if it ran successfully.

```bash
$ ./foo hello world
$ echo $?
0
```

In the example above, `echo $?` prints the value of the environment variable `$?`, which is `0`, indicating that the previous command was successful; otherwise, it means the command failed.

Note that only `main()` has the default `return 0` mechanism; other functions do not have this feature.

## Environment Variables

The C language provides the `getenv()` function (prototype in `stdlib.h`) to read command line environment variables.

```c
#include <stdio.h>
#include <stdlib.h>

int main(void) 
{
  char* val = getenv("HOME");

  if (val == NULL) 
  {
    printf("Cannot find the HOME environment variable\n");
    return 1;
  }

  printf("Value: %s\n", val);
  return 0;
}
```

In the example above, `getenv("HOME")` is used to retrieve the command line environment variable `$HOME`. If the variable is empty (`NULL`), the program prints an error message and returns.

# 22. Multi-Byte Characters

This chapter introduces how C handles non-English characters.

## Introduction to Unicode

When C was first created, it only considered English characters, using 7-bit ASCII encoding to represent all characters. ASCII ranges from 0 to 127, allowing for at most 128 characters, which can be represented using a single byte, so the `char` type only takes up one byte.

However, one byte is not enough for non-English characters. For example, Chinese characters alone number in the tens of thousands, necessitating the use of multiple bytes for the character set.

Initially, different countries had their own character encoding schemes, making it inconvenient to mix various characters. Therefore, a unified Unicode encoding was adopted later, encompassing all characters in one character set.

Unicode assigns a number, called a code point, to each character. The range from 0 to 127 overlaps with ASCII codes. Characters are typically represented using the format "U+hexadecimal code point", such as `U+0041` for the letter `A`.

Unicode currently contains over a million characters, with code points ranging from U+0000 to U+10FFFF. To represent the entire Unicode character set, at least three bytes are needed. However, not all documents require that many characters. For example, English documents that only need ASCII codes would have a file size three times larger if each character were represented with three bytes.

To accommodate different needs, the Unicode Consortium provides three different encoding methods for code points:

- **UTF-8**: Uses 1 to 4 bytes to represent a code point. Different characters require different numbers of bytes.
- **UTF-16**: Uses 2 bytes to represent a code point for characters in the range U+0000 to U+FFFF (known as the Basic Multilingual Plane). Other characters use 4 bytes.
- **UTF-32**: Uses a uniform 4 bytes to represent a code point.

Among these, UTF-8 is the most widely used because it represents ASCII characters (U+0000 to U+007F) with just one byte, which is identical to ASCII encoding.

C provides two macros to represent the byte length of the encoding supported by the current system. These macros are defined in the header file `limits.h`:

- **`MB_LEN_MAX`**: The maximum byte length supported by any locale, defined in `limits.h`.
- **`MB_CUR_MAX`**: The maximum byte length for the current locale, always less than or equal to `MB_LEN_MAX`, defined in `stdlib.h`.

## Character Representation

The essence of character representation is mapping each character to an integer, and then retrieving the character corresponding to that integer from the encoding table.

C provides different notations to represent the integer code of a character.

- **`\123`**: Represents a character using octal value; three digits are needed after the backslash.
- **`\x4D`**: Represents a character using hexadecimal value; `\x` is followed by a hexadecimal integer.
- **`\u2620`**: Represents a character using Unicode code point (not applicable to ASCII characters); the code point is represented in hexadecimal, and `\u` is followed by 4 characters.
- **`\U0001243F`**: Represents a character using Unicode code point (not applicable to ASCII characters); the code point is represented in hexadecimal, and `\U` is followed by 8 characters.

```c
printf("ABC\n");
printf("\101\102\103\n");
printf("\x41\x42\x43\n");
```

All three lines will output "ABC".

```c
printf("\u2022 Bullet 1\n");
printf("\U00002022 Bullet 1\n");
```

Both lines will output "• Bullet 1".

## Multi-Byte Character Representation

C language presets that only basic characters can be represented using literals; other characters should be represented using code points, and the current system must support the encoding method for that code point.

Basic characters refer to all printable ASCII characters, with three exceptions: `@`, `$`, and `` ` ``.

Thus, non-English characters should be written in Unicode code point format.

```c
char* s = "\u6625\u5929";
printf("%s\n", s); // 春天
```

The code above will output the Chinese "春天".

If the current system uses UTF-8 encoding, multi-byte characters can be directly represented using literals.

```c
char* s = "春天";
printf("%s\n", s);
```

Note that `\u + code point` and `\U + code point` notations cannot be used to represent ASCII characters (code points less than `0xA0`), except for three characters: `0x24` (`$`), `0x40` (`@`), and `0x60` (`` ` ``).

```c
char* s = "\u0024\u0040\u0060";
printf("%s\n", s);  // @$`
```

The code above will output the three Unicode characters “@$`”, but other ASCII characters cannot be represented using this notation.

To ensure that characters are correctly interpreted when the program runs, it is best to switch the program environment to a localized environment.

```c
setlocale(LC_ALL, "");
```

The code above uses `setlocale()` to switch the execution environment to the system's localized language. The prototype for `setlocale()` is defined in the header file `locale.h`, see the `locale.h` section in the standard library.

You can also specify the encoding language as follows:

```c
setlocale(LC_ALL, "zh_CN.UTF-8");
```

The code above switches the program execution environment to the Chinese locale with UTF-8 encoding.

C allows using the `u8` prefix to specify the encoding of multi-byte strings as UTF-8.

```c
char* s = u8"春天";
printf("%s\n", s);
```

Once a string contains multi-byte characters, the number of bytes in the string no longer corresponds directly to the number of characters. For example, a string with a length of 10 bytes might contain 7 characters, 5 characters, etc.

```c
setlocale(LC_ALL, "");

char* s = "春天";
printf("%d\n", strlen(s)); // 6
```

In the example above, the string `s` contains only two characters, but `strlen()` returns 6, indicating that these two characters occupy 6 bytes in total.

C string functions only work for single-byte characters and will not give correct results for multi-byte characters. Functions like `strtok()`, `strchr()`, `strspn()`, `toupper()`, `tolower()`, `isalpha()`, etc., may not provide accurate results.

## Wide Characters

In the previous section, multi-byte strings had variable byte widths per character. While this encoding method is convenient, it makes string processing complex because you need to check each character's byte length. To address this, C provides a fixed-width multi-byte character storage method called wide characters.

**Wide characters** have a fixed byte size, either 2 bytes or 4 bytes, making processing straightforward.

The wide character type is `wchar_t`, and each wide character is of this type. It is an alias for integer types and can be either signed or unsigned, depending on the implementation. This type's length is 16 bits (2 bytes) or 32 bits (4 bytes), sufficient to accommodate all characters of the current system. It is defined in the header file `wchar.h`.

Wide character literals must be prefixed with `L`; otherwise, C will treat the literals as narrow characters.

```c
setlocale(LC_ALL, "");

wchar_t c = L'牛';
printf("%lc\n", c);

wchar_t* s = L"春天";
printf("%ls\n", s);
```

In the above example, the prefix `L` before the single quote denotes a wide character, corresponding to `%lc` in `printf()`. Similarly, the prefix `L` before the double quote denotes a wide string, corresponding to `%ls` in `printf()`.

Wide strings also end with a wide null character, which occupies multiple bytes.

Handling wide characters requires using wide character-specific functions, most of which are defined in the `wchar.h` header file.

## Multi-Byte Character Processing Functions

### `mblen()`

The `mblen()` function returns the number of bytes used by a multi-byte character. Its prototype is defined in `stdlib.h`.

```c
int mblen(const char* mbstr, size_t n);
```

It takes two arguments: the first is a pointer to the multi-byte string (usually checking the first character), and the second is the number of bytes to check, which cannot exceed the maximum bytes per character supported by the system (generally using `MB_CUR_MAX`).

The return value is the number of bytes used by the character. If the character is a wide character with no bytes, it returns `0`; if the character is not a valid multi-byte character, it returns `-1`.

```c
setlocale(LC_ALL, "");

char* mbs1 = "春天";
printf("%d\n", mblen(mbs1, MB_CUR_MAX)); // 3

char* mbs2 = "abc";
printf("%d\n", mblen(mbs2, MB_CUR_MAX)); // 1
```

In the example above, the string "春天" has a first character "春" that occupies 3 bytes, while "abc" has a first character "a" that occupies 1 byte.

### `wctomb()`

The `wctomb()` function (wide character to multibyte) converts a wide character to a multi-byte character. Its prototype is defined in `stdlib.h`.

```c
int wctomb(char* s, wchar_t wc);
```

`wctomb()` takes two arguments: the first is a pointer to the target multi-byte character array, and the second is the wide character to convert. It returns the number of bytes used to store the multi-byte character; if conversion fails, it returns `-1`.

```c
setlocale(LC_ALL, "");

wchar_t wc = L'牛';
char mbStr[10] = "";

int nBytes = 0;
nBytes = wctomb(mbStr, wc);

printf("%s\n", mbStr);  // 牛
printf("%d\n", nBytes);  // 3
```

In the example, `wctomb()` converts the wide character "牛" to a multi-byte character, with the function returning the number of bytes (3).

### `mbtowc()`

The `mbtowc()` function converts a multi-byte character to a wide character. Its prototype is defined in `stdlib.h`.

```c
int mbtowc(wchar_t* wchar,
   		   const char* mbchar,
   		   size_t count
		   );
```

It takes three arguments: the first is a pointer to the target wide character, the second is a pointer to the multi-byte character to convert, and the third is the number of bytes of the multi-byte character.

The return value is the number of bytes used by the multi-byte character; if conversion fails, it returns `-1`.

```c
setlocale(LC_ALL, "");

char* mbchar = "牛";
wchar_t wc;
wchar_t* pwc = &wc;

int nBytes = 0;
nBytes = mbtowc(pwc, mbchar, 3);

printf("%d\n", nBytes); // 3
printf("%lc\n", *pwc);  // 牛
```

In the example, `mbtowc()` converts the multi-byte character "牛" to a wide character `wc`, with the function returning the number of bytes of `mbchar` (3).

### `wcstombs()`

The `wcstombs()` function converts a wide string to a multi-byte string. Its prototype is defined in `stdlib.h`.

```c
size_t wcstombs(char* mbstr,
   				const wchar_t* wcstr,
   				size_t count
				);
```

It takes three arguments: the first is a pointer to the target multi-byte string, the second is a pointer to the wide string to convert, and the third is the maximum number of bytes to store in the multi-byte string.

If the conversion is successful, the return value is the number of bytes written to the multi-byte string, excluding the terminating null character; if conversion fails, it returns `-1`.

Here is an example.

```c
setlocale(LC_ALL, "");

char mbs[20];
wchar_t* wcs = L"春天";

int nBytes = 0;
nBytes = wcstombs(mbs, wcs, 20);

printf("%s\n", mbs); // 春天
printf("%d\n", nBytes); // 6
```

In the example, `wcstombs()` converts the wide string `wcs` to a multi-byte string `mbs`, with the return value `6` indicating that 6 bytes were written to `mbs`, excluding the terminating null character.

If the first parameter of `wcstombs()` is `NULL`, the function returns the number of bytes needed to store the converted string.

### `mbstowcs()`

The `mbstowcs()` function converts a multi-byte string to a wide string. Its prototype is defined in `stdlib.h`.

```c
size_t mbstowcs(wchar_t* wcstr,
  				const char* mbstr,
  				size_t count
				);
```

It takes three arguments: the first is a pointer to the target wide string, the second is a pointer to the multi-byte string to convert, and the third is the maximum number of characters to convert from the multi-byte string.

On success, the return value is the number of wide characters successfully converted; on failure, it returns `-1`. If the return value is equal to the third argument, the converted wide string is not null-terminated.

Here is an example.

```c
setlocale(LC_ALL, "");

char* mbs = "天气不错";
wchar_t wcs[20];

int nBytes = 0;
nBytes = mbstowcs(wcs, mbs, 20);

printf("%ls\n", wcs); // 天气不错
printf("%d\n", nBytes); // 4
```

In the example, the multi-byte string `mbs` is converted to a wide string using `mbstowcs()`, with the function successfully converting 4 characters, so the return value is 4.

If the first parameter of `mbstowcs()` is `NULL`, it returns the number of characters that the target wide string would contain. "Sweet Home Home". "Sweet Home Home".



