[![General Assembly Logo](https://camo.githubusercontent.com/1a91b05b8f4d44b5bbfb83abac2b0996d8e26c92/687474703a2f2f692e696d6775722e636f6d2f6b6538555354712e706e67)](https://generalassemb.ly/education/web-development-immersive)

# Python

Hey, Polyglots! Ready for another programming language?

## Prerequisites

Developers would greatly benefit from being able to accomplish the following in at least one other higher language:
-   Iterate through an array of elements
-   Declare, define, and evaluate variables
-   Understand the concepts of Object-Oriented-Programming
-   Demonstrate the ability to use conditional expressions to execute code based on given conditions
-   Write functions that receive parameters and return data

## Objectives

By the end of this, students should be able to:

-   Contrast Python REPL with the JS REPL node.
-   Contrast basic language features and types from Python with basic language features and types from Javascript.
-   Write a simple script in Python.

## Preparation

1.  Fork and clone this repository.

## Installation

1.  `brew install pyenv`
1.  `pyenv install 3.5.1`
1.  `pyenv global 3.5.1`
1.  Python doesn't ship with the most up to date version of package manager
pip, so upgrade pip : `pip install --upgrade pip`
1.  `brew install pyenv-virtualenv`
1.  Add the following to `~/.bashrc`:

    ```bash
    eval "$(pyenv init -)"
    eval "$(pyenv virtualenv-init -)"
    ```
1. Open a new terminal.

## Python REPL

We'll be using Python's built-in REPL to practice what we learn today.

Typing `python` onto the command line will bring you into this REPL, similar to calling `node` to run the `node` REPL.

To run Python scripts, simply run
`python <filename.rb>` from the command line. To run Python in version 2.7.0 or the original Python version install on your machine, run `pyenv use 2.7.0` in your terminal.

_Hint: to print to the console in Python, we use `print(<string to print>)`_

Let's practice this. Take a minute to look at [lib/test.py](lib/test.py),
then run the `test` script from the command line using
`python lib/test.py`.

## Core Syntax, Variables, and Operators

### Syntax

The default variable syntax uses snake case; as in `keep_your_variables_defined_this_way` and `we_are_in_pythons_house_now`.

**Parens** `()` in Python are required around parameters.

There is a lack of semicolons in Python. Line breaks in your
code are enough to denote the end of an expression.

However, as you may have noticed from our `test` script, we are introduced
to **colons** `:` throughout our code. Colons always come directly after the
first line of the block statement. Colons are also immediately followed by a
new, indented line (this indentation is purposeful **whitespace**).

Python's colons/whitespace combo act as an 'end' for method
declarations and loops.

In Python, it is critical to consider whitespace usage when
ensuring working code. Otherwise, you'll run into an `IndentationError`.

### Variable Declaration

Variables can be defined without being previously declared. Variable reassignment is also very flexible.

```python
>>> x = 2 # assigns x to numerical value 2
>>> x = "This is Dane." # reassigns x to string value
```

Also similar to Ruby, variables in Python _cannot_ be called or stated without
being defined.

```python
>>> z
NameError: name 'z' is not defined
```

### True and False

In Python, true and false are represented by `True` and `False` (yes, case
matters).

The falsy values of Python are:

`False` `None` `0` `0.0` `''` `[]` `{}`

`None` is equivalent to Javscripts's `null`.

### Operators

|                      |        Ruby                          |        Python               |
|:---------------------|:------------------------------------:|:---------------------------:|
| logical operators    | `&&`, <code>&#124;&#124;</code>, `!` | `and`, `or`, `not`          |
| relational operators | `==` `!=` `>` `<` `>=` `<=`          | `==` `!=` `>` `<` `>=` `<=` |
| arithmetic operators | `+`, `-`, `*`, `/`, `%`         | `+`, `-`, `*`, `/`, `//`, `%`     |

#### Brief Aside: Double Slash (`//`) Operator

Python has two division operators, a single slash character for classic division and a double-slash for “floor” division. Classic division means that the result will be true division (i.e. can be a float), whereas floor division means the answer will always be rounded down to the nearest whole number.

In Python, this whole integer division behavior can be mirrored with the `//`
operator.

```python
>>> 14.5 / 3    # => 4.833333
>>> 14.5 // 3   # => 4.0
```

Note that operations on floats will still return floats no matter the operator.

To convert between floats and integers, use:

```python
>>> int(14.5)    # => 14
>>> float(14)    # => 14.0
```

## Lab: Practice Using Operators

Let's get used to these operators.

In your Python REPL from the command line, take some time to practice each
logical, relational and artithmetic operator listed for you above.

## Strings

In Python, there is no difference between using `" "` or `' '`.
[Escape Characters](http://python-reference.readthedocs.io/en/latest/docs/str/escapes.html)
are evaluated in both.

```python
>>> print("This is a \n new line.")
# => This is a
# => new line.

>>> print('This is a \n new line.')
# => This is a
# => new line.
```

### String Interpolation

There are many options for string interpolation in Python. For our
purposes, we'll be using `.format()`, as it is preferred for Python 3.5.

`.format()` is appended to a string and takes a parameters the strings to be
concatenated. If the string contains empty `{}`s, the parameters fill the `{}`s
in the order passed in. If they contain a number (beginning with 0), they will
be mapped to the parameter passed to `.format()` at said index.

```python

>>> awkward_nerd = "Justin"
>>> awesome_nerd = "Wes"
>>> occupation = "instructor"

>>> "{} is a pretty cool {}.".format(awkward_nerd, occupation)
# => "Justin is a pretty cool instructor."

>>> "{0} is a {1}. {2} is a {1} as well.".format(awkward_nerd, occupation, awesome_nerd)
# => "Justin is an instructor. Wes is an instructor as well."
```

## Flow Control

### Conditionals

Again, colons and whitespace are critical to working Python code. Aside from
that and the use of `elif` vs. `else if`, these should feel very similar to Javascript conditional statements.

```python
if x < 0:
  print('Negative')
elif x == 0:
  print('Zero')
else:
  print('Positive')
```

### Loops

Also like Javascript, Python employs `while` and `for` loops.

Python also allows for an optional `else` statement with each of these. With
`while` loops, the `else` statement is executed once the `while` condition is
no longer true. With `for` loops, `else` is executed upon the loop's
completion.

```python
count = 0
while count < 5:
   print(count, " is  less than 5")
   count = count + 1
else:
   print(count, " is not less than 5")
```

```python
count = 15
for i in range(1,count):
  print(i)
else:
  print("done")
```

Again, this `else` is optional and different in nature from a conditional else.
It functions more as a completion handler.

## Functions

Functions in Python are similar to Ruby methods (Python also has methods, but
we only refer to them as such when they are functions of a Class).

Aside from syntactical differences, the main difference to note is the need for
an **explicit return**. Think JavaScript!

Basic function structure:

```python
def function_example(param_one, param_two):
  """Example function returning string interpolation of parameters."""
  concat = "What a splendid function! I've got my {0} and {1}.".format(param_one, param_two)
  return concat
```

#### Brief Aside: Docstrings

You may have noticed something like

`"""This function..."""`

within each of our example functions. These are called `docstrings` and are
conventionally used in Python to provide documentation throughout a codebase.
Code will run fine without them, but that would stray from Python's conventions
as well as throw you into linter message hell. Try them out!

## Exercises: Python Functions

Write the following functions in your `lib/` directory:

1. `mad_libs.py` – 
  Input: `name`, `age`, `job`, `city`, and `state`
  Output: sentence with properly formatted arguments

  Example:

```python
  mad_libs('Paul', 35, 'veterinarian', 'Denver', 'CO')
  # => 'Paul is 35 years old and works as a veterinarion in Denver, CO.'
```

1. `meow.py` – 
  Input: `num`
  Output: sentence with 'meow' `num` times

  Example:

```python
  meow(4)
  # => 'meow 
  meow 
  meow 
  meow'
```

1. `countdown.py` – 
  Input: `num`
  Output: blastoff countdown sentence starting from `num` and incrementing down

  Example:

```python
  countdown(7)
  # => '7! 
  6! 
  5! 
  4! 
  3! 
  2! 
  1! 
  Blastoff!'
```

1. `division_message.py` – 
  Input: `first_num`, `second_num`
  Output: sentence displaying answer and remainder

  Example:

```python
  division_message(7, 2)
  # => 'The answer is 3, with a remainder of 1'
```

1. `umbrella.py` – 
  Input: `currently_raining` (boolean), `storm_probability` (float number between 0 and 1)
  Output: True or False, depending on whether you should carry an umbrella (return True if `currently_raining` or storm probability is over 50%)

  Example:

```python
  umbrella(True, 0.1)
  # => True

  umbrella(False, 0.1)
  # => False

  umbrella(False, 0.67)
  # => True
```

BONUS: Fill out `fizzbuzz.py` (requirements inside file).

## Lab: Build a Calculator

In [lib/calculator.py](lib/calculator.py), create a calculator function that
takes two parameters. The first should be the operation to be completed
(`addition`, `subtraction`, `multiplication`, `division`). The second should be
a list with the appropriate number of numbers to operate on. The function
mapped to the appropriate operation should take the expected numbers by index
from the list passed in and return back to you the result of the operation.

We haven't discussed lists yet, but they are very similar to Javascript arrays. The
syntax required for this is very similar to how you would approach this in
Javascript.

Remember, to run a Python script from the command line:

`python <filename.py>`

## Collections

### Lists

Python lists are comparable to Ruby arrays. They store comma separated values
of varying data types between square brackets `[]`.

Lists are ordered, thus, indices can be leveraged to get or set their elements.

```python
wdi_base_langs = ["JavaScript", "Ruby", "SQL"]
wdi_base_langs[2] # => "SQL"
wdi_base_langs[0] = "JS" # => ["JS", "Ruby", "SQL"]
```

`len()` is used to get the length of a list in Python.

```python
len(wdi_base_langs) # => 3
```

We can merge lists together using the `+` operator:

```python
wdi_new_langs = ["Python"]
all_wdi_langs = wdi_new_langs + wdi_base_langs # => ["JS", "Ruby", "SQL", "Python"]
```

#### List Methods

We could have gone about adding "Python" to the end of the `wdi_base_langs`
list by using `.append()`.

```python
wdi_base_langs.append("Python") # => ["JS", "Ruby", "SQL", "Python"]
```

Like Ruby, `.pop()` removes the last element from a Python list. `.append()`
will add to the end of a list.

We do not have built-in operators for removing or adding to the beginning of a
list. As hackers, we've got some hacks, though.

`.remove()` allows us to remove an element at any index. Thus, `list.remove(0)`
would remove the first element from a list.

We could implement our array merging to add to the beginning of a list. Look at
the following:

```python
a = "first"
b = ["second", "third"]
[a] + b # => ["first", "second", "third"]
```

#### Looping Through Lists

`for` loops with lists don't stray far from the loops we saw earlier.

```python
all_wdi_langs = ["JS", "Ruby", "SQL", "Python"]

for lang in all_wdi_langs:
  print(lang)
```

### Dictionaries

Python dictionaries are very similar to other key-value objects we've seen.

Dictionary keys **must** be unique. Creating a key-value pair for a key that
already exists will simply reassign the value of the existing key.

Keys can be either strings or numbers.

There are two ways of instantiating a Python dictionary:

```python
new_dict = dict()   # => {}
# or
new_dict = {}       # => {}

example_dict = {
  "key_one": "val one",
  "key_two": "val two",
  "key_three": "val three"
}
```

To add or retrieve a key-value pair, we implement square bracket notation:

```python
new_dict["fun_key"] = "fresh"
new_dict["fun_key"]    # => "fresh"
```

`.get()` is another option for retrieving a key's value.

```python
new_dict.get("fun_key") # => "fresh"
```

Dictionary defaults are a little different from object literals in Javascript. If it is unknown that a key you are retrieving exists, you can call `.get()` with a default value
should it not exist.

```python
new_dict.get("no_key", "not there") # => "not there"
```

## Lab: Revamp FizzBuzz

In [lib/list_and_dict_buzz.rb](lib/list_and_dict_buzz.rb), build a more robust
FizzBuzz from scratch. Create a dictionary containing keys `fizz`, `buzz`,
`fizzbuzz`, and `other`, each with lists as values. As you iterate through all
the numbers from 1 to max_num, add each number to one of the lists mentioned
above; numbers divisible by 3 only should go into the `fizz` list, numbers
divisible by 5 only should go into the `buzz` list, numbers divisible by both
should go into the `fizzbuzz` list, and numbers divisible by neither should go
into the "other" list. Finally, once you're done, print the resulting
dictionary to check that your code works properly.

## List Comprehensions

Python supports a concept called "list comprehensions" to construct lists in a very easy and intuitive way.

List comprehensions all follow the same format: 

```
[expression for item in list]
```

You can use list comprehensions with an expression like `x + 1` below:

```python
scores = [83, 72, 94, 87, 98]

incremented_scores = [ x + 1 for x in scores]
# => [84, 73, 95, 88, 99]
```

You can add conditionals at the end of a list comprehension to determine whether an element in a list should be returned in the resulting list: 

```python
my_nums = range(20)
number_list = [ x for x in my_nums if x % 2 == 0]
```

You can also use list comprehensions with a function call like `increment(x)` below:

```python
scores = [83, 72, 94, 87, 98]

def increment(score):
  return score + 1

incremented_scores = [ increment(x) for x in scores]
```

## Exercises: Python List Comprehension
Write the following functions in your `lib/comprehensions/` directory:

1. `percentages.py` – 
  Input: `test_scores` list, `perfect_score`
  Output: list of percentages

  Example:

```python
  percentages([5, 10, 20, 30], 50)
  # => [10, 20, 40, 60]
```

1. `passing_grades.py` –
  Input: `test_scores` list, `perfect_score`
  Output: list of grades 75% or above

  Example:

```python
  percentages([75, 85, 65, 95, 50], 100)
  # => [75, 85, 95]
```

1. `grades.py` –
  Input: `test_scores` list, `perfect_score`
  Output: list of grades ( < 60 - 'F'; < 70 - 'D'; < 80 - 'C'; < 90 - 'B'; <= 100 - 'A')

  Example:

```python
  percentages([75, 85, 65, 95, 50], 100)
  # => ['C', 'B', 'D', 'A', 'F']
```

## Additional Resources

-   [Python's Documentation](https://docs.python.org/3/)

## [License](LICENSE)

Source code distributed under the MIT license. Text and other assets copyright
General Assembly, Inc., all rights reserved.
