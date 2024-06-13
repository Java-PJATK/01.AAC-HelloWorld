# 1.AAC-HelloWorld
Listing 1 AAC-HelloWorld/Hello.java Page 4

# Section 1: General Introduction

## 1.1 Computers and Programming Languages
1. **Hardware:** processors, memory, caches, disks and the like...
2. **Operating System:** "system software that manages computer hardware and software resources and provides common services for computer programs... For hardware functions such as input/output and memory allocation, the operating system acts as an intermediary between programs and the computer hardware" (Wikipedia). The operating system interacts with the file system, launches other programs, assigns resources, interacts with the user, and detects events (e.g., mouse movements, clicks, key presses).

   On desktop computers, the dominant operating system is Microsoft Windows, followed by Apple’s macOS and various distributions of Linux. On smartphones and tablets, Google’s Android is the leader, followed by Apple’s iOS. Linux distributions are dominant in the server and super-computing sectors. According to Stack Overflow, among professional developers, 50% use Windows, 27% use macOS, and 23% use a Linux distribution.

3. **Bits and Bytes, Hexadecimal and Octal System:**
   - **Bit:** the smallest unit of information, with only two possible values (0 or 1).
   - **Byte:** a sequence of 8 bits, with 256 possible sequences.
   - **Hexadecimal Notation:** practical for representing bytes, as four bits correspond exactly to one hexadecimal digit (0-9, A-F).

4. **Processor:** the component that executes instructions. Important components include registers, where data is stored and manipulated by instructions. Each processor has its own instruction set, consisting of basic instructions like setting a register to a value, copying data between memory and registers, arithmetic operations, etc.

5. **Program:** a sequence of instructions, written in any programming language, which performs a specific task after being transformed into machine code.

6. **Compiler:** a program that translates source code into machine code or an intermediate form that is later compiled further to machine code. For languages like Java, the compiled result is not directly executable but requires a virtual machine (JVM) for execution.

7. **Programming Languages:**
   - **Low-level:** machine code, assembly language.
   - **High-level:** interpreted or compiled, categorized into imperative (procedural, object-oriented) and declarative (relational, functional, logic).

   Popular programming languages include Java, C/C++, Python, and JavaScript, with preferences varying by domain (e.g., Fortran for scientific computing, R for statistics).

8. **Algorithm:** "an unambiguous specification of how to solve a class of problems" (Wikipedia). Algorithms are step-by-step procedures to achieve a desired outcome, such as sorting a collection of numbers or finding the greatest common divisor of two numbers.

   The term "algorithm" is derived from the name of the 9th-century Persian scholar Muhammad ibn Musa al-Khwarizmi and the Greek word "arithmos" (number).

## 1.2 What is Java?
Java is a high-level imperative programming language with object-oriented features and elements of functional programming. It was designed with emphasis on:
1. Platform independence
2. Simplicity
3. Safety (e.g., no direct memory access, garbage collector, security management)
4. Efficiency
5. Rich standard library

**Features of Java:**
- Designed by Sun Microsystems in the mid-1990s for commercial use.
- Compiled to platform-independent bytecode.
- Executed by the Java Virtual Machine (JVM), which interprets bytecode and dynamically translates it into machine code for execution.
- Syntax closely resembles that of C/C++.
- Includes a comprehensive standard library for graphics, multithreading, network programming, database access, multimedia processing, security, microprogramming, and data format handling (XML, JSON, etc.).

**Installation:** Obtain JDK (Java Development Kit) from Oracle’s website. JDK includes the JVM for running Java programs and tools for developing Java applications, including the compiler.

**Documentation:** Available online or downloadable as a zip file.

# Section 2. Compiling and running a Java program  

* Program in Java is a collection of classes (what class really means, we will learn shortly). Normally, each class is written in a separate (text) file with extension .java.  

* Whatever we write must be in a class; there must be at least one class declared as public and containing public function main;  
  
* Names are important: (public) class Person must be defined in file Person.java.  

* Names of classes (and therefore of files containing their definition) should start with a capital letter; strictly speaking, it is not required, but to avoid vexing trouble, we should always stick to this convention.  

Let us look at a very simple example: a program which consists of only one class (and, consequently, one file) which contains nothing but the function main. The program just prints (i.e., writes to the screen) “Hello, World”.  

```java
// AAC-HelloWorld/Hello.java
 
/*
 *  Program Hello
 *  It prints "Hello, World"
 */

public class Hello { /* Entry class must be public
                        File name = class name!   */
    public static void main(String[] args) {
        System.out.println("Hello, World");
    }
    // signature of 'main' always like this
}
```

Some elements to note:  

* We have to define classes — everything is in a class!
* Name of the (public) class = name of the file.
* All names are case sensitive (xy, XY and Xy are completely distinct names having
nothing in common) — this may be not so obvious for Windows’ users.
* There must be a (static) function main, with ‘signature’ as shown in the example,
in the class which is the entry point to the whole application.
* Each class is compiled to a separate class-file with extension class (which contains
something like machine code, but for JVM, not for a real processor).
* Comments (from // to the end of line, and from /* through */).
* Each statements of the program must end with a semicolon and may be written
in many lines: sequences of white spaces (including end of line characters) are
treated as one space.
* Printing (System.out.println).

Having a source file(s), we have to compile it. The Java compiler is a program named javac (javac.exe on Windows). We invoke it passing, as arguments, one or more `.java` source files (or `*.java` to compile all `.java` files in the current directory). The compiler
creates the so called class files: one for each class defined in our source files. The names of these files are the same as the names of the classes, but with extension .class instead of .java. They contain the so called byte code corresponding to classes. This
is not the machine code for any real processor, but rather for a virtual processor which doesn’t physically exist but is standarized and platform independent. Hence, it doesn’t matter on which platform the process of compilation takes place — the resulting byte code can be run on any platform where Java is installed.  

As the byte code is not yet in the form of the machine code, we still need another
program to run (execute) the compiled Java application. This program is called JVM
— Java Virtual Machine — program which is named just java (java.exe on Windows).
Invoking it, we pass, as the argument, the name of the class which is the entry point
to our application (without any extension) — this class must contain the function
main. The program reads the byte code, compiles it ‘to the end’ into the form of
machine code appropriate for a given platform and executes it (without creating any
additional files).  

Strictly speaking, JVM (or its sub-process called JIT — just-in-time
compilation) compiles the byte code constantly ‘on the fly’; it can dynamically detect
‘bottle necks’ of the program and optimize these parts of the code because it has access
to dynamic run-time information (which is not the case for traditional compilers).
Continuing our example, the process of compiling and running our application might
look like this

```
$ ls                           what’s in the current directory?
Hello.java
$ javac Hello.java             we compile...
$ ls                           what do we have now?
Hello.class
$ java HelloHello.java         we run the program
Hello, World                   and get its output
```
