# Lesson: Control Flow

## Topics Covered:
- Conditional Statements
- Loops

---

## 1. Conditional Statements

### Question 1: Simple if Statement

Write a program that asks the user to input a number and prints whether the number is positive.

```python
number = float(input("Enter a number: "))
if number > 0:
    print("The number is positive.")
```

### Question 2: if-else Statement

Write a program that asks the user to input a number and prints whether the number is positive or negative.

```python
number = float(input("Enter a number: "))
if number > 0:
    print("The number is positive.")
else:
    print("The number is negative.")
```

### Question 3: if-elif-else Statement

Write a program that asks the user to input a number and prints whether the number is positive, negative, or zero.

```python
number = float(input("Enter a number: "))
if number > 0:
    print("The number is positive.")
elif number < 0:
    print("The number is negative.")
else:
    print("The number is zero.")
```

### Question 4: Nested if Statement

Write a program that asks the user to input a number and prints whether the number is positive and even, positive and odd, or negative.

```python
number = float(input("Enter a number: "))
if number > 0:
    if number % 2 == 0:
        print("The number is positive and even.")
    else:
        print("The number is positive and odd.")
else:
    print("The number is negative.")
```
---

## 2. Loops

### Question 5: for Loop

Write a program that prints all the numbers from 1 to 10 using a for loop.

```python
for i in range(1, 11):
    print(i)
```

### Question 6: while Loop

Write a program that prints all the numbers from 1 to 10 using a while loop.

```python
i = 1
while i <= 10:
    print(i)
    i += 1
```

### Question 7: Nested Loops

Write a program that prints a 5x5 grid of asterisks (*) using nested loops.

```python
for i in range(5):
    for j in range(5):
        print("*", end=" ")
    print()
```

### Question 8: break Statement

Write a program that asks the user to input numbers until they input 0. The program should print the sum of all the input numbers.

```python
total = 0
while True:
    number = float(input("Enter a number (0 to stop): "))
    if number == 0:
        break
    total += number
print(f"The sum of all the numbers is {total}.")
```

### Question 9: continue Statement

Write a program that prints all the numbers from 1 to 10 except 5 using a for loop and continue statement.

```python
for i in range(1, 11):
    if i == 5:
        continue
    print(i)
```

### Question 10: pass Statement

Write a program that defines an empty function using the pass statement.

```python
def empty_function():
    pass

# Calling the empty function
empty_function()
```

### Question 11: Combining Loops and Conditionals

Write a program that asks the user to input a number and prints all the even numbers from 1 to that number using a for loop.

```python
number = int(input("Enter a number: "))
for i in range(1, number + 1):
    if i % 2 == 0:
        print(i)
```

### Question 12: Factorial Calculation

Write a program that calculates the factorial of a number input by the user using a while loop.

```python
number = int(input("Enter a number: "))
factorial = 1
i = 1
while i <= number:
    factorial *= i
    i += 1
print(f"The factorial of {number} is {factorial}.")
```

### Question 13: Sum of Digits

Write a program that calculates the sum of the digits of a number input by the user using a while loop.

```python
number = int(input("Enter a number: "))
sum_of_digits = 0
while number > 0:
    digit = number % 10
    sum_of_digits += digit
    number = number // 10
print(f"The sum of the digits is {sum_of_digits}.")
```

### Question 14: Prime Number Check

Write a program that checks if a number input by the user is a prime number using a for loop.

```python
number = int(input("Enter a number: "))
is_prime = True
if number <= 1:
    is_prime = False
else:
    for i in range(2, int(number ** 0.5) + 1):
        if number % i == 0:
            is_prime = False
            break
if is_prime:
    print(f"{number} is a prime number.")
else:
    print(f"{number} is not a prime number.")
```

### Question 15: Fibonacci Sequence

Write a program that prints the first n Fibonacci numbers, where n is input by the user.

```python
n = int(input("Enter the number of Fibonacci numbers to print: "))
a, b = 0, 1
count = 0
while count < n:
    print(a)
    a, b = b, a + b
    count += 1
```
