# Functions in Python

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>This tutorial was written by Katherine Walden and is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Lab Overview & Goals

This lab provides an overview of foundational programming concepts in the areas of control flow and functions, with a focus on Python syntax. Topics covered include:
- Control flow and control structures
- Code modularity and reuse
- Built-in functions in Python
- Named functions in Python
- Core function components, including definition, arguments, parameters, scoping, and docstrings

## Acknowledgements

When building this lab, the author consulted materials developed by:
- [Dr. Peter Bui](http://www3.nd.edu/~pbui/) for the [CSE 10101 "Elements of Computing I" course](https://www3.nd.edu/~pbui/teaching/cdt.30010.fa16/).
  * [Conditional and Alternative Execution](http://nbviewer.jupyter.org/urls/gitlab.com/snippets/25773/raw)
  * [Functions](http://nbviewer.jupyter.org/urls/gitlab.com/snippets/26619/raw)
- [Dr. Janet Davis](https://cs.whitman.edu/~davisj/) for the the [CSC 105 "The Digital Age" course](https://www.cs.grinnell.edu/~davisjan/csc/105/2012S/). 
  * [Laboratory: Programming in Python (Decisions and Repetition)](http://www.cs.grinnell.edu/~davisjan/csc/105/labs/python3.html)
- [Dr. Corey Pennycuff](https://www3.nd.edu/~cpennycu/) for the [CSE 10101 Elements of Computing (Fall 2019)](https://www3.nd.edu/~cpennycu/2019/fa-CSE10101-CDT30010.html).
  * [Control flow structures](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.09.03.ipynb)
  * [Functions](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.09.19.ipynb)
  * [String functions and manipulation](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.10.01.ipynb)
- [Lindsay K. Mattock](http://lindsaymattock.net/) for the the [SLIS 5020 Computing Foundations course](http://lindsaymattock.net/computingfoundations.html). 

Definitions and explanations in this lab are adapted from Kenneth Leroy Busbee and Dave Braunschweig, *[Programming Fundamentals: A Modular Structured Approach, 2nd Edition](https://press.rebus.community/programmingfundamentals/)* (Rebus Press, 2018)
- [Chapter III, Functions](https://press.rebus.community/programmingfundamentals/part/functions/)

# Table of Contents
- [Key Concepts](#key-concepts)
- [Lab Notebook Template](#lab-notebook-template)
- [Overview](#overview)
  * [Modular Programming & Functions](#modular-programming--functions)
- [Functions in Python](#functions-in-python)
  * [Built-In Functions](#built-in-functions)
  * [Named Functions](#named-functions)
    * [How Named Functions Work](#how-named-functions-work)
    * [Python Example A](#python-example-a)
    * [Python Example B](#python-example-b)
    * [Python Example C](#python-example-c)
  * [Parameters & Scoping](#parameters--scoping)  
  * [Docstrings](#docstrings)
  * [Fruitful Versus Void Functions](#fruitful-versus-void-functions)
- [Putting It All Together: Why Functions?](#putting-it-all-together-why-functions)
  * [Code Reuse & Modularity](#code-reuse--modularity-aka-a-quick-detour-into-modules-packages-and-libraries)
- [How to submit this lab (and show your work)](#how-to-submit-this-lab-and-show-your-work)
- [Lab Notebook Questions](#lab-notebook-questions)

[Click here]() to access this lab procedure as a Jupyter Notebook.

## Key Concepts

[Click here](https://github.com/kwaldenphd/python-functions/blob/main/key-concepts.md) for a full list of key concepts and definitions from this lab.

## Lab Notebook Template

[Click here](https://colab.research.google.com/drive/18YBJg-hvbohdMlfhLVU1TZBHho-YRYqF?usp=sharing) to make a copy of the Replit template for this lab.

Alternatives:
- [`.py` template]() (Google Drive, ND users)
- [Jupyter Notebook, `.ipynb`](https://colab.research.google.com/drive/1EltssZ7B1PKv8FBQM55yc7AeyDyEi3Ma?usp=sharing) (Google Colab, ND users)

## How to submit this lab (and show your work)

Moving forward, we'll submit lab notebooks as `.py` files. 

One option is to have a `.py` file that you use to run code and test programs while working through the lab. When ready to submit the lab notebook, you add comments and remove extraneous materials.

Another option is to have an "official" `.py` file that you are using as a lab notebook (separate from your working/testing file). Use comments in Python to note when you are starting a new question (as well as answering a question).
  * Example: `Lab_Notebook_Walden.py`

What gets submitted as the lab notebook is the `Lab_Notebook_Walden.py` file.
- When in doubt, use comments
- Be sure you are using comments to note what question you're responding to

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

## Modular Programming & Functions

We've also previously been introduced to the concept of **code blocks**. From Busbee and Braunschweig's "[Code Blocks](https://press.rebus.community/programmingfundamentals/chapter/code-blocks/)" from *Programming Fundamentals*:
- "A code block, sometimes referred to as a compound statement, is a lexical structure of source code which is grouped together. Blocks consist of one or more declarations and statements. A programming language that permits the creation of blocks, including blocks nested within other blocks, is called a block-structured programming language. Blocks are fundamental to structured programming, where control structures are formed from blocks."
   
Approaching a program as a series of components that each accomplish tasks that are part of the larger workflow gets us to a new concept: **modularity** or **modular programming**

From Busbee and Braunschweig's "[Modular Programming](https://press.rebus.community/programmingfundamentals/chapter/modular-programming/)," in *Programming Fundamentals*:
- "Modular programming is a software design technique that emphasizes separating the functionality of a program into independent, interchangeable modules, such that each contains everything necessary to execute only one aspect of the desired functionality."

Code blocks are one way to think about these discrete parts of a program. A more precise term used in programming languages is **function.** "Functions are important because they allow us to take large complicated programs and to divide them into smaller manageable pieces. Because the function is a smaller piece of the overall program, we can concentrate on what we want it to do and test it to make sure it works properly" (Busbee and Braunschweig, [Modular Programming](https://press.rebus.community/programmingfundamentals/chapter/modular-programming/)).

# Functions in Python

In Python, a function is a named sequence of statements that performs a computation.
- Key term: *function*

To execute a function, we call it by name and pass it an appropriate set of input arguments. A function takes zero or more arguments as inputs and returns zero or more outputs as a result. The output or result of a function is called the return value.
- Key terms: *function call*, *input argument*, *function output* or *return value*

Data, parameters, or arguments can be passed into a function. Functions can also return data.

## Built-In Functions

We have actually already been working with a number of Python's built-in functions. These include `print()`, `dict()`, `input()`, `int()`, and `len()`.

We call built-in functions using the function name, followed by parenthesis.
- `print()`
- `dict()`
- `input()`
- `int()`
- `len()`

When we call one of these built-in functions, Python accesses and then executes the funtion's source code stored elsewhere in the Python environment.
- For example, you can see the source code for the `print()` function, contained in `[bltinmodule.c](https://github.com/python/cpython/blob/main/Python/bltinmodule.c#L1972)` file in Python's [source code](https://github.com/python/cpython/blob/).

Using `print()` as an example:
- The function definition is contained elsewhere in Python's source code
- We call the function using its name `print()`
- We pass some kind of input to the function (i.e. `print("Hello world")`)
- Some functions have an output or return value

### Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/internet/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSc6SKZMpaS62tTYi6_gVNnpXNKtpWsFwAMKxCsRoJywyPqERg/viewform?usp=sf_link">Built-in Functions in Python Comprehension Check</a></td>
  </tr>
  </table>

Describe functions in your own words

Which of following is NOT an example of a built-in function in Python

How a built-in function in Python executes

## Named Functions

But Python also lets us to create (and name) our own functions.
- Key term: *named function(s)*

We can define or name a function using the `def` keyword. A function definition includes a few core components:
- The name of the new function
- The list of function arguments
- The sequence of statements to execute when the function is called

The core syntax for defining your own function:

```Python
# use def keyword to define function name
def function_name(argument):
 statement(s)
 return result
```

Let's unpack each of those components.
- `def function_name()` is the name you are giving to the function you create- this is the header for the function definition.
  * Function names have many of the same rules as variable names- no spaces or special characters.
- `argument` is the argument that will be passed to the function.
  * When we are initially defining the function, the `argument` value is typically a placeholder.
  * Later in the program when we call the named function, the argument being passed to the function goes in these parenthesis.
- The nested or indented line `statement(s)` is the body of the function definition. It includes a sequence of statements to execute when the function is called.
- The nested or indented line `return result` is a placeholder for the function output or endpoint- it is also part of the body of the function definition.

### How Named Functions Work

So what happens when we use the `def` keyword to create a named function?

Programs are always executed sequentially, one statement at a time. Function definitions create new functions, but do not execute the bodies or statements within the functions UNTIL the functions are called.

When we call a named function, the program jumps to the definition for the function being called, executes the function's body, and then returns to the point in the program where the function was called and resumes executing the program.

As mentioned earlier, functions are an example of a control structure. Let's look at some examples.

### Python Example A

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

### Python Example B

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

We'll dig into what's happening here in more detail later in this lab. To summarize, we created a function for each piece of our conversion program (`getFahrenheit`, `convertTemp`, `result`), and then created a `main` function that combined those three steps.

Putting that all together:

```Python
# function for getting input
def getFahrenheit():
  fahrenheit = float(input("Enter a temperature in Fahrenheit: ")) 
  return fahrenheit
  
# function for converting to Celsius
def convertTemp(fahrenheit):
  celsius = (fahrenheit -32) * 5/9
  return celsius
  
# function for returning output
def result(fahrenheit, celsius):
  print(f"{fahrenheit} degrees Fahrenheit is equal to {celsius} degrees celsius")
  
# combined function
def combined():
  fahrenheit = getFahrenheit()
  celsius = convertTemp(fahrenheit)
  result(fahrenheit, celsius)
  
# combined temperature conversion program function call
combined()
```

### Python Example C

Let's say we want to create a function that prints an input string three times. Breaking down the steps of that program:
- Get input string
- Print the string (3x)

We might also need some way of tracking how many times we've printed the string so it stops at three.

One way we could approach this would be using a `count` variable and a `while` statement.

```Python
# assign count to 0
count = 0

# get input string
message = input("Type your message here: ")

# while statement
while count < 3:
    print(message) # print message
    count += 1 # reassign count
```

Thinking through how this program runs:
- `count` starts at `0` and increases by an increment of `1` each time the code nested under `while` runs
- The code nested under `while` will keep running until the initial condition (`count < 3`) is no longer true

We can test this program to make sure the output is what we expect. How that we have a program that prints an input string three times, we can create the named function.

```Python
# function definition
def printThreeTimes(string):
```

Then under the `def` keyword will go the lines of code that execute our program.

```Python
# function definition
def printThreeTimes():
    count = 0 # assign count
    message = input("Type your message here: ") # get input message
    while count < 3: # while statement
        print(message) # print message
        count += 1 # reassign count
```

Now when we run this block of code, there won't be any output because we are just creating or defining the `printThreeTimes` function. When we need to use the function, we can call it using its name.

```Python
# sample function call
printThreeTimes()
```

Putting that all together:
    
```Python
# function definition
def printThreeTimes():
    count = 0 # assign count
    message = input("Type your message here: ") # get input message
    while count < 3: # while statement
        print(message) # print message
        count += 1 # reassign count
    
# function call
printThreeTimes()
```

But let's say we don't want to use an `input()` statement as part of the function- what if we wanted to pass a specific value to the function?

First, let's build a program that accomplishes this task.

```Python
# assign string
message = "There's no place like home"

# assign count
count = 0

# while statement
while count < 3:
    print(message) # print message
    count += 1 # reassign count
```

To create the function:

```Python
def printThreeTimes(message):
    count = 0 # assign count
    while count < 3: # while statement
        print(message) # print message
        count += 1 # reassign count
```

Remember in this scenario, we are going to pass a specific value to the function, rather than asking for an input as part of the function.

So how would we call our modified `printThreeTimes` function? We would pass a string object to the function.

```Python
# assign string
message = "There's no place like home"

# function definition
def printThreeTimes(message):
    count = 0 # assign count
    while count < 3: # while statement
        print(message) # print message
        count += 1 # reassign count

# function call
printThreeTimes(message) 
```

### Parameters & Scoping

This modified example introduces a couple of key concepts for working with functions:
- Inside a function, the arguments are assigned to local variables, or placeholder variables. These local variables are called parameters.
  * Key term: *parameter*
- The name of the parameter inside the function is separated or isolated from the name outside the function. This separation of namespaces is called scoping.
  * Key term: *scoping*

An example of scoping:

```Python
# assign x variable
x = 1

# function definition
def print_number(x):
 print(x)
 
# print x variable
print(x)

# call named function
print_number(2)
```

The value of `x` in the first line of this program has nothing to do with the purpose `x` is serving in the function definition.

In short, the placeholder variables (or parameters) we use inside the function definition are separated or isolated from any instance where a variable or parameter with the same name is used outside the function definition.

<blockquote><a href="https://www.w3schools.com/python/python_scope.asp">Click here</a> to learn more about scope in Python, via W3Schools.</blockquote>

#### Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/internet/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSdCocH8cRcDgnc4WTiEQESxPKzKv8IpvhCc4D5CFAYb5Sim3Q/viewform?usp=sf_link">Named Functions in Python Comprehension Check</a></td>
  </tr>
  </table>

describe process for creating a named function in your own words

how do we call a named function

argument/parameter/scope in your own words

parameters- given an example, what is the value of x in line 2 vs line 7

#### Application

Let's say we want to create a function that prints an input string a specific number of times.

Breaking down the steps of that program:
- Get the input string (`message`)
- Get the number of times (`x`)
- Print the string `x` number of times

We might also need some way of tracking how many times we've printed the string so it stops at the specified number.

<blockquote>Q1A: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?</blockquote>

<blockquote>Q1B: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?</blockquote>

Here is one approach to this task:

We can use two input statements to get `message` and `x`. And one way we could approach printing the string `x` number of times would be to use a `count` variable and a `while` statement.

```Python
# input statement for string
message = input("Enter your message here: ")

# input statement for number of times
x = int(input("How many times do you want this statement to print? Enter a number value."))

# assign count
count = 0

# while statement
while count < x:
    print(message) # print message
    count += 1 # reassign count
```

Now to create a function using this program.

```Python
# function definition
def printNTimes():
    message = input("Enter your message here: ") # input statement for string
    x = int(input("How many times do you want this statement to print? Enter a number value.")) # input statement for number of times
    count = 0 # assign count
    while count < x: # while statement
        print(message) # print message
        count += 1 # reassign count

# function call
printNTimes()
```

<blockquote>Q1C: How does the sample program compare to your approach? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?</blockquote>

<blockquote>Q2: MODIFY TO PASS SPECIFIC VALUES TO THE FUNCTION</blockquote>

### Docstrings

We can add comments to a function definition by including a docstring under the function header.
- Key term: *docstring*

As we've learned previously, single-line comments in Python are declared using the `#` symbol, and multi-line comments in Python are declared using the <code>'''</code> symbol.

Docstrings are declared using triple single quotes (<code>'''</code>) or triple double quotes (`"""`).
- Best practice is to start the docstring just below the function header.
- Another best practice for docstrings is to begin with a capital letter and end with a period.
- The docstring should briefly describe what the function does.

Let's see this in action with an example from earlier in the lab.

```Python
# function definition
def printThreeTimes():
 '''Prints an input string three times'''
    count = 0 # assign count
    message = input("Type your message here: ") # get input message
    while count < 3: # while statement
        print(message) # print message
        count += 1 # reassign count
```

We have a couple options for accessing the contents of the docstring elesewhere in the program. We can use the `__doc__` method (underscore, underscore, doc, underscore, underscore).
```Python
print("Using __doc__:")
print(printThreeTimes.__doc__)
```

Or we can use the `help()` function.
```Python
print("Using help:")
help(printThreeTimes)
```

Multi-line docstrings can be used to provide additional description about the named function, including information about parameters, arguments, and returns.

<blockquote><a href="https://www.python.org/dev/peps/pep-0257/">Click here</a> to learn more about docstrings in Python, via Python.org documentation.</blockquote>

### Fruitful Versus Void Functions

Functions that yield a result are considered fruitful. To output a result, a function uses the `return` statement to pass results back to the function call.
- Key term: *fruitful function(s)*

Functions that perform a computation but do not yield a result are considered void. By default, the return value for void functions is `None`.
- Key term: *void function(s)*

#### Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/internet/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSciArOqUPt4P8K2jhmj8ZabkM65bxCnp-jwi-L4Xzxc6MryZg/viewform?usp=sf_link">Python Function Considerations Comprehension Check</a></td>
  </tr>
  </table>

Describe docstrings in your own words

Syntax ID - creating and accessing docstrings

Example function - is it fruitful or is it void

#### Application

QX: Write a function is_even that determines whether or not a number n is even. Include code + comments for the function definition as well as a sample function call.

QX: Write a function average that determines the average value of a list. Include code + comments for the function definition as well as a sample function call.

QX: Write a function uniq that takes a list and returns a new list containing only unique values. Include code + comments for the function definition as well as a sample function call.

# Putting It All Together: Why Functions?

<p align="center"><img src="https://github.com/kwaldenphd/python-functions/blob/main/images/hulk_antman_meme.png?raw=true" width="500"></p>

Using functions to promote modular programming serves a few key purposes:
- Yields **more concise code*** by eliminating the need to write out code for the same task multiple times
- Improves **improve code readability**
- Helps us **more effectively test and debug code**
  * Because we are creating reusable pieces or building blocks of code, we can more readily pinpoint where things are going wrong or not working in our code.
- **Promotes code reuse and modularity** by allowing us to define and call functions for common tasks

This may seem overly-complicated for a relatively simple program.

But imagine all kinds of more complex tasks we might want to accomplish in a programming environment- analyzing data, generating visualizations, creating textures, building interaction objects, etc. All of that becomes possible through functions- modular building blocks that can be combined to accomplish more complex tasks.

## Code Reuse & Modularity (aka a quick detour into modules, packages, and libraries)

As we move forward in Python, we're going to be encountering the terms `package`, `module`, and `library.` All of these terms refer to external Python programs that we can use in our program without having to recreate the entire original code. We can think of these resources as "expansion packs" for Python that expand or extend the programming language's built-in functionality.

A few preliminary definitions...
- A ***module*** is a Python file that typically includes specialized functions and variables. Modules typically have `.py` file extensions.
- A single or simple directory of modules is called a ***package***. Packages are typically a simple directory with multiple modules.
- A ***library*** includes blocks of code that can be reused within a program. Libraries are a collection of modules that have a much more complex directory/sub-directory/etc structure than packages

Some modules, packages, and libraries are built-in to Python and require no additional installation. Others have to be installed (typically at the command line, or in the terminal) before you can import and use them in a program.

Built-in functions don't require any extra steps to be able to access them in the programming environment. For example, you can see the source code for the `print()` function, contained in Python's `[bltinmodule.c](https://github.com/python/cpython/blob/main/Python/bltinmodule.c#L1972)` file in the [source code](https://github.com/python/cpython/blob/). But all we have to do is use the function name in our program.

<p align="center"><img src="https://github.com/kwaldenphd/python-functions/blob/main/images/python_package.png?raw=true" width="500"></p>

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

### Comprehension Check

<table>
 <tr><td>
<img src="https://github.com/kwaldenphd/internet/blob/main/images/clipboard.png?raw=true" alt="Clipboard icon" width="50"/></td>
  <td><a href="https://docs.google.com/forms/d/e/1FAIpQLSctIknF2mA209zKSFH7lAA_6dBg9HoAmYDBg58QqNk37YgBVA/viewform?usp=sf_link">Code Reuse & Modularity in Python Comprehension Check</a></td>
  </tr>
  </table>

relationship of functions and modules

Relationship of modules and packages

how we import specific modules from a package

### Application

Pick a specific Python package- what does it do/what is it for

What specific modules does it contain

How would we import it into a program

Write a program that uses functions/arguments from the module

Packages that folks could chose from:
- Statistics
- Random
- If you hate yourself, SportsDB


QX: Why would we use functions, value of functions. Relationship to code reuse/modularity.

## How to submit this lab (and show your work)

Moving forward, we'll submit lab notebooks as `.py` files. 

One option is to have a `.py` file that you use to run code and test programs while working through the lab. When ready to submit the lab notebook, you add comments and remove extraneous materials.

Another option is to have an "official" `.py` file that you are using as a lab notebook (separate from your working/testing file). Use comments in Python to note when you are starting a new question (as well as answering a question).
  * Example: `Lab_Notebook_Walden.py`

What gets submitted as the lab notebook is the `Lab_Notebook_Walden.py` file.
- When in doubt, use comments
- Be sure you are using comments to note what question you're responding to

# Lab Notebook Questions

[Click here]() to make a copy of the Replit template for this lab.

Alternatives:
- [`.py` template]() (Google Drive, ND users)
- [Jupyter Notebook, `.ipynb`]() (Google Colab, ND users)


