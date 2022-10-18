# Key Concepts



**Built-In Functions**
- "Python has several functions that are readily available for use. These functions are called built-in functions" ([Programiz](https://www.programiz.com/python-programming/methods/built-in))
- Examples of built-in Python functions include: `dict()`, `print()`, `help()`, `int()`
- For more on Python's built-in functions: https://www.w3schools.com/python/python_ref_functions.asp

**Code Blocks**
- "A code block, sometimes referred to as a compound statement, is a lexical structure of source code which is grouped together. Blocks consist of one or more declarations and statements. A programming language that permits the creation of blocks, including blocks nested within other blocks, is called a block-structured programming language. Blocks are fundamental to structured programming, where control structures are formed from blocks." (Busbee and Braunschweig's "[Code Blocks](https://press.rebus.community/programmingfundamentals/chapter/code-blocks/)" from *Programming Fundamentals*)

**Code Reuse & Modularity**
- "Modular programming is a software design technique that emphasizes separating the functionality of a program into independent, interchangeable modules, such that each contains everything necessary to execute only one aspect of the desired functionality." (Busbee and Braunschweig's "[Modular Programming](https://press.rebus.community/programmingfundamentals/chapter/modular-programming/)," in *Programming Fundamentals*)

**Control Flow, Control Structures**

From Busbee and Braunschweig's "[Structured Programming](https://press.rebus.community/programmingfundamentals/chapter/structured-programming/)" from *Programming Fundamentals*
    
"One of the most important concepts of programming is the ability to control a program so that different lines of code are executed or that some lines of code are executed many times. The mechanisms that allow us to control the flow of execution are called control structures. Flowcharting is a method of documenting (charting) the flow (or paths) that a program would execute. There are three main categories of control structures:"
  * Sequence [executes in given sequence]
  * Selection [selects between two or more flows using condition or question]
  * Iteration [repeats same piece of code multiple times]
    
Examples of control structures in Python include:
- `if-then-else` (syntax: `if`, `else`, `elif`)
- `while` statements (syntax: `while`)


**`def` keyword**
- "In Python a function is defined using the def keyword" (W3Schools, ["Creating a Function"](https://www.w3schools.com/python/python_functions.asp))

```Python
# use def keyword to define function name
def function_name(argument):
 statement(s)
 return result
```

**Docstrings**
- "A Python docstring is a string used to document a Python module, class, function or method, so programmers can understand what it does without having to read the details of the implementation" ([Pandas docstring guide](https://pandas.pydata.org/docs/development/contributing_docstring.html))

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

**Fruitful vs Void Functions**
- Functions that yield a result are considered fruitful. To output a result, a function uses the `return` statement to pass results back to the function call. Functions that perform a computation but do not yield a result are considered void. By default, the return value for void functions is `None`.

**`import` statement**
- "The import statement combines two operations; it searches for the named module, then it binds the results of that search to a name in the local scope" ([Python, "The import system"](https://docs.python.org/3/reference/import.html))

**Functions**
- In Python, a function is a named sequence of statements that performs a computation. To execute a function, we call it by name and pass it an appropriate set of input arguments. A function takes zero or more arguments as inputs and returns zero or more outputs as a result. The output or result of a function is called the return value.
- For more on functions in Python: https://www.w3schools.com/python/python_functions.asp

**Modules, Packages & Libraries**
- A ***module*** is a Python file that typically includes specialized functions and variables. Modules typically have `.py` file extensions.
- A single or simple directory of modules is called a ***package***. Packages are typically a simple directory with multiple modules.
- A ***library*** includes blocks of code that can be reused within a program. Libraries are a collection of modules that have a much more complex directory/sub-directory/etc structure than packages

Some modules, packages, and libraries are built-in to Python and require no additional installation. Others have to be installed (typically at the command line, or in the terminal) before you can import and use them in a program.

For more on the difference between modules, packages, and libraries in Python: https://www.geeksforgeeks.org/what-is-the-difference-between-pythons-module-package-and-library/

**Parameters, Scoping**
- Inside a function, the arguments are assigned to local variables, or placeholder variables. These local variables are called parameters. The name of the parameter inside the function is separated or isolated from the name outside the function. This separation of namespaces is called scoping.

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

For more on scope in Python: https://www.w3schools.com/python/python_scope.asp
