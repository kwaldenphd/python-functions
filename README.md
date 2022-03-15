# Functions in Python

<a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license"><img style="border-width: 0;" src="https://i.creativecommons.org/l/by-nc/4.0/88x31.png" alt="Creative Commons License" /></a>
This tutorial is licensed under a <a href="http://creativecommons.org/licenses/by-nc/4.0/" rel="license">Creative Commons Attribution-NonCommercial 4.0 International License</a>.

## Acknowledgements

Elements of this lab procedure were adapted from materials developed by [Dr. Peter Bui](http://www3.nd.edu/~pbui/) for the [CSE 10101 "Elements of Computing I" course](https://www3.nd.edu/~pbui/teaching/cdt.30010.fa16/).
- [Conditional and Alternative Execution](http://nbviewer.jupyter.org/urls/gitlab.com/snippets/25773/raw)
- [Functions](http://nbviewer.jupyter.org/urls/gitlab.com/snippets/26619/raw)

Elements of this lab procedure were adapted from materials developed by [Dr. Janet Davis](https://cs.whitman.edu/~davisj/) for the the [CSC 105 "The Digital Age" course](https://www.cs.grinnell.edu/~davisjan/csc/105/2012S/). 
- [Laboratory: Programming in Python (Decisions and Repetition)](http://www.cs.grinnell.edu/~davisjan/csc/105/labs/python3.html)

Elements of this lab procedure were adapted from materials developed by [Dr. Corey Pennycuff](https://www3.nd.edu/~cpennycu/) for the [CSE 10101 Elements of Computing (Fall 2019)](https://www3.nd.edu/~cpennycu/2019/fa-CSE10101-CDT30010.html).
- [Control flow structures](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.09.03.ipynb)
- [Functions](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.09.19.ipynb)
- [String functions and manipulation](https://www3.nd.edu/~cpennycu/2019/assets/fall/EOC/19.10.01.ipynb)

Elements of this lab procedure were adapted from materials developed by [Lindsay K. Mattock](http://lindsaymattock.net/) for the the [SLIS 5020 Computing Foundations course](http://lindsaymattock.net/computingfoundations.html). 

# Table of Contents

- [Lecture and Live Coding](#lecture-and-live-coding)
- [Lab Notebook Template](#lab-notebook-template)
- [Functions](#functions)
  * [Built-In Functions](#built-in-functions)
  * [Named Functions](#named-functions)
    * [How Named Functions Work](#how-named-functions-work)
    * [Name Function Examples](#named-function-examples)
      * [Function Example A](#function-example-a)
      * [Function Example B](#function-example-b)
    * [Additional Function Considerations](#additional-function-considerations)
      * [Fruitful Versus Void Functions](#fruitful-versus-void-functions)
      * [Parameters](#parameters)
      * [Scoping](#scoping)
      * [Docstrings](#docstrings)
  * [Why Functions](#why-functions)
  * [Additional Work With Functions](#additional-work-with-functions)
- [Lab Notebook Questions](#lab-notebook-questions)

[Link to lab procedure as a Jupyter Notebook](https://drive.google.com/file/d/1flRQmYhhiPiq3tmyr-aQnLVfX8N4O1Az/view?usp=sharing)

# Lecture and Live Coding

Throughout this lab, you will see a Panopto icon at the start of select sections.

This icon indicates there is lecture/live coding asynchronous content that accompanies this section of the lab. 

You can click the link in the figure caption to access these materials (ND users only).

Example:

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=1d06be1d-ba65-478e-a5ad-ad820162cacf">Lab overview</a></td>
  </tr>
  </table>
  
<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
<td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?pid=266f95e7-65bd-4718-9a97-ae300135e32a">Lecture/live coding playlist</a></td>
  </tr>
  </table>

# Lab Notebook Template

Lab notebook template:
- [`.py` file](https://drive.google.com/file/d/1y5HuDUvcFGwQIDog-6kqpImPwcm_-YO5/view?usp=sharing)
- [Jupyter Notebook](https://drive.google.com/file/d/1uJi6ehVbYOPtU1zAYa7jNuznMlizrFq5/view?usp=sharing)


# Functions

<table>
 <tr><td>
<img src="https://elearn.southampton.ac.uk/wp-content/blogs.dir/sites/64/2021/04/PanPan.png" alt="Panopto logo" width="50"/></td>
  <td><a href="https://notredame.hosted.panopto.com/Panopto/Pages/Viewer.aspx?id=1d06be1d-ba65-478e-a5ad-ad820162cacf">Lab overview</a></td>
  </tr>
  </table>

1. In Python, a function is a named sequence of statements that performs a computation.
- Key term: *function*

2. To execute a function, we call it by name and pass it an appropriate set of input arguments.
- Key terms: *function call, input argument*

3. A function takes zero or more arguments as inputs and returns zero or more outputs as a result.

4. The output or result of a function is called the return value.
- Key terms: *function output or return value*

5. Data, parameters, or arguments can be passed into a function.

6. Functions can also return data.

## Built-In Functions

7. We have actually already been working with a number of Python's built-in functions.

8. These include `print()`, `dict()`, `input()`, `int()`, and `len()`.

9. We call built-in functions using the function name, followed by parenthesis.
- `print()`
- `dict()`
- `input()`
- `int()`
- `len()`

## Named Functions

10. But Python also allows you to create (and name) your own functions.
- Key term: *named function(s)*

11. We can define or name a function using the `def` keyword.

12. A function definition includes a few core components:
- The name of the new function
- The list of function arguments
- The sequence of statements to execute when the function is called

13. The core syntax for defining your own function:

```Python
# use def keyword to define function name
def function_name(argument):
 statement(s)
 return result
```

14. Let's unpack each of those components.

15. `def function_name()` is the name you are giving to the function you create- this is the header for the function definition.

16. Function names have many of the same rules as variable names- no spaces or special characters.

17. `argument` is the argument that will be passed to the function.

18. When we are initially defining the function, the `argument` value is typically a placeholder.

19. Later in the program when we call the named function, the argument being passed to the function goes in these parenthesis.

20. The nested or indented line `statement(s)` is the body of the function definition.

21. It includes a sequence of statements to execute when the function is called.

22. The nested or indented line `return result` is a placeholder for the function output or endpoint- it is also part of the body of the function definition.

### How Named Functions Work

23. So what happens when we use the `def` keyword to create a named function?

24. Programs are always executed sequentially, one statement at a time.

25. Function definitions create new functions, but do not execute the bodies or statements within the functions UNTIL the functions are called.

26. When we call a named function, the program jumps to the definition for the function being called, executes the function's body, and then returns to the point in the program where the function was called and resumes executing the program.

27. Let's look at some examples.

#### Named Function Examples

##### Function Example A

28. Let's say we want to create a function that prints an input string three times.

```Python
def printThreeTimes(string):
 for x in range(3):
  print(string)
```

29. To walk through what is happening in this function definition...

30. `def printThreeTimes(string)` assigns the function name (`printThreeTimes`).

31. This is the name we will use when calling this function elsewhere in the program.

32. `for x in range(3)` is part of the body of the function.

33. This line of code uses a `for` loop to say "for each integer value in the range leading up to but not including 3," do.....something!

34. That "something" is the `print` statement nested in the `for` loop.

35. That `print` statement will output the `string` value each time through the `for` loop.

36. Now let's see this named function in action.

```Python
string = "There's no place like home."

printThreeTimes(string)
```

37. We wouldn't need to assign the string to a variable- we could pass it directly to the function.

```Python
printThreeTimes("There's no place like home.")
```

##### Function Example B

38. Let's look at another example.

39. Here, we want to create a function that prints an input string a specific number of times.

<blockquote>Q1: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?</blockquote>

<blockquote>Q2: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?</blockquote>

40. Here is one approach to this task.

41. First, we want to define the name of our function, as well as what input arguments it will take.

42. We know that we need to pass a string to be printed AND an integer for the number of times to the named function.

43. For now, let's call the string `string` and the integer `times`.

44. So the function header could look like:
```Python
def printNTimes(string, times):
```

45. We've named the `printNTimes` function and established we will be passing two arguments to the function.

46. Next, we could us a `for` loop in combination with the `range()` function to accomplish a specific task for a specific number of iterations.

```Python
for x in range(times)
```

47. As in the previous named function example, we can think of the `for` loop as saying "for each integer value in the range leading up to but not including the `times` value," do.....something!

48. That "something" is the `print` statement nested in the `for` loop.

49. That `print` statement will output the `string` value each time through the `for` loop.

50. Putting that all together:

```Python
def printNTimes(string, times):
 for x in range(times):
  print(string)
```

51. So now we have a function that prints our string a number of times specified by the `times` value in combination with the `range()` function.

<blockquote>Q3: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?</blockquote>

<blockquote>Q4: How would you write a program that calls the function you have created? Include code + comments.</blockquote>

<blockquote><a href="https://www.w3schools.com/python/python_functions.asp">Click here</a> for more information on named functions in Python, via W3Schools.</blockquote>

### Additional Functions Considerations

#### Fruitful Versus Void Functions

52. Functions that yield a result are considered fruitful.
- Key term: *fruitful function(s)*

53. To output a result, a function uses the return statement to pass results back to the function call.

54. Functions that perform a computation but do not yield a result are considered void.
- Key term: *void function(s)*

55. By default, the return value for void functions is `None`.

#### Parameters

56. Inside a function, the arguments are assigned to local variables, or placeholder variables.

57. These local variables are called parameters.
- Key term: *parameter*

#### Scoping

58. The name of the parameter inside the function is separated or isolated from the name outside the function.

59. This separation of namespaces is called scoping.
- Key term: *scoping*

60. An example of scoping:

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

61. In short, the placeholder variables (or parameters) we use inside the function definition are separated or isolated from any instance where a variable or parameter with the same name is used outside the function definition.

<blockquote><a href="https://www.w3schools.com/python/python_scope.asp">Click here</a> to learn more about scope in Python, via W3Schools.</blockquote>

#### Docstrings

62. We can add comments to a function definition by including a docstring under the function header.
- Key term: *docstring*

63. As we've learned previously, single-line comments in Python are declared using the `#` symbol, and multi-line comments in Python are declared using the <code>'''</code> symbol.

64. Docstrings are declared using triple single quotes (<code>'''</code>) or triple double quotes (`"""`).

65. Best practice is to start the docstring just below the function header.

66. Another best practice for docstrings is to begin with a capital letter and end with a period.

67. The docstring should briefly describe what the function does.

68. Let's see this in action with an example from earlier in the lab.

```Python
def printThreeTimes(string):
 '''Prints an input string three times'''
 for x in range(3):
  print(string)
```

69. We have a couple options for accessing the contents of the docstring elesewhere in the program.

70. We can use the `__doc__` method (underscore, underscore, doc, underscore, underscore).
```Python
print("Using __doc__:")
print(printThreeTimes.__doc__)
```

71. Or we can use the `help()` function.
```Python
print("Using help:")
help(printThreeTimes)
```

72. Multi-line docstrings can be used to provide additional description about the named function, including information about parameters, arguments, and returns.

<blockquote><a href="https://www.python.org/dev/peps/pep-0257/">Click here</a> to learn more about docstrings in Python, via Python.org documentation.</blockquote>

## Why Functions

73. By this point in the lab, your brain might be hurting. Mine is.

74. Let's take a step back and think about *why* we would want or need to use functions in our code.

<p align="center"><a href="https://github.com/kwaldenphd/python-conditional-statements-functions/blob/main/Python_Function_Meme.png?raw=true"><img class="aligncenter" src="https://github.com/kwaldenphd/python-conditional-statements-functions/blob/main/Python_Function_Meme.png?raw=true" /></a></p>

75. Python functions can help with programming tasks in a number of key ways.

76. They help yield **more concise code*** by eliminating the need to write out code for the same task multiple times.

77. In doing so, they also **improve code readability**.

78. Functions also help us **more effectively test and debug code**.

79. Again, because we are creating reusable pieces or building blocks of code, we can more readily pinpoint where things are going wrong or not working in our code.

80. By allowing us to define and call functions for common tasks, they **promote code reuse and modularity**.

## Additional Work With Functions

Q5: Write a function `is_even` that determines whether or not a number `n` is even. Include code + comments for the function definition as well as a sample function call.

Q6: Write a function `average` that determines the average value of a list. Include code + comments for the function definition as well as a sample function call.

Q7: Write a function `uniq` that takes a list and returns a new list containing only unique values. Include code + comments for the function definition as well as a sample function call.

Q8: The Python code below is suppose to create a function that determines if the given list of numbers is sorted. That is, the function should return `True` if each item in the list is less than the next item. Unfortunately, there are a few errors in the code below. Identify the errors and fix the code. Include your modified code with comments that document what changes you made to address the errors.

```Python
is_sorted([1, 2, 3, 4, 2])

def is_sorted(numbers):
    ''' Return whether or not the list of numbers is sorted '''
    for i in range(len(numbers) - 1):
        if numbers[i] > numbers[i + 1]:
            return False
    return True
```

Q9: In your own words, what is a function?

Q10: In your own words, how do we create a function?

Q11: In your own words, what is an argument or parameter?

Q12: In your own words, what is a return value?

Q13: Why would we use functions, or what is the value of functions?

Q14: Include a link to your Replit workspace for this lab.

# Lab Notebook Questions

Lab notebook template:
- [`.py` file](https://drive.google.com/file/d/1y5HuDUvcFGwQIDog-6kqpImPwcm_-YO5/view?usp=sharing)
- [Jupyter Notebook](https://drive.google.com/file/d/1uJi6ehVbYOPtU1zAYa7jNuznMlizrFq5/view?usp=sharing)

Q1: Describe how you would start building out code to accomplish this task? What functions, statements, or keywords would you need to use? How would you start to organize this program?

Q2: See where you can get with writing this program. What parts of the program were you able to get working? Where did you run into challenges?

Q3: How does the sample program compare to your approach to the previous two questions? What was similar? What was different? How are you thinking differently (if at all) about how to approach this type of program?

Q4: How would you write a program that calls the function you have created? Include code + comments.

Q5: Write a function is_even that determines whether or not a number n is even. Include code + comments for the function definition as well as a sample function call.

Q6: Write a function average that determines the average value of a list. Include code + comments for the function definition as well as a sample function call.

Q7: Write a function uniq that takes a list and returns a new list containing only unique values. Include code + comments for the function definition as well as a sample function call.

Q8: The Python code below is suppose to create a function that determines if the given list of numbers is sorted. That is, the function should return True if each item in the list is less than the next item. Unfortunately, there are a few errors in the code below. Identify the errors and fix the code. Include your modified code with comments that document what changes you made to address the errors.

```Python
is_sorted([1, 2, 3, 4, 2])

def is_sorted(numbers):
    ''' Return whether or not the list of numbers is sorted '''
    for i in range(len(numbers) - 1):
        if numbers[i] > numbers[i + 1]:
            return False
    return True
```

Q9: In your own words, what is a function?

Q10: In your own words, how do we create a function?

Q11: In your own words, what is an argument or parameter?

Q12: In your own words, what is a return value?

Q13: Why would we use functions, or what is the value of functions?

Q14: Include a link to your Replit workspace for this lab.
