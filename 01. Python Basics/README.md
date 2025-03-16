# Lesson: Python Basics

## Topics Covered:
- Syntax and Semantics
- Variables and Data Types
- Basic Operators (Arithmetic, Comparison, Logical)

---

## 1. Syntax and Semantics

### Question 1: Write a Python program to print "Hello, World!".
```python
print("Hello, World!")
```

### Question 2: Write a Python program that takes a user input and prints it.
```python
user_input = input("Please enter something: ")
print(f"You entered: {user_input}")
```

### Question 3: Write a Python program to check if a number is positive, negative, or zero.
```python
number = float(input("Enter a number: "))
if number > 0:
    print("The number is positive.")
elif number < 0:
    print("The number is negative.")
else:
    print("The number is zero.")
```

### Question 4: Write a Python program to find the largest of three numbers.
```python
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))
num3 = float(input("Enter third number: "))

if (num1 >= num2) and (num1 >= num3):
    largest = num1
elif (num2 >= num1) and (num2 >= num3):
    largest = num2
else:
    largest = num3

print(f"The largest number is {largest}")
```

### Question 5: Write a Python program to calculate the factorial of a number.
```python
def factorial(n):
    if n == 0:
        return 1
    else:
        return n * factorial(n-1)

num = int(input("Enter a number: "))
print(f"The factorial of {num} is {factorial(num)}")
```

---

## 2. Variables and Data Types

### Question 6: Create variables of different data types and print their values and types.
```python
integer_var = 10
float_var = 10.5
string_var = "Hello"
boolean_var = True

print(f"Integer value: {integer_var}, type: {type(integer_var)}")
print(f"Float value: {float_var}, type: {type(float_var)}")
print(f"String value: {string_var}, type: {type(string_var)}")
print(f"Boolean value: {boolean_var}, type: {type(boolean_var)}")
```

### Question 7: Write a Python program to swap the values of two variables.
```python
a, b = 5, 10
print(f"Before swap: a = {a}, b = {b}")
a, b = b, a
print(f"After swap: a = {a}, b = {b}")
```

### Question 8: Write a Python program to convert Celsius to Fahrenheit.
```python
celsius = float(input("Enter temperature in Celsius: "))
fahrenheit = (celsius * 9/5) + 32
print(f"{celsius}°C is equal to {fahrenheit}°F")
```

### Question 9: Write a Python program to concatenate two strings.
```python
string1 = "Hello"
string2 = "World"
concatenated_string = string1 + " " + string2
print(concatenated_string)
```

### Question 10: Write a Python program to check if a variable is of a specific data type.
```python
var = 10.5
if isinstance(var, float):
    print(f"{var} is a float")
else:
    print(f"{var} is not a float")
```

---

## 3. Basic Operators (Arithmetic, Comparison, Logical)

### Question 11: Write a Python program to perform arithmetic operations.
```python
a, b = 5, 3
print(f"Addition: {a} + {b} = {a + b}")
print(f"Subtraction: {a} - {b} = {a - b}")
print(f"Multiplication: {a} * {b} = {a * b}")
print(f"Division: {a} / {b} = {a / b}")
```

### Question 12: Write a Python program to demonstrate comparison operators.
```python
a, b = 5, 3
print(f"{a} == {b}: {a == b}")
print(f"{a} != {b}: {a != b}")
print(f"{a} > {b}: {a > b}")
print(f"{a} < {b}: {a < b}")
```

### Question 13: Write a Python program to demonstrate logical operators.
```python
a, b = True, False
print(f"True and False: {a and b}")
print(f"True or False: {a or b}")
print(f"not True: {not a}")
```

### Question 14: Write a Python program to calculate the square of a number.
```python
num = float(input("Enter a number: "))
square = num ** 2
print(f"The square of {num} is {square}")
```

### Question 15: Write a Python program to check if a number is even or odd.
```python
num = int(input("Enter a number: "))
if num % 2 == 0:
    print(f"{num} is even.")
else:
    print(f"{num} is odd.")
```

### Question 16: Write a Python program to find the sum of the first n natural numbers.
```python
n = int(input("Enter a number: "))
sum_n = (n * (n + 1)) // 2
print(f"The sum of the first {n} natural numbers is {sum_n}")
```

### Question 17: Write a Python program to check if a year is a leap year.
```python
year = int(input("Enter a year: "))
if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):
    print(f"{year} is a leap year.")
else:
    print(f"{year} is not a leap year.")
```

### Question 18: Write a Python program to reverse a string.
```python
string = input("Enter a string: ")
print(f"The reversed string is: {string[::-1]}")
```

### Question 19: Write a Python program to check if a string is a palindrome.
```python
string = input("Enter a string: ")
if string == string[::-1]:
    print(f"{string} is a palindrome.")
else:
    print(f"{string} is not a palindrome.")
```

### Question 20: Write a Python program to sort a list of numbers in ascending order.
```python
numbers = [int(x) for x in input("Enter numbers separated by space: ").split()]
numbers.sort()
print(f"Sorted list: {numbers}")
```