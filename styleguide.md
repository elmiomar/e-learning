# Style Guide

<!-- toc -->
## Table Of Content

  - [Code Layout](#code-layout)
    - [Indentation](#indentation)
    - [Maximum Line Length](#maximum-line-length)
    - [Blank Lines](#blank-lines)
    - [Imports](#imports)
    - [String Quotes](#string-quotes)
    - [Comments](#comments)
    - [Docstrings](#docstrings)
  - [Naming Conventions](#naming-conventions)
  - [Testing](#testing)
  - [Linting](#linting)
  - [References](#references)

> Note: This document assumes the use of Python 3.


## Code Layout

### Indentation

tl;dr: __4 spaces, no tabs__.

Indentation in Python is a language requirement and not a matter of style. Python code blocks are structured through indentation.

Indentation issues will raise errors of type `IndentationError` when compiling the code.

Tabs or spaces? Spaces are preferred for indentation. We use 4 spaces for indentation, no tabs.

>Note: Python 3 does not allow using both spaces and tabs. Tabs can be used for backward compatibility.


### Maximum Line Length

Similarly to the Python standard library, we limit:
- lines to 79 characters
- docstrings/comments to 72 characters


### Blank Lines

Function and class definitions are surrounded by two blank lines.

Method definitions inside a class are surrounded by a single blank line.

Extra blank lines can be used to separate logical sections inside functions.


### Imports

Imports are placed at the top of the file, after comments/docstrings, and beofre globals and constants.

The order of imports should be as follows:
 - Standard library imports
 - Third party imports
 - Local application imports

These import groups should be separated by a blank line.

Avoid using wildcard imports (`from <module> import *`).

### String Quotes

In Python, single-quoted strings and double-quoted strings are the same.

We use double-quoted strings.

For readability's sake, when a string contains single or double quote characters, use the other to avoid using backslashes in the string, example:

```python
print("This program says 'Hello World!'")
```

### Comments

A comment should be a complete sentence, starting with a capitalized word and ending in a period.

Example:

- good
  
```python
# This is a good comment.
```

- bad

```python
#this is a bad comment
```

Comments should be in english, clear, and easily understanble.

An inline comment is a comment on the same line as a statement. We discourage using inline comments.

Use comments sparingly. Sometimes, small methods are better and more readable than comments, example:

- bad

```python
# Check if number is even.
if number % 2 == 0:
    print('Number is even.)
```

- good

```python
def is_even(number):
    return number % 2 == 0


if is_even(number):
    print('Number is even.)
```

### Docstrings

Docstrings is short for __Documentation Strings__. A docstring is a string literal, and the first statement in a module, function, class or method definition.

As per [PEP-257](https://www.python.org/dev/peps/pep-0257/):
- all modules should normally have docstrings, and all functions and classes exported by a module should also have docstrings.
- public methods (including the `__init__` constructor) should also have docstrings.
-  a package may be documented in the module docstring of the `__init__.py` file in the package directory.


There are two forms of docstrings: one-liners and multi-line docstrings:
- one-liner docstring example:

```python
def hello_world():
    """Function that returns a 'Hello World!' message"""
    print('Hello World!')
```
- multi-liner docstring example:

```python
def hello_world(name):
    """Function for greeting the user.
    
    Arguments:
    name -- the user's name.
    """
    print('Hello ', name)
```

The chances of remembering what different parts of the code do are slim. That is why it is recommended to write docstrings. Docstrings are imporant to understand what a module, function, class or method does.

For more details, [PEP-257](https://www.python.org/dev/peps/pep-0257/) is the definitive guide to dosctrings.


## Naming Conventions


- For variables, functions, methods, packages, and modules, we use:
  -  `lowercase_with_underscores` (or *snake_case*)
- For classes and exceptions:
  - `CapitalizedWords` (or *CamelCase*)
- Constants
  - `ALL_CAPS_WITH_UNDERSCORES`
- Protected methods and internal functions
  - `_single_leading_underscore(self, ...)`
- Private methods
  - `__double_leading_underscore(self, ...)`


## Testing
- unittest
- pytest: https://docs.pytest.org/en/stable/goodpractices.html


## Linting

- pylint


## References

- [PEP 8 -- Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008)
- [Google Python Style Guide](https://github.com/google/styleguide/blob/gh-pages/pyguide.md)
- [The Hitchhiker’s Guide to Python -- Testing Your Code](https://docs.python-guide.org/writing/tests/)
- [The Best of the Best Practices (BOBP) Guide for Python](https://gist.github.com/sloria/7001839)

