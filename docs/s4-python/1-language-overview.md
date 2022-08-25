---
layout: default
title: A Brief Teaser
nav_order: 1
parent: Python Programming
---

# A Brief Teaser

Python, named after the 1970s BBC comedy show "Monty Python's Flying Circus", has its origins in the Netherlands. In 1987, Dutch scientist Guido van Rossum began developing the programming language as a side project at the national research institute CWI, eventually releasing it to the public in 1991. Since then, the language has gone through several versions (the latest stable version being 3.10.6) and exploded in popularity. The latest [Stack Overflow Developer Survey](https://survey.stackoverflow.co/2022/#most-popular-technologies-language), conducted in May 2022 with over 70,000 respondents, reported that Python was the fourth most popular technology behind JavaScript, HTML/CSS, and SQL. The TIOBE Index, a monthly indicator of programming popularity, reported in [August 2022](https://www.tiobe.com/tiobe-index/) that Python was _the_ top language.

Your instructors for CAPP 30121 have chosen to use Python rather than another common language like Java, C, or C++ because it offers several advantages, such as greater readability. In addition, it is free, open-source, and general purpose; offers a rich and growing collection of libraries for data science and machine learning; and is currently used extensively within both academia and industry.

In this section, we will not attempt to teach Python. Rather, we will introduce some of its basic symbols and syntax to (a) give you a better understanding of the Python-specific features offered by VS Code and (b) allow you to practice writing Python expressions in the final exercise. Let's get started!

## Anatomy of a Python File

Your programming assignments will require you to edit Python files, which end in `.py`. These files will have a similar structure:

**Docstring**.  At the very top of the file, you will find a docstring that starts and ends with a series of three quotation marks. When you run your Python program, the contents of the docstring will be ignored. Docstrings are used for informational purposes, such as conveying the name of the program, its author, and a brief description.

```
'''
Epidemic modelling

Launa Greer

Functions for running a simple epidemiological simulation.
'''
```

**Imports**:  Below the doc string, you will often find a series of one-line statements beginning with the word `import`. The `import` keyword allows your Python program to access logic from another Python program. The Python language has a standard library of Python programs, called _modules_, that can be imported. For example, in the code snippet below, the `random` module is being imported so the "Epidemic modelling" program can call it to generate pseudo-random numbers.

```
'''
Epidemic modelling

Launa Greer

Functions for running a simple epidemiological simulation.
'''

import random
import click
```

**Logic**:  After the `import` statements, the main logic of the program begins. You've already seen `print` commands in previous lessons. Printing "Hello, World!" to the terminal is a simple example of program logic.

## Example Data Types

Below are three of Python's built-in data types that we'll reference as we practice writing code. You will learn about these data types and others in more detail during CAPP 30121:

### `int` (integer)

Integers are whole numbers that can be positive, negative, or zero. Examples include `-10`, `0`, `3`, and `49999`. In the current major release of Python ("Python 3"), there are no explicit restictions on how big integers can be. The amount of memory available on your machine is the practical limit.

Integers can be added (`+`), subtracted (`-`), multipled (`*`), and raised to a power (`**`). They can also be divided using either _true division_ (`/`) or _floor division_ (`//`). Floor division only takes the whole number part and not the decimal part following a normal/true division operation. For example, `5 / 2` would return `2.5` but `5 // 2` would return `2`. You can also calculate the _modulo_ of two integers—i.e., their remainder following true division—using `%`. `5 % 2` would return `1` because 5 divided by 2 equals 2 with a remainder of 1.

When applying several operations in sequence, normal _order of operations_ is followed. Mathematical expressions in parentheses are evaluated first, followed by exponents, multiplication and division from left to right, and finally, addition and subtraction from left to right.

#### Checkpoint

In your terminal, type `ipython3` to launch an interactive Python shell where you can test Python commands. Then run the following expressions to confirm their value. (Note: You **don't** need to type "In[1]" or "Out[1]"; those are examples of what you would see as output in the terminal.)

**Order of Operations**
```python
In [1]: ((4 - 5) + 3)**2
Out [1]: 4
```

**Normal/True Division**
```python
In [2]: 4 / 5
Out [2]: 0.8

In [3]: 4 // 0
Out [3]: ---------------------------------------------------------
ZeroDivisionError       Traceback (most recent call last)
Input In [12], in <module>
----> 1 4 // 0

ZeroDivisionError: integer division or modulo by zero
```

**Floor Division**
```python
In [4]: 4 // 5
Out [4]: 0
```

**Modulo**
```python
In [5]: 4 % 5
Out [5]: 4

In [6]: 6 % 3
Out [6]: 0

In [7]: 5 % 4
Out [7]: 1
```

Try out a few more commands on your own to get a sense of how these operators are used!

{: .note}
When you attempted to divide by zero, Python raised an _exception_ called `ZeroDivisionError`. Whenever Python programs encounter an error, they immediately raise a exception and _terminate_ (i.e., stop running) unless the exception is "caught" and handled by the programmer. We won't cover how to catch exceptions in this camp, but that knowledge will be indispensible for future CS coursework. For now, you should observe that exceptions print helpful error messages to the terminal that help you understand what went wrong.  They also provide a _stack trace_ showing where in the program the error occurred.


### `float` (floating point number)

`float` represents numbers that have a decimal point. `3.45`, `-0.9`, and `2003.0` are all examples. The data type's name comes from the fact that its decimal point can "float" to wherever it's needed based on how the data is stored in computer memory. Unlike integers, floats have a maximum and minimum value defined by Python. There are also special values of positive or negative infinity that can be referenced using `float('inf')` and `float('-inf')`, respectively.

Like `int` values, `float` values can be added (`+`), subtracted (`-`), multiplied (`*`), divided (`/`), and raised to a power (`**`). Here we should note that normal/true division always results in a `float`, regardless of whether the numbers you're dividing with are integers or floats. Test the following expressions in IPython3 to confirm. In this case, the function `type` returns the Python data type of the numerical expression after it is evaluated to a single number:

```python
In [8]: 2 / 2
Out [8]: 1.0

In [9]: type(2 / 2)
Out [9]: float

In [10]: type(2.0 / 2.0)
Out [10]: float

In [11]: type(2.0 / 2.0)
Out [11]: float

In [10]: type(2.0 / 2.0)
Out [10]: float
```

In addition, if you do an arithmetic operation that mixes floats and ints, the answer will always come back as a `float` data type:

```python
In [10]: 5.0 + 2
Out [10]: 7.0

In [11]: type(5.0 + 2)
Out [11]: float

In [12]: 5 * 2.0
Out [12]: 10.0

In [13]: type(5 * 2.0)
Out [13]: float
```

{: .warning}
> **Important: beware of floating point rounding!**  
> 
> Computers store data within _bits_ of memory. Each bit can hold a value of 0 or 1. Therefore, we say that computers store numbers using a base-2, or _binary_, system because only two digits are available. By contrast, we write numbers in everyday life using a base-10 system in which 10 digits, 0 through 9, are used.
>
> Unfortunately, some numbers with decimals infinitely repeat when converted from base-10 to base-2. As a result, the computer has to truncate the number of digits to save memory, which leads to unexpected rounding errors. For example, try out the following expressions in IPython3:
> 
> ```
> In [14]: 0.1 + 0.2
> Out [14]: 0.30000000000000004
>
> In [15]: 0.1 + 0.1
> Out [15]: 0.2
>
> In [16]: 0.1 * 2
> Out [16]: 0.2
>
> In [17]: 0.1 * 3
> Out[17]: 0.30000000000000004
>
> In [17]: 0.1 * 4
> Out[17]: 0.4
>
> In [17]: 0.1 * 5
> Out[17]: 0.5
>
> In [17]: 0.1 * 6
> Out[17]: 0.6000000000000001
>
> In [18]: 0.1 * 7
> Out [18]: 0.7000000000000001
> ```
>
> Umm...what is going on here? The answer is: round-off errors. In the first example, `0.01` and `0.02` each become infinitely repeating binary fractions when converted from base 10 to base 2, so their sum does not exactly equal `0.3`.  Other results, like `0.1 + 0.1` are also infinitely repeating binary decimals, but Python displays them as terminating decimals due to how its internal rounding algorithm is implemented.
>

### `bool` (boolean)

Booleans are `True` and `False` values. You can use logical operators like `and`, `or`, and `not` to create boolean statements:

- `not` is a negation. For example, `not True` would yield `False`.

- `and` requires that both conditions on either side are `True`. `False and True` would therefore evaluate to `False`.

- `or` requres that one of the conditions are true. `False or True` would therefore evaluate to `True`.

You can also use comparison operators like equals (`==`), not equals (`!==`), greater than (`>`), less than (`<`), greater than or equal to (`>=`), and less than or equal to (`<=`) to create booleans.  For example: `5 == 3` would output `False` and `(40 / 10) >= 1` would output `True`.

Like numeric types, parentheses will also dictate the order in which expressions are evaluated.


#### Checkpoint

Run the following commands in IPython3 and then test more of your own:

**`and`, `or`, and `not` Operators**

```python
In [19]: not(not False)
Out [19]: False
```

```python
In [20]: not(False) or True
Out [20]: True
```
```python
In [21]: not(False or True)
Out [21]: False
```

**Comparison Operators**

```python
In [22]: 100 == 100
Out [22]: True
```

```python
In [23]: -10 < -9
Out [23]: True
```

{: .warning}
> **Don't directly compare floating point numbers!**  
> 
> As we saw above, certain decimal numbers cannot be represented precisely as binary numbers. Therefore, you should avoid directly comparing floating point numbers, which represent decimals in binary. For example, the following expression does not evaluate to the expected result:
> 
> ```
> In [24]: 0.1 + 0.2 == 0.3
> Out [24]: False
> ```
>
> Again, this occurs because `0.1 + 0.2` is close but not directly equal to 0.3.
>


## Variables

We have been generating Python expressions. The values aren't saved anywhere after Python has finished evaluating them. To save the result of an expression, we use _variables_.  You define the name for your variable, followed by an equal sign, and then the expression. For example:

```python
pi = 3.14159
radius = 2
circle_area =  pi * radius ** 2
circle_circumference = 2 * pi * r
```

As shown above, Python has certain expectations and conventions for variable names. 

- A variable name must start with a letter or an underscore (`_`).

- A variable name can _only_ contain alphanumeric characters and underscores (`A-z`, `0-9`, and `_ `).

- Variable names are case-sensitive. `my_var` and `MY_VAR` would be considered two separate variables.

- Variable names use **snake case**, where all letters are lowercase and spaces are represented by underscores.

### Checkpoint

In your terminal with `ipython3` running, practice creating a variable and printing its value using `print`. The variable will live in memory until the terminal is closed.

```python
In [12]: plancks_constant = 6.62607 * 10**-34

In [13]: print(plancks_constant)
6.62607e-34
```

```python
In [14]: 1_invalid_num = 200 # Invalid variable names will cause Python to throw a syntax error
Input In [14]
    1_invalid_num = 200
     ^
SyntaxError: invalid decimal literal
```

## Control Flow

Now that we have expressions and variables, we can begin writing statements that affect Python program's _control flow_, or the order in which it executes statements. For now, we will do this using conditional blocks.

### if-elif-else Blocks

Sometimes we only want to execute code if a condition is satisifed.  Python enables this functionality by providing `if`, `elif`, and `else` conditional statements.  For example:

```python
min_rider_height = 48
max_rider_height = 84
rider_height = 36

if rider_height < min_rider_height:
    print("Sorry, you must be at least", min_rider_height, "inches.")
elif rider_height > max_rider_height:
    print("Sorry, you can't be any taller than", max_rider_height, "inches.")
else:
    print("Sure, you can ride the roller coaster.")
```

If the first condition evaluated at `if` is `True`, Python will execute everything underneath that `if` statement (i.e., within the "if block") without evaluating the other conditions. The program will print out `Sorry, you must be at least 48 inches.`.

If the first condition evaluated at `if` is `False`, Python will move to evaluate `elif` ("else if") instead.  If that condition is `True`, that "elif block" will be run, and the program will print `Sorry, you can't be any taller than 84 inches.`. You can have as many `elif` blocks as you want between the initial `if` statement and the final `else` statement.

If all of the previous conditionals evaluate to `False`, then the `else` statement is executed.  Therefore, if you are greater than 36 inches and shorter than 84 inches, the program would print `Sure, you can ride the roller coaster.`.

It is important to emphasize here what the conditional block looks like. Each `if`, `elif`, and `else` statement ends with a colon (`:`) and the code underneath it is indented.  Python uses _indentation_ to indicate a block of code. Python permits you to use one or more spaces for indentation. The only requirement is that you use indentation consistently across your Python file.  In CAPP 30121, you will use four spaces to indent.

### Functions

The above example was contrived; what if we wanted to call the if-elif-else block repeatedly with different rider heights?  To accomplish this, you would use a `function`.  We won't go over functions in great detail now. In your first few assignments for CAPP 30121, you will be writing logic within functions that have already been created for you.  At this moment, it is just helpful to understand that a function receives inputs called "arguments" and then performs operations on those arguments to return output.Functions are called from other places in a Python file or may be used in a different file altogether.

For example, if we wanted to write a function for our conditional block, it would look something like this:

```python
def assess_rider_height(rider_height):
    """
    Prints a message to the terminal
    summarizing whether the given height
    permits the rider to go on 
    a roller coaster.

    Inputs:
        rider_height (int): The rider
            height in inches.

    Returns:
        None    
    """
    min_rider_height = 48
    max_rider_height = 84

    if rider_height < min_rider_height:
        print("Sorry, you're not tall enough to ride.")
    elif rider_height > max_rider_height:
        print("Sorry, you're too tall for this ride.")
    else:
        print("Sure, you can ride the roller coaster.")
```

And then we would call it later in our Python script like this, with some sample values:

```
assess_rider_height(20)
assess_rider_height(68)
assess_rider_height(90)
```

A function starts with the keyword `def` followed by the function name (here, `assess_rider_height`) and a pair of parentheses.  Inside the parentheses, you can define what inputs are accepted. Here, `rider_height` is accepted. When you call function farther down the script with `assess_rider_height(20)`, the value `20` is passed in for the `rider_height`. Then the rest of the statements are evaluated and the correct `print` command is made.  In this case, the function doesn't explicitly return any value using the `return` keyword, so the `return` value is understood to be the Python value `None`.

Note also the presence of a function docstring, defined by two sets of triple quotation marks (`"""`). Like a file docstring, function doc strings provide helpful information to other programmers. Function doc strings commonly summarize what the function does, what inputs are accepted, and what value (or values) will be returned.

To provide a simple, second example:

```python
def square(n):
    """
    Squares an integer.

    Inputs:
        n (int): The integer.

    Returns (int): The result.
    """
    return (n)**2


print(square(3)) # Will print 9
print(square(-4)) # Will print 16
```

The above function is declared again using the keyword `def` and given the name `square`. Square takes an integer `n` as input and then returns that integer raised to the second power. Here we see an explicit `return` statement that will return the integer result.

#### Checkpoint

Copy and paste the function into the terminal. Press Enter (Return) until `ipython3` recognizes that you are done entering input. Then try calling the function as shown above with different values.


## Next Steps

Even with this small sample of Python's available data types and control flow mechanisms, we can compose complex programs! You will learn more about how VS Code helps with Python programming and gain practice writing Python expressions in the upcoming sections.

{:style="text-align:center"}
[Previous](./index.html){: .btn } [Next](./2-vs-code-for-python.html){: .btn }
