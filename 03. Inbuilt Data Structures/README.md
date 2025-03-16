# Lesson: Inbuilt Data Structures

## Topics Covered:
- Lists
- Dictionaries

---

## 1. Lists

### Question 1: Creating and Accessing Lists
Create a list of the first 20 positive integers. Print the list.
```python
lst = list(range(1, 21))
print(lst)
```

### Question 2: Accessing List Elements
Print the first, middle, and last elements of the list created in Question 1.
```python
print(f"First element: {lst[0]}")
print(f"Middle element: {lst[len(lst) // 2]}")
print(f"Last element: {lst[-1]}")
```

### Question 3: List Slicing
Print the first five elements, the last five elements, and the elements from index 5 to 15 of the list created in Question 1.
```python
print(f"First five elements: {lst[:5]}")
print(f"Last five elements: {lst[-5:]}")
print(f"Elements from index 5 to 15: {lst[5:16]}")
```

### Question 4: List Comprehensions
Create a new list containing the squares of the first 10 positive integers using a list comprehension. Print the new list.
```python
squares = [x**2 for x in range(1, 11)]
print(squares)
```

### Question 5: Filtering Lists
Create a new list containing only the even numbers from the list created in Question 1 using a list comprehension. Print the new list.
```python
evens = [x for x in lst if x % 2 == 0]
print(evens)
```

### Question 6: List Methods
Create a list of random numbers and sort it in ascending and descending order. Remove the duplicates from the list and print the modified list.
```python
import random

random_numbers = [random.randint(1, 20) for _ in range(15)]
print(f"Original list: {random_numbers}")

sorted_numbers = sorted(random_numbers)
print(f"Sorted in ascending order: {sorted_numbers}")

sorted_numbers_desc = sorted(random_numbers, reverse=True)
print(f"Sorted in descending order: {sorted_numbers_desc}")

unique_numbers = list(set(random_numbers))
print(f"List with duplicates removed: {unique_numbers}")
```

### Question 7: Nested Lists
Create a nested list representing a 3x3 matrix and print the matrix. Access and print the element at the second row and third column.
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
print("Matrix:")
for row in matrix:
    print(row)
print(f"Element at second row and third column: {matrix[1][2]}")
```

### Question 8: List of Dictionaries
Create a list of dictionaries where each dictionary represents a student with keys 'name' and 'score'. Sort the list of dictionaries by the 'score' in descending order and print the sorted list.
```python
students = [
    {'name': 'Alice', 'score': 88},
    {'name': 'Bob', 'score': 72},
    {'name': 'Charlie', 'score': 95},
    {'name': 'David', 'score': 65},
    {'name': 'Eve', 'score': 78}
]
sorted_students = sorted(students, key=lambda x: x['score'], reverse=True)
print("Sorted students by score in descending order:")
for student in sorted_students:
    print(student)
```

### Question 9: Matrix Transposition
Write a function that takes a 3x3 matrix (nested list) as input and returns its transpose. Print the original and transposed matrices.
```python
def transpose_matrix(matrix):
    transposed = [[matrix[j][i] for j in range(len(matrix))] for i in range(len(matrix[0]))]
    return transposed

matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
transposed = transpose_matrix(matrix)
print("Original matrix:")
for row in matrix:
    print(row)
print("Transposed matrix:")
for row in transposed:
    print(row)
```

### Question 10: Flattening a Nested List
Write a function that takes a nested list and flattens it into a single list. Print the original and flattened lists.
```python
def flatten_list(nested_list):
    flat_list = [item for sublist in nested_list for item in sublist]
    return flat_list

nested_list = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]
flattened = flatten_list(nested_list)
print("Original nested list:")
print(nested_list)
print("Flattened list:")
print(flattened)
```

### Question 11: List Manipulation
Create a list of the first 10 positive integers. Remove the elements at indices 2, 4, and 6, and insert the element '99' at index 5. Print the modified list.
```python
lst = list(range(1, 11))
print(f"Original list: {lst}")
del lst[6]
del lst[4]
del lst[2]
lst.insert(5, 99)
print(f"Modified list: {lst}")
```

### Question 12: List Zipping
Create two lists of the same length. Use the `zip` function to combine these lists into a list of tuples and print the result.
```python
list1 = [1, 2, 3, 4, 5]
list2 = ['a', 'b', 'c', 'd', 'e']
zipped = list(zip(list1, list2))
print(zipped)
```

### Question 13: List Reversal
Write a function that takes a list and returns a new list with the elements in reverse order. Print the original and reversed lists.
```python
def reverse_list(lst):
    return lst[::-1]

original_list = [1, 2, 3, 4, 5]
reversed_list = reverse_list(original_list)
print(f"Original list: {original_list}")
print(f"Reversed list: {reversed_list}")
```

### Question 14: List Rotation
Write a function that rotates a list by n positions. Print the original and rotated lists.
```python
def rotate_list(lst, n):
    return lst[n:] + lst[:n]

original_list = [1, 2, 3, 4, 5]
rotated_list = rotate_list(original_list, 2)
print(f"Original list: {original_list}")
print(f"Rotated list: {rotated_list}")
```

### Question 15: List Intersection
Write a function that takes two lists and returns a new list containing only the elements that are present in both lists. Print the intersected list.
```python
def list_intersection(lst1, lst2):
    return [x for x in lst1 if x in lst2]

list1 = [1, 2, 3, 4, 5]
list2 = [3, 4, 5, 6, 7]
intersection = list_intersection(list1, list2)
print(f"Intersection: {intersection}")
```

---

## 2. Dictionaries

### Question 16: Creating and Accessing Dictionaries
Create a dictionary with the first 10 positive integers as keys and their squares as values. Print the dictionary.

```python
d = {i: i**2 for i in range(1, 11)}
print(d)
```

### Question 17: Accessing Dictionary Elements
Print the value of the key `5` and the keys of the dictionary created in Question 1.

```python
print(f"Value of key 5: {d[5]}")
print(f"Keys: {list(d.keys())}")
```

### Question 18: Dictionary Methods
Add a new key-value pair `(11, 121)` to the dictionary and then remove the key-value pair with key `1`. Print the modified dictionary.

```python
d[11] = 121
d.pop(1)
print(d)
```

### Question 19: Iterating Over Dictionaries
Iterate over the dictionary and print each key-value pair.

```python
for key, value in d.items():
    print(f"{key}: {value}")
```

### Question 20: Dictionary Comprehensions
Create a new dictionary containing the cubes of the first 10 positive integers using a dictionary comprehension. Print the new dictionary.

```python
cubes = {i: i**3 for i in range(1, 11)}
print(cubes)
```

### Question 21: Merging Dictionaries
Create two dictionaries and merge them into a single dictionary.

```python
d1 = {i: i**2 for i in range(1, 6)}
d2 = {i: i**2 for i in range(6, 11)}
d1.update(d2)
print(d1)
```

### Question 22: Nested Dictionaries
Create a nested dictionary representing a student.

```python
student = {
    'name': 'John Doe',
    'age': 16,
    'grades': {
        'math': 90,
        'science': 85,
        'english': 88
    }
}
print(student)
```

### Question 23: Dictionary of Lists
Create a dictionary where the keys are the first 5 positive integers and the values are lists containing the first 5 multiples of the key.

```python
multiples = {i: [i * j for j in range(1, 6)] for i in range(1, 6)}
print(multiples)
```

### Question 24: Dictionary of Tuples
Create a dictionary where the keys are the first 5 positive integers and the values are tuples containing the key and its square.

```python
tuple_dict = {i: (i, i**2) for i in range(1, 6)}
print(tuple_dict)
```

### Question 25: Dictionary and List Conversion
Convert a dictionary to a list of tuples and print it.

```python
d = {i: i**2 for i in range(1, 6)}
list_of_tuples = list(d.items())
print(list_of_tuples)
```

### Question 26: Dictionary Filtering
Create a new dictionary containing only the key-value pairs where the key is even.

```python
d = {i: i**2 for i in range(1, 11)}
even_dict = {k: v for k, v in d.items() if k % 2 == 0}
print(even_dict)
```

### Question 27: Dictionary Key and Value Transformation
Swap keys and values in a dictionary.

```python
d = {i: i**2 for i in range(1, 6)}
swapped_dict = {v: k for k, v in d.items()}
print(swapped_dict)
```

### Question 28: Default Dictionary
Create a default dictionary where each key has a default value of an empty list.

```python
from collections import defaultdict

default_dict = defaultdict(list)
default_dict['a'].append(1)
default_dict['a'].append(2)
default_dict['b'].append(3)
print(default_dict)
```

### Question 29: Counting with Dictionaries
Write a function that takes a string and returns a dictionary with the count of each character in the string.

```python
def count_chars(s):
    count_dict = {}
    for char in s:
        count_dict[char] = count_dict.get(char, 0) + 1
    return count_dict

string = "hello world"
print(count_chars(string))
```

### Question 30: Dictionary and JSON
Convert a dictionary to a JSON string.

```python
import json

book = {
    'title': 'To Kill a Mockingbird',
    'author': 'Harper Lee',
    'year': 1960,
    'genre': 'Fiction'
}
book_json = json.dumps(book)
print(book_json)
```