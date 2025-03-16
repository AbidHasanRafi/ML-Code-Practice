# Lesson: Advanced Functions

## Topics Covered:
- Defining Functions

---

## 1. Defining Functions

### Question 1: Fibonacci Sequence with Memoization

Define a recursive function to calculate the nth Fibonacci number using memoization. Test the function with different inputs.

```python
def fibonacci(n, memo={}):
    if n in memo:
        return memo[n]
    if n <= 1:
        return n
    memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)
    return memo[n]

# Test
print(fibonacci(10))  # 55
print(fibonacci(15))  # 610
```

### Question 2: Function with Nested Default Arguments

Define a function that takes two arguments, `a` and `b`, where `b` is a dictionary with a default value of an empty dictionary. The function should add a new key-value pair to the dictionary and return it. Test the function with different inputs.

```python
def add_to_dict(a, b=None):
    if b is None:
        b = {}
    b[a] = a**2
    return b

# Test
print(add_to_dict(2))  # {2: 4}
print(add_to_dict(3, {1: 1}))  # {1: 1, 3: 9}
```

### Question 3: Function with Variable Keyword Arguments

Define a function that takes a variable number of keyword arguments and returns a dictionary containing only those key-value pairs where the value is an integer. Test the function with different inputs.

```python
def filter_integers(**kwargs):
    return {k: v for k, v in kwargs.items() if isinstance(v, int)}

# Test
print(filter_integers(a=1, b='two', c=3, d=4.5))  # {'a': 1, 'c': 3}
print(filter_integers(x=10, y='yes', z=20))  # {'x': 10, 'z': 20}
```

### Question 4: Function with Callback

Define a function that takes another function as a callback and a list of integers. The function should apply the callback to each integer in the list and return a new list with the results. Test with different callback functions.

```python
def apply_callback(callback, lst):
    return [callback(x) for x in lst]

# Test
print(apply_callback(lambda x: x**2, [1, 2, 3, 4]))  # [1, 4, 9, 16]
print(apply_callback(lambda x: x+1, [1, 2, 3, 4]))  # [2, 3, 4, 5]
```

### Question 5: Function that Returns a Function

Define a function that returns another function. The returned function should take an integer and return its square. Test the returned function with different inputs.

```python
def outer_function():
    def inner_function(x):
        return x ** 2
    return inner_function

# Test
square = outer_function()
print(square(2))  # 4
print(square(5))  # 25
```

### Question 6: Function with Decorators

Define a function that calculates the time taken to execute another function. Apply this decorator to a function that performs a complex calculation. Test the decorated function with different inputs.

```python
import time

def timer_decorator(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"Function {func.__name__} took {end_time - start_time} seconds to execute.")
        return result
    return wrapper

@timer_decorator
def complex_calculation(n):
    return sum(x**2 for x in range(n))

# Test
print(complex_calculation(10000))
```

### Question 7: Higher-Order Function for Filtering and Mapping

Define a higher-order function that takes two functions, a filter function and a map function, along with a list of integers. The higher-order function should first filter the integers using the filter function and then apply the map function to the filtered integers. Test with different filter and map functions.

```python
def filter_and_map(filter_func, map_func, lst):
    return [map_func(x) for x in lst if filter_func(x)]

# Test
print(filter_and_map(lambda x: x % 2 == 0, lambda x: x ** 2, [1, 2, 3, 4, 5]))  # [4, 16]
print(filter_and_map(lambda x: x > 2, lambda x: x + 1, [1, 2, 3, 4, 5]))  # [4, 5, 6]
```

### Question 8: Function Composition

Define a function that composes two functions, `f` and `g`, such that the result is `f(g(x))`. Test with different functions `f` and `g`.

```python
def compose(f, g):
    return lambda x: f(g(x))

# Test
f = lambda x: x + 1
g = lambda x: x * 2
h = compose(f, g)
print(h(3))  # 7
print(h(5))  # 11
```

### Question 9: Partial Function Application

Use the `functools.partial` function to create a new function that multiplies its input by 2. Test the new function with different inputs.

```python
from functools import partial

multiply_by_2 = partial(lambda x, y: x * y, 2)

# Test
print(multiply_by_2(3))  # 6
print(multiply_by_2(5))  # 10
```

### Question 10: Function with Error Handling

Define a function that takes a list of integers and returns their average. The function should handle any errors that occur (e.g., empty list) and return `None` in such cases. Test with different inputs.

```python
def average(lst):
    try:
        return sum(lst) / len(lst)
    except ZeroDivisionError:
        return None

# Test
print(average([1, 2, 3, 4, 5]))  # 3.0
print(average([]))  # None
```

### Question 11: Function with Generators

Define a function that generates an infinite sequence of Fibonacci numbers. Test by printing the first 10 numbers in the sequence.

```python
def fibonacci_generator():
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b

# Test
fib_gen = fibonacci_generator()
for _ in range(10):
    print(next(fib_gen))
```

### Question 12: Currying

Define a curried function that takes three arguments, one at a time, and returns their product. Test the function by providing arguments one at a time.

```python
def curry_product(x):
    def inner1(y):
        def inner2(z):
            return x * y * z
        return inner2
    return inner1

# Test
print(curry_product(2)(3)(4))  # 24
print(curry_product(1)(5)(6))  # 30
```

### Question 13: Function with Context Manager

Define a function that uses a context manager to write a list of integers to a file. The function should handle any errors that occur during file operations. Test with different lists.

```python
def write_to_file(lst, filename):
    try:
        with open(filename, 'w') as f:
            for num in lst:
                f.write(f"{num}\n")
    except IOError as e:
        print(f"An error occurred: {e}")

# Test
write_to_file([1, 2, 3, 4, 5], 'output.txt')
```

### Question 14: Function with Multiple Return Types

Define a function that takes a list of mixed data types (integers, strings, and floats) and returns three lists: one containing all the integers, one containing all the strings, and one containing all the floats. Test with different inputs.

```python
def separate_types(lst):
    ints, strs, floats = [], [], []
    for item in lst:
        if isinstance(item, int):
            ints.append(item)
        elif isinstance(item, str):
            strs.append(item)
        elif isinstance(item, float):
            floats.append(item)
    return ints, strs, floats

# Test
print(separate_types([1, 'a', 2.5, 3, 'b', 4.0, 'c']))  # ([1, 3], ['a', 'b', 'c'], [2.5, 4.0])
```

### Question 15: Function with State

Define a function that maintains state between calls using a mutable default argument. The function should keep track of how many times it has been called. Test by calling the function multiple times.

```python
def call_counter(counter={'count': 0}):
    counter['count'] += 1
    return counter['count']

# Test
print(call_counter())  # 1
print(call_counter())  # 2
print(call_counter())  # 3
```