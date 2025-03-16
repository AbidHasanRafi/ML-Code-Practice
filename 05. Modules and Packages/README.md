# Lesson: Modules and Packages

## Topics Covered:
- Importing Modules
- Standard Library Overview
- Creating and Using Packages

---

## 1. Importing Modules

### Question 1: Importing and Using Modules

Import the `math` module and use it to calculate the square root of 25 and the sine of 90 degrees.

```python
import math

print(math.sqrt(25))  # 5.0
print(math.sin(math.radians(90)))  # 1.0
```

### Question 2: Aliasing Modules

Import the `datetime` module with an alias and use it to print the current date and time.

```python
import datetime as dt

print(dt.datetime.now())
```

### Question 3: Importing Specific Functions

Import the `randint` function from the `random` module and use it to generate a random integer between 1 and 100.

```python
from random import randint

print(randint(1, 100))
```

### Question 4: Importing Multiple Functions

Import the `sqrt` and `pow` functions from the `math` module and use them to calculate the square root of 16 and 2 raised to the power of 3.

```python
from math import sqrt, pow

print(sqrt(16))  # 4.0
print(pow(2, 3))  # 8.0
```

### Question 5: Handling Import Errors

Write code that attempts to import a non-existent module and gracefully handles the import error by printing an error message.

```python
try:
    import non_existent_module
except ImportError as e:
    print(f"Error importing module: {e}")
```

---

## 2. Standard Library Overview

### Question 6: Working with the `os` Module

Use the `os` module to create a new directory, list the contents of the current directory, and remove the newly created directory.

```python
import os

# Create a new directory
os.mkdir('new_directory')

# List contents of the current directory
print(os.listdir('.'))

# Remove the newly created directory
os.rmdir('new_directory')
print(os.listdir('.'))
```

### Question 7: Working with the `sys` Module

Use the `sys` module to print the Python version currently in use and the command-line arguments passed to the script.

```python
import sys

print(f"Python version: {sys.version}")
print(f"Command-line arguments: {sys.argv}")
```

### Question 8: Working with the `math` Module

Use the `math` module to calculate the greatest common divisor (GCD) of two numbers and the factorial of a number.

```python
import math

print(math.gcd(48, 18))  # 6
print(math.factorial(5))  # 120
```

### Question 9: Working with the `datetime` Module

Use the `datetime` module to print the current date, calculate the date 100 days from today, and determine the day of the week for a given date.

```python
import datetime

# Current date
today = datetime.date.today()
print(f"Today's date: {today}")

# Date 100 days from today
future_date = today + datetime.timedelta(days=100)
print(f"Date 100 days from today: {future_date}")

# Day of the week for a given date
given_date = datetime.date(2022, 1, 1)
print(f"Day of the week for 2022-01-01: {given_date.strftime('%A')}")
```

### Question 10: Working with the `random` Module

Use the `random` module to generate a list of 5 random numbers between 1 and 50 and shuffle the elements of a list.

```python
import random

# List of 5 random numbers between 1 and 50
random_numbers = [random.randint(1, 50) for _ in range(5)]
print(random_numbers)

# Shuffle a list
lst = [1, 2, 3, 4, 5]
random.shuffle(lst)
print(lst)
```

---

## 3. Creating and Using Packages

### Question 11: Creating a Simple Package

Create a package named `mypackage` with two modules: `module1` and `module2`. `module1` should contain a function that adds two numbers, and `module2` should contain a function that multiplies two numbers. Write code to use these functions.

```
# File structure:
# mypackage/
#   __init__.py
#   module1.py
#   module2.py

# Content of module1.py
# def add(a, b):
#     return a + b

# Content of module2.py
# def multiply(a, b):
#     return a * b
```

```python
# Using the package
from mypackage import module1, module2

print(module1.add(2, 3))  # 5
print(module2.multiply(2, 3))  # 6
```

### Question 12: Using `__init__.py`

Modify the `mypackage` package to include an `__init__.py` file that imports the functions from `module1` and `module2`. Write code to use these functions.

```
# Content of __init__.py
# from .module1 import add
# from .module2 import multiply
```

```python
# Using the package
from mypackage import add, multiply

print(add(2, 3))  # 5
print(multiply(2, 3))  # 6
```

### Question 13: Importing from a Package

Write code to import and use the functions from `mypackage` without explicitly importing `module1` and `module2`.

```python
from mypackage import add, multiply

print(add(2, 3))  # 5
print(multiply(2, 3))  # 6
```

### Question 14: Relative Imports

Create a subpackage named `subpackage` within `mypackage` and move `module2` into `subpackage`. Modify the import statements in `__init__.py` to use relative imports. Write code to use the functions from both modules.

```
# File structure:
# mypackage/
#   __init__.py
#   module1.py
#   subpackage/
#     __init__.py
#     module2.py

# Content of __init__.py in mypackage
# from .module1 import add
# from .subpackage.module2 import multiply
```

```python
# Using the package
from mypackage import add, multiply

print(add(2, 3))  # 5
print(multiply(2, 3))  # 6
```

### Question 15: Handling Package Import Errors

Write code that attempts to import a non-existent function from `mypackage` and gracefully handles the import error by printing an error message.

```python
try:
    from mypackage import non_existent_function
except ImportError as e:
    print(f"Error importing function: {e}")
```