# 1.AAC-HelloWorld
Listing 1 AAC-HelloWorld/Hello.java Page 4

Section 2
Compiling and running a Java program
• Program in Java is a collection of classes (what class really means, we will learn
shortly). Normally, each class is written in a separate (text) file with extension
.java.
• Whatever we write must be in a class; there must be at least one class declared
as public and containing public function main;
• Names are important: (public) class Person must be defined in file Person.java.
Names of classes (and therefore of files containing their definition) should start
with a capital letter; strictly speaking, it is not required, but to avoid vexing
trouble, we should always stick to this convention.
Let us look at a very simple example: a program which consists of only one class
(and, consequently, one file) which contains nothing but the function main. The pro-
gram just prints (i.e., writes to the screen) “Hello, World”.

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
• We have to define classes — everything is in a class!
• Name of the (public) class = name of the file.
• All names are case sensitive (xy, XY and Xy are completely distinct names having
nothing in common) — this may be not so obvious for Windows’ users.
• There must be a (static) function main, with ‘signature’ as shown in the example,
in the class which is the entry point to the whole application.
• Each class is compiled to a separate class-file with extension class (which contains
something like machine code, but for JVM, not for a real processor).
• Comments (from // to the end of line, and from /* through */).
• Each statements of the program must end with a semicolon and may be written
in many lines: sequences of white spaces (including end of line characters) are
treated as one space.
• Printing (System.out.println).
Having a source file(s), we have to compile it. The Java compiler is a program named
javac (javac.exe on Windows). We invoke it passing, as arguments, one or more .java
4
source files (or ’*.java’ to compile all .java files in the current directory). The compiler
creates the so called class files: one for each class defined in our source files. The
names of these files are the same as the names of the classes, but with extension .class
instead of .java. They contain the so called byte code corresponding to classes. This
is not the machine code for any real processor, but rather for a virtual processor which
doesn’t physically exist but is standarized and platform independent. Hence, it doesn’t
matter on which platform the process of compilation takes place — the resulting byte
code can be run on any platform where Java is installed.
As the byte code is not yet in the form of the machine code, we still need another
program to run (execute) the compiled Java application. This program is called JVM
— Java Virtual Machine — program which is named just java (java.exe on Windows).
Invoking it, we pass, as the argument, the name of the class which is the entry point
to our application (without any extension) — this class must contain the function
main. The program reads the byte code, compiles it ‘to the end’ into the form of
machine code appropriate for a given platform and executes it (without creating any
additional files). Strictly speaking, JVM (or its sub-process called JIT — just-in-time
compilation) compiles the byte code constantly ‘on the fly’; it can dynamically detect
‘bottle necks’ of the program and optimize these parts of the code because it has access
to dynamic run-time information (which is not the case for traditional compilers).
Continuing our example, the process of compiling and running our application might
look like this
$ ls
what’s in the current directory?
Hello.java
$ javac Hello.java
we compile...
$ ls
what do we have now?
Hello.class
$ java HelloHello.java
we run the program
Hello, World
and get its output
