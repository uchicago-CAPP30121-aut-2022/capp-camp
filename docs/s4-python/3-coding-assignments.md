---
layout: default
title: Coding Assignments
nav_order: 3
parent: Python Programming
---

# Coding Assignments

In CAPP 30121, you will complete individual and team-based assignments to practice algorithmic thinking and cement your understanding of Python's data structures and syntax. As current and former students of CAPP, we (Marc, Launa, and Ali) encourage you to focus on the bigger picture of skills, _not_ scores, and adopt a [growth mindset](https://jamesclear.com/fixed-mindset-vs-growth-mindset). Some assignments and topics may challenge you. View those as exciting opportunities to stretch yourself en route to becoming a stronger practitioner of data. You'll probably realize that you're having fun along the way!

In this section, we provide general tips for assignments and then end the lab with two mock assignments as exercises. Let's dive in!

## Reading Code and Documentation

When you first receive an assignment, carefully read the instructions and skim the functions that have been scaffolded out for you. Then step through the code line-by-line to understand how data is being transformed from the input to the returned output.

Your course textbook will be an excellent resource for understanding new Python commands. You can also clarify what Python commands are doing by using VS Code's IntelliSense aand referencing official documentation websites. For example, the Python Software Foundation provides [detailed summaries](https://docs.python.org/3/library/index.html) of the Python standard library's data types and the operations that can be performed on those types. [pandas](https://pandas.pydata.org/docs/index.html), a popular Python library used for data analysis, offers an _API reference_ that describes the expected inputs, outputs, and behavior of its functions, as well as "Getting started" and "User Guide" sections that show common usage of the library.

## Planning Your Approach

Once you understand what the pre-existing code is doing, you can start planning your solution to the homework assignment. Some find it helpful to write _pseudocode_—i.e., "fake code" that describes the logical steps of your program without using formal syntax— on paper before actually editing the Python file. For example, we might write:

```
if a number is evenly divisible by 3:
    print "fizz"
else if a number is evenly divisible by 5:
    print "buzz"
else:
    print "fizzbuzz"
```

There are no hard and fast rules about how pseudocode should look. You make the rules; it only matters that you have anticipated how your program will handle different types of input.

## Testing Your Code

After planning your code, you will re-write your informal algorithm as formal Python code and then test your program to see that it is working. There are broadly two ways of doing this:

- **Manual testing:** This involves running the code you wrote with some sample values to check whether it behaves as expected. For example, if you were writing an expression to compute whether a year is a leap year, you may try running your code with IPython3 for a few leap years and a few non-leap years, to see whether your code correctly identifies the leap years.

- **Automated testing:** There are automated testing frameworks that allow you to specify a series of tests you want to run on your code, and which make it easy to automatically re-run all those tests. For example, following the leap year example, you wouldn’t have to manually test each year value one by one; instead, the testing framework would test all these year values for you, and would report back how many produced the expected result.

In CAPP 30121, all the exercises and programming assignments include a suite of automated tests that you can use to check whether your code is working correctly, Furthermore, these tests also factor into your score for an exercise or programming assignment.

Because the automated tests are easy to run (and affect your score for the assignment), you may be tempted to do the following: write some code, immediately try running the automated tests to find a test that fails, make a guess as to how to modify your code, and then repeat the process until all of the tests pass.

This is not a good way to test your code. Instead, you should start by doing some manual testing to get a sense of whether it is working before you try the automated tests.

### Manual Tests

**IPython3** is a great resource for manual testing. For example, let's say you've been asked to complete a function called `add_one_and_multiply` that receives two integers as input (i.e., `a`, `b`), adds one to the first integer, and then multiplies that sum by the second integer. You can start by informally testing your expression with IPython3. For example, you could do this:

```python
In [1]: a = 5

In [2]: x = 2

In [3]: a + 1 * x
Out[3]: 7
```

However, that doesn't seem quite right. The result should’ve been 12 (if we add 1 to 5, that gives us 6, which multiplied by 2 gives us 12). Looks like you need to experiment a bit more in IPython!

Once you believe you have the correct expression, you can update your function with your code and then test the function by importing the larger Python file as a program (called a `module`) in IPython3. For example if `add_one_and_multiply` was located in a file called `sel1.py`, you could write:

```python
In [1]: %load_ext autoreload

In [2]: %autoreload 2

In [3]: import sel1

In [4]: sel1.add_one_and_multiply(5, 2)
Out[4]: 12

In [5]: sel1.add_one_and_multiply(7, 0)
Out[5]: 0
```

The commands `%load_ext autoreload` and `%autoreload 2` load an IPython extension that allows you to make changes to `sel1.py` and automatically those changes reflected in further uses of the `sel1` module. For example, suppose you added `print("hello")` to `add_one_and_multiply` before returning the output, saved `sel1.py`, and then ran `sel1.add_one_and_multiply(7, 0)` in the terminal. The program would print `"hello"` followed by `0`.

If you get the wrong answer for some sample input, stop to reason why your code is behaving the way it is and think about how to modify it to get the correct result.

In short exercises like the one above, it is sometimes enough to look at the code and figure out why it is not working. However, for more complex code, you will want to follow a more rigorous approach. You should make a hypothesis about what might be wrong and use **print statements** to print out key values to help you verify or disprove your hypothesis. Output from the VS Code Python **linter**, found in the "Problems" section of a terminal window, can sometimes reveal errors in logic and style.

Finally, you can find a lot of tips on how to debug your code in the CS Department's [Debugging Guide](https://uchicago-cs.github.io/debugging-guide/). A detailed explanation of how to use **VS Code's built-in debugger** may be found in the [Advanced Section](../advanced/index.md) of the lab.

### Automated Tests

After you've done some manual testing, and get the sense that your function seems to be working for, at least, a few simple inputs, you should try running the automated tests. The tests could reveal that there are still issues with your function and, at that point, you could repeat the same process we described above. The important thing is that you always have an idea in your head about how your code works, and don't make random changes that you don't fully understand.

For automated testing, CAPP 30121 will use the `pytest` framework. (Pytest is available on the remote Linux servers.) To run our automated tests, you will use the `py.test` command from the Linux command line (not from within `ipython3`). We recommend opening a second terminal in VS Code for running this command, which will allow you to go back and forth easily between testing code by hand in `ipython3` in one terminal window and running the test suite using `py.test` in the other. (When we work on assignments, we usually have three windows open: the file we're editing, a terminal for experimenting in ipython3, and another terminal for running the automated tests.)

For example, to run all the tests for `add_one_and_multiply`, you can run the following command from the Linux command-line:

```bash
$ pytest -v -x -k add_one_and_multiply test_sel1.py
```

(Recall that the `$` represents the prompt and is not included in the command.)

Here is what each part of this command means:

- `pytest` indicates that we want to run pytest.

- `test_sel1.py` is the name of the file that contains the testing code. (If you look at this file, you may find some of the syntax unfamiliar; this is okay for now.)

In between these, we specify three options:

- The flag `-v` means run in verbose mode; this gives us a more detailed readout of the test results.

- The flag `-x` means that pytest should stop running tests after a single test failure.

- The option `-k` add_one_and_multiply restricts pytest to only running the tests for add_one_and_multiply. The way the `-k` option works is actually a bit more elaborate but, for now, you can assume that providing the name of the function you’re testing will run only the tests for that function.

Here is (slightly-modified) output from using this command to test our reference implementation of `add_one_and_multiply`:

```bash
$ pytest -v -x -k add_one_and_multiply test_sel1.py
====================================== test session starts =======================================
platform linux -- Python 3.8.5, pytest-3.9.1, py-1.10.0, pluggy-0.13.1 -- /bin/python3
cachedir: .pytest_cache
metadata: {'Python': '3.8.5', 'Platform': 'Linux-5.8.0-59-generic-x86_64-with-glibc2.29',
'Packages': {'pytest': '3.9.1', 'py': '1.10.0', 'pluggy': '0.13.1'}, 'Plugins': {'timeout':
'1.3.2', 'json': '0.4.0', 'metadata': '1.7.0', 'html': '1.19.0'}}
rootdir: /home/username/cmsc12100/short-exercises/test_sel1, inifile: pytest.ini
plugins: timeout-1.3.2, json-0.4.0, metadata-1.7.0, html-1.19.0
collected 26 items / 20 deselected

::test_sel1.py::test_add_one_and_multiply_1 PASSED                                          [ 16%]
::test_sel1.py::test_add_one_and_multiply_2 PASSED                                          [ 33%]
::test_sel1.py::test_add_one_and_multiply_3 PASSED                                          [ 50%]
::test_sel1.py::test_add_one_and_multiply_4 PASSED                                          [ 66%]
::test_sel1.py::test_add_one_and_multiply_5 PASSED                                          [ 83%]
::test_sel1.py::test_add_one_and_multiply_6 PASSED                                          [100%]

- generated json report: /home/username/cmsc12100/short-exercises/test_sel1/tests.json -
============================ 6 passed, 20 deselected in 0.04 seconds =============================
```

This output shows that our code passed all six tests for `add_one_and_multiply`. It also shows that there were 20 tests that were de-selected (that is, were not run) because they did not match the test selection criteria specified by the argument to `-k`.

If you fail a test, pytest will print out some information about what went wrong. For example, let’s say you specified the following expression, which we saw earlier was incorrect:

```python
a + 1 * x
```

This would pass the first test, but would fail the second one:

```bash
$ pytest -v -x -k add_one_and_multiply test_se1.py
====================================== test session starts =======================================
platform linux -- Python 3.8.5, pytest-3.9.1, py-1.10.0, pluggy-0.13.1 -- /bin/python3
cachedir: .pytest_cache
metadata: {'Python': '3.8.5', 'Platform': 'Linux-5.8.0-59-generic-x86_64-with-glibc2.29',
'Packages': {'pytest': '3.9.1', 'py': '1.10.0', 'pluggy': '0.13.1'}, 'Plugins': {'timeout':
'1.3.2', 'json': '0.4.0', 'metadata': '1.7.0', 'html': '1.19.0'}}
rootdir: /home/username/cmsc12100/short-exercises/se1, inifile: pytest.ini
plugins: timeout-1.3.2, json-0.4.0, metadata-1.7.0, html-1.19.0
collected 26 items / 20 deselected

::test_se1.py::test_add_one_and_multiply_1 PASSED                                          [ 16%]
::test_se1.py::test_add_one_and_multiply_2 FAILED                                          [ 33%]

============================================ FAILURES ============================================
__________________________________ test_add_one_and_multiply_2 ___________________________________

    def test_add_one_and_multiply_2():
>       do_test_add_one_and_multiply(a=5, x=2, expected=12)

test_se1.py:17:
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _
test_se1.py:185: in do_test_add_one_and_multiply
    check_equals(actual, expected, recreate_msg)
_ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _ _

actual = 7, expected = 12
recreate_msg = 'To recreate this test in ipython3 run:\n  se1.add_one_and_multiply(5, 2)'

    def check_equals(actual, expected, recreate_msg=None):
        msg = "Actual ({}) and expected ({}) values do not match.".format(actual, expected)
        if recreate_msg is not None:
            msg += "\n" + recreate_msg

>       assert actual == expected, msg
E       AssertionError: Actual (7) and expected (12) values do not match.
E         To recreate this test in ipython3 run:
E           se1.add_one_and_multiply(5, 2)
E       assert 7 == 12

test_se1.py:158: AssertionError
- generated json report: /home/username/cmsc12100/short-exercises/se1/tests.json -
======================= 1 failed, 1 passed, 20 deselected in 0.10 seconds ========================
```

The volume of output can be a bit overwhelming. You should focus on the lines towards the end that start with E. These lines will usually contain a helpful message telling you why the test failed:

```
E       AssertionError: Actual (7) and expected (12) values do not match.
E         To recreate this test in ipython3 run:
E           se1.add_one_and_multiply(5, 2)
```

This information can help you narrow down the issue with your code. This error message, in particular, tells you that, like the manual testing example we saw earlier, the test code expected a return value of 12, but got a return value of 7. It also shows you how to run this test in ipython3. At this point, you should switch back to testing your function in ipython3 until you have fixed the problem.

A few more notes on the `pytest` command and its options:

By default, if you do not supply the name of a specific test file (such as `test_se1.py`), pytest will look in the current directory tree for Python files that have names that start with `test_`.

Because we specified the `-x` option, pytest exited as soon as the second test failed (without running the remaining tests). Omitting the `-x` option makes sense when you want to get a sense of which tests are passing and which ones aren’t; however, when debugging your code, you should always use the `-x` option so that you can focus on one error at a time.

If you don’t use the `-k` option, pytest will run any function that starts with `test_`. You can limit the tests that get run by using the `-k` option along with any string that uniquely identifies the desired tests. The string is not required to be a prefix. For example, if you specify `-k` add, pytest will run test functions that start with `test_` and include the word `add`.

Pytest has many other options that we did not use here. You can see the rest of the options by running the `command py.test -h`.

In general, we will leave out the name of the file with the test code (`test_se1.py`), use short substrings to describe the desired tests, and combine the option flags (`-v`, `-x`, and `-k`) into a single string (`-xvk`). For example, the tests for `add_one_and_multiply` can also be run with the following command:

```bash
$ pytest -xvk add
```

## Obtaining Your Test Score

Your programming assignments will use several criteria for grading, one of which is your score from the automated tests. To retrieve this score, simply run the following from the Linux command-line. (Remember to leave out the `$` prompt when you type the command.)

```bash
$ pytest
$ ./grader.py
```

Notice that we’re running py.test without the `-k` or `-x` options: we want it to run all the tests. If you’re still failing some tests, and don’t want to see the output from all the failed tests, you can add the `--tb=no` option when running py.test:

```bash
$ pytest --tb=no
```

Take into account that the `grader.py` program will look at the results of the last time you ran `py.test` so, if you make any changes to your code, you need to make sure to re-run `py.test`.

You can also just run `py.test` followed by the grader on one line by running this:

```bash
$ pytest --tb=no; ../common/grader.py
```

If you run this inside the `se1` directory, you should see something like this (of course, your actual scores may be different!):

```
Category                                             Passed / Total       Score  / Points
------------------------------------------------------------------------------------------
Exercise 1                                           6      / 6           15.00  / 15.00
Exercise 2                                           4      / 4           15.00  / 15.00
Exercise 3                                           3      / 3           15.00  / 15.00
Exercise 4                                           5      / 5           15.00  / 15.00
Exercise 5                                           4      / 4           20.00  / 20.00
Exercise 6                                           4      / 4           20.00  / 20.00
------------------------------------------------------------------------------------------
                                                                  TOTAL = 100.00 / 100
==========================================================================================
```

## Asking for Help

Again, you may find some programming assignments challenging. This is completely normal and nothing to be ashamed of! One of the advantages of studying a subject within a university environment is having access to a large learning community of faculty instructors, staff, teaching assistants, peers, and technical support. Sometimes, you will be the one explaining concepts others, and in some cases you will need to ask for help.

For CAPP 30121, you will ask questions on the Ed platform. We encourage you to carefully read through the [explanation](https://edstem.org/us/courses/24735/discussion/1675332) of how to properly ask questions there. To reiterate, when making a post, you should:

- Confirm that you have actually asked a question rather than making a request. You should also confirm that your question has not already been answered by an instructor or TA, and that you are asking only _one_ question at a time.

- Include details about where the code is being executed (e.g., the remote Linux server) as well as your OS version, the chain of events leading up to the error, and the full and unabridged error message.

- Avoid using screenshots and never post your code; the latter could result in a violation of Academic Honesty policies. If you need to share your code, just push it to GitHub and the course staff will look at it there.

- Make sure your post is public if it is not a family or medical emergency or an otherwise sensitive matter. Public posts will also help your classmates if they run into similar issues.

As a courtesy to the course staff, if you've found the answer to your own question, please note that the issue has been resolved. If your question related to a technical setup error, add a brief description of how you solved the problem to help others.

## Next Steps

In the next section, we will practice the programming assignment workflow by completing a mock assignment and then submitting it for grading.

{:style="text-align:center"}
[Previous](./2-vs-code-for-python.html){: .btn } [Next](./4-exercises.html){: .btn }
