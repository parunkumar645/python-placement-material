# Python Lists

## Definition
A list in Python is an ordered, mutable collection of items. Lists can contain elements of different data types (integers, strings, other lists, etc.) and are defined by enclosing comma-separated values within square brackets `[]`. Lists are indexed starting from 0 for the first element.

## Why Use Lists?
1. **Collection Storage**: Lists allow you to store multiple items in a single variable, making data organization more efficient.
2. **Mutability**: Unlike strings or tuples, lists can be modified after creation (items can be added, removed, or changed).
3. **Ordered Sequence**: Lists maintain the order of elements, allowing for predictable iteration and indexing.
4. **Versatility**: Lists can store elements of different data types, including other lists (nested lists).
5. **Rich Functionality**: Python provides numerous built-in methods and operations for list manipulation.

## Examples

### Example 1: Creating and Accessing Lists
```python
# Creating lists
fruits = ["apple", "banana", "cherry"]
mixed_list = [1, "hello", 3.14, True]
nested_list = [1, 2, [3, 4, 5], 6]

# Accessing elements (indexing)
first_fruit = fruits[0]  # "apple"
print(first_fruit)

# Negative indexing (counting from the end)
last_fruit = fruits[-1]  # "cherry"
print(last_fruit)

# Accessing nested list elements
inner_element = nested_list[2][1]  # 4
print(inner_element)

# Checking if an item exists in a list
print("banana" in fruits)  # True
print("orange" in fruits)  # False

# Finding list length
print(len(fruits))  # 3
```

### Example 2: List Slicing and Operations
```python
numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# List slicing [start:end:step]
subset = numbers[2:7]  # [2, 3, 4, 5, 6]
print(subset)

# Slice with step
every_second = numbers[1:9:2]  # [1, 3, 5, 7]
print(every_second)

# Omitting start or end
first_five = numbers[:5]  # [0, 1, 2, 3, 4]
from_index_six = numbers[6:]  # [6, 7, 8, 9]
print(first_five)
print(from_index_six)

# Reversing a list
reversed_numbers = numbers[::-1]  # [9, 8, 7, 6, 5, 4, 3, 2, 1, 0]
print(reversed_numbers)

# List concatenation
combined = fruits + numbers
print(combined)  # ["apple", "banana", "cherry", 0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

# List repetition
repeated = fruits * 2
print(repeated)  # ["apple", "banana", "cherry", "apple", "banana", "cherry"]
```

### Example 3: Modifying Lists
```python
colors = ["red", "green", "blue"]

# Changing an element
colors[1] = "yellow"
print(colors)  # ["red", "yellow", "blue"]

# Adding elements
colors.append("purple")  # Add to the end
print(colors)  # ["red", "yellow", "blue", "purple"]

colors.insert(2, "orange")  # Insert at specific position
print(colors)  # ["red", "yellow", "orange", "blue", "purple"]

# Extending a list
more_colors = ["pink", "black"]
colors.extend(more_colors)  # Add all items from another list
print(colors)  # ["red", "yellow", "orange", "blue", "purple", "pink", "black"]

# Removing elements
colors.remove("orange")  # Remove by value
print(colors)  # ["red", "yellow", "blue", "purple", "pink", "black"]

popped_color = colors.pop()  # Remove and return the last item
print(popped_color)  # "black"
print(colors)  # ["red", "yellow", "blue", "purple", "pink"]

popped_index = colors.pop(1)  # Remove and return item at index
print(popped_index)  # "yellow"
print(colors)  # ["red", "blue", "purple", "pink"]

# Clearing a list
colors.clear()
print(colors)  # []
```

### Example 4: List Methods and Operations
```python
scores = [88, 92, 78, 90, 65, 92]

# Finding min and max values
print(min(scores))  # 65
print(max(scores))  # 92

# Finding the sum
print(sum(scores))  # 505

# Counting occurrences
print(scores.count(92))  # 2

# Finding the index of an item
print(scores.index(78))  # 2

# Sorting lists
scores.sort()  # In-place sorting
print(scores)  # [65, 78, 88, 90, 92, 92]

scores.sort(reverse=True)  # Descending order
print(scores)  # [92, 92, 90, 88, 78, 65]

# Creating a new sorted list (original remains unchanged)
names = ["Zack", "Alice", "Bob", "Charlie"]
sorted_names = sorted(names)
print(sorted_names)  # ["Alice", "Bob", "Charlie", "Zack"]
print(names)  # ["Zack", "Alice", "Bob", "Charlie"] - original unchanged

# Reversing a list in-place
names.reverse()
print(names)  # ["Charlie", "Bob", "Alice", "Zack"]
```

### Example 5: List Comprehensions
```python
# Basic list comprehension
squares = [x**2 for x in range(1, 11)]
print(squares)  # [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]

# List comprehension with condition
even_squares = [x**2 for x in range(1, 11) if x % 2 == 0]
print(even_squares)  # [4, 16, 36, 64, 100]

# List comprehension with multiple conditions
numbers = [x for x in range(50) if x % 2 == 0 if x % 5 == 0]
print(numbers)  # [0, 10, 20, 30, 40]

# Transforming items in a list
fruits = ["apple", "banana", "cherry", "kiwi"]
uppercase_fruits = [fruit.upper() for fruit in fruits]
print(uppercase_fruits)  # ["APPLE", "BANANA", "CHERRY", "KIWI"]

# Creating a matrix (nested list)
matrix = [[i + j for j in range(3)] for i in range(3)]
print(matrix)  # [[0, 1, 2], [1, 2, 3], [2, 3, 4]]
```

## Practice Questions

1. **Basic:** Write a program that creates a list of your favorite foods and prints them one by one using a loop.

2. **Intermediate:** Create a function called `find_common_elements` that takes two lists as input and returns a new list containing only the elements that appear in both lists.

3. **Challenge:** Write a function called `flatten_list` that takes a nested list (a list containing other lists) and returns a flattened list with all elements in a single dimension.

4. **Applied:** Create a program that takes a list of numbers as input and returns two separate lists: one containing all the even numbers and another containing all the odd numbers from the original list.

5. **Advanced:** Write a function called `remove_duplicates` that takes a list as input and returns a new list with all duplicate elements removed while preserving the original order of elements. Implement this function in two ways: 
   - Using built-in Python functions/methods
   - Without using any built-in functions specifically designed for removing duplicates (like sets)