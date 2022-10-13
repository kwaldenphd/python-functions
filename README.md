# Functions in Python

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>This tutorial was written by Katherine Walden and is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Overview & Goals

## Acknowledgements

# Table of Contents
- [Key Concepts](#key-concepts)
- [Lab Notebook Template](#lab-notebook-template)

- [How to submit this lab (and show your work)](#how-to-submit-this-lab-and-show-your-work)
- [Lab Notebook Questions](#lab-notebook-questions)

## Key Contents

## Lab Notebook Template

# Overview

From Busbee and Braunschweig's "[Structured Programming](https://press.rebus.community/programmingfundamentals/chapter/structured-programming/)," in *Programming Fundamentals*:
    
"One of the most important concepts of programming is the ability to control a program so that different lines of code are executed or that some lines of code are executed many times. The mechanisms that allow us to control the flow of execution are called control structures. Flowcharting is a method of documenting (charting) the flow (or paths) that a program would execute. There are three main categories of control structures:"
  * Sequence [executes in given sequence]
  * Selection [selects between two or more flows using condition or question]
  * Iteration [repeats same piece of code multiple times]
  
We're going to spend multiple labs thinking through control structures and control flow, with a focus on how we use them in Python.
    
Examples of control structures in Python include:
- `if-then-else` (syntax: `if`, `else`, `elif`)
- `while` statements (syntax: `while`)

We've also previously been introduced to the concept of **code blocks**. From Busbee and Braunschweig's "[Code Blocks](https://press.rebus.community/programmingfundamentals/chapter/code-blocks/)" from *Programming Fundamentals*:
- "A code block, sometimes referred to as a compound statement, is a lexical structure of source code which is grouped together. Blocks consist of one or more declarations and statements. A programming language that permits the creation of blocks, including blocks nested within other blocks, is called a block-structured programming language. Blocks are fundamental to structured programming, where control structures are formed from blocks."
   
Approaching a program as a series of components that each accomplish tasks that are part of the larger workflow gets us to a new concept: **modularity** or **modular programming**

From Busbee and Braunschweig's "[Modular Programming](https://press.rebus.community/programmingfundamentals/chapter/modular-programming/)," in *Programming Fundamentals*:
- "Modular programming is a software design technique that emphasizes separating the functionality of a program into independent, interchangeable modules, such that each contains everything necessary to execute only one aspect of the desired functionality."

Code blocks are one way to think about these discrete parts of a program. A more precise term used in programming languages is **function.** "Functions are important because they allow us to take large complicated programs and to divide them into smaller manageable pieces. Because the function is a smaller piece of the overall program, we can concentrate on what we want it to do and test it to make sure it works properly" (Busbee and Braunschweig, [Modular Programming](https://press.rebus.community/programmingfundamentals/chapter/modular-programming/)).

Let's look at a Python example. In a previous lab, we wrote a program that took a temperature in Fahrenheit and converted it to Celsius.

What that program might have looked like:
```Python
# input temp
f = float(input("Enter a temperature in Fahrenheit: "))

# convert to celsius
c = (f -32) * 5/9

# show output
print(f"{f} degrees Fahrenheit is equal to {c} degrees celsius")
```

<blockquote>For more on <code>f strings</code> in Python: https://realpython.com/python-f-strings/</blockquote>

This isn't a terribly long program to write out, but if we need to perform this conversion regularly, we might want to just write it out once and be able use that working code elsewhere in our program.

We can rewrite this program as a function that we can access elsewhere in our program. 

```Python
# define function
def tempConvert():
  fahrenheit = float(input("Enter a temperature in Fahrenheit: ")) # get temperature
  celsius = (fahrenheit -32) * 5/9 # convert to celsius
  print(f"{fahrenheit} degrees Fahrenheit is equal to {celsius} degrees celsius") # show output
```

Then, elsewhere in our program, we could call that function using its name.

```Python
# sample function call
tempConvert(32)
```

In this example, we passed the value `32` to the `tempConvert` function we created. 

But we could break down this program further, thinking about the underlying steps:
- Get user input for Fahrenheit temperature
- Convert to celsius
- Show output

We could create modular pieces for each of these tasks.

```Python
# function for getting input
def getFahrenheit():
  fahrenheit = float(input("Enter a temperature in Fahrenheit: ")) 
  return fahrenheit
```

```Python
# function for converting to Celsius
def convertTemp(fahrenheit):
  celsius = (fahrenheit -32) * 5/9
  return celsius
```

```Python
# function for returning output
def result(fahrenheit, celsius):
  print(f"{fahrenheit} degrees Fahrenheit is equal to {celsius} degrees celsius")
```

And we could create a combined function from each of those three individual functions.

```Python
# combined function
def combined():
  fahrenheit = getFahrenheit()
  celsius = convertTemp(fahrenheit)
  result(fahrenheit, celsius)
```

To run our entire temperature conversion program, we would just need to call the `combined()` function using its name.

```Python
# combined temperature conversion program function call
combined()
```

We'll dig into what's happening here in more detail later in this lab, but to summarize: 

NEW HULK MEME

Using functions to promote modular programming serves a few key purposes:
- Yields **more concise code*** by eliminating the need to write out code for the same task multiple times
- Improves **improve code readability**
- Helps us **more effectively test and debug code**
  * Because we are creating reusable pieces or building blocks of code, we can more readily pinpoint where things are going wrong or not working in our code.
- **Promotes code reuse and modularity** by allowing us to define and call functions for common tasks

This may seem overly-complicated for a relatively simple program.

But imagine all kinds of more complex tasks we might want to accomplish in a programming environment- analyzing data, generating visualizations, creating textures, building interaction objects, etc. All of that becomes possible through functions- modular building blocks that can be combined to accomplish more complex tasks.

# Functions in Python

In Python, a function is a named sequence of statements that performs a computation.
- Key term: *function*

To execute a function, we call it by name and pass it an appropriate set of input arguments.
- Key terms: *function call*, *input argument*

A function takes zero or more arguments as inputs and returns zero or more outputs as a result.

The output or result of a function is called the return value.
- Key terms: *function output* or *return value*

Data, parameters, or arguments can be passed into a function. Functions can also return data.

## Built-In Functions

- Examples we've already seen (print, type, input)
- What these are/how they work generally
- Deep dive on `print()` where it shows up in the documentation, how Python interacts with/access it here

We have actually already been working with a number of Python's built-in functions. These include `print()`, `dict()`, `input()`, `int()`, and `len()`.

We call built-in functions using the function name, followed by parenthesis.
- `print()`
- `dict()`
- `input()`
- `int()`
- `len()`

W

## Comprehension Check

## Application


# Creating Name Functions

- Core syntax, examples

## Comprehension Check

## Application



# Additional Considerations

- Fruitful vs void
- Parameters
- Scoping
- Docstrings/documentation

## Comprehension Check

## Application

# Putting It All Together: Code Reuse & Modularity

#### A Quick Detour Into Packages, Modules, and Libraries

As we move forward in Python, we're going to be encountering the terms `package`, `module`, and `library.` All of these terms refer to external Python programs that we can use in our program without having to recreate the entire original code. We can think of these resources as "expansion packs" for Python that expand or extend the programming language's built-in functionality.

A few preliminary definitions...
- A ***module*** is a Python file that typically includes specialized functions and variables. Modules typically have `.py` file extensions.
- A single or simple directory of modules is called a ***package***. Packages are typically a simple directory with multiple modules.
- A ***library*** includes blocks of code that can be reused within a program. Libraries are a collection of modules that have a much more complex directory/sub-directory/etc structure than packages

Some modules, packages, and libraries are built-in to Python and require no additional installation. Others have to be installed (typically at the command line, or in the terminal) before you can import and use them in a program.

GAME PACKAGE FIGURE

In this example, we have a `game` package that includes `sound`, `image`, and `level` sub-packages. Each of those sub-packages includes specific modules. For example, the `sound` sub-package includes the `load.py`, `play.py`, and `pause.py` modules.

We can bring these modules into our program using an `import` statement.

For example, let's say we wanted to bring the `start.py` module from the `level` sub-package into our program.

We could do this using the following `import` statement at the start of our program.

```Python
from game.level import start
```

Now, we would be able to access any of the functions (or other code) contained in the `start.py` module, because we have **imported** them into our program.

For more on modules, packages, and libraries in Python:
- Programmiz, "[Python Package](https://www.programiz.com/python-programming/package)
- GeeksForGeeks, "[What is the difference between Python's Module, Package and Library?](https://www.geeksforgeeks.org/what-is-the-difference-between-pythons-module-package-and-library/)" (30 September 2022)
- John Sturtz, "[Python Modules and Packages - An Introduction](https://realpython.com/python-modules-packages/)" *Real Python*


## Comprehension Check

## Application



# Lab Notebook Questions

