# Python Tuples

## Definition
A tuple in Python is an ordered, immutable collection of elements. Tuples are defined by enclosing comma-separated values within parentheses `()`. Once created, the elements and their order in a tuple cannot be changed. Tuples can contain elements of different data types, including other tuples, and are indexed starting from 0.

## Why Use Tuples?
1. **Immutability**: Tuples cannot be modified after creation, making them useful for data that shouldn't change throughout program execution.
2. **Performance**: Tuples are slightly faster than lists and use less memory because they're immutable.
3. **Dictionary Keys**: Unlike lists, tuples can be used as keys in dictionaries because of their immutability.
4. **Multiple Return Values**: Functions can easily return multiple values packaged as a tuple.
5. **Data Integrity**: Tuples provide a way to ensure that data remains unchanged, protecting against accidental modification.

## Examples

### Example 1: Creating and Accessing Tuples
```python
# Creating tuples
empty_tuple = ()
single_item = (42,)  # Note the comma after the value
coordinates = (10, 20)
mixed_tuple = (1, "hello", 3.14, True)
nested_tuple = (1, 2, (3, 4, 5), 6)

# Accessing elements
x_coordinate = coordinates[0]  # 10
print(x_coordinate)

# Negative indexing
last_item = mixed_tuple[-1]  # True
print(last_item)

# Accessing nested elements
inner_element = nested_tuple[2][1]  # 4
print(inner_element)

# Tuple length
print(len(coordinates))  # 2

# Checking if an item exists
print("hello" in mixed_tuple)  # True
print(5 in mixed_tuple)  # False
```

### Example 2: Tuple Operations and Methods
```python
tuple1 = (1, 2, 3)
tuple2 = ('a', 'b', 'c')

# Concatenation
combined = tuple1 + tuple2
print(combined)  # (1, 2, 3, 'a', 'b', 'c')

# Repetition
repeated = tuple1 * 3
print(repeated)  # (1, 2, 3, 1, 2, 3, 1, 2, 3)

# Slicing
numbers = (0, 1, 2, 3, 4, 5, 6, 7, 8, 9)
subset = numbers[2:7]  # (2, 3, 4, 5, 6)
print(subset)

# Step slicing
every_second = numbers[1:9:2]  # (1, 3, 5, 7)
print(every_second)

# Reverse
reversed_tuple = numbers[::-1]  # (9, 8, 7, 6, 5, 4, 3, 2, 1, 0)
print(reversed_tuple)

# Finding minimum and maximum values
print(min(numbers))  # 0
print(max(numbers))  # 9

# Counting occurrences
repeat_tuple = (1, 2, 2, 3, 3, 3, 4, 4, 4, 4)
print(repeat_tuple.count(3))  # 3

# Finding index of an element
print(repeat_tuple.index(4))  # 6 (first occurrence)
```

### Example 3: Tuple Packing and Unpacking
```python
# Tuple packing
person = ("John Doe", 30, "Software Engineer")

# Tuple unpacking
name, age, profession = person
print(name)        # John Doe
print(age)         # 30
print(profession)  # Software Engineer

# Extended unpacking (Python 3.x)
first, *middle, last = (1, 2, 3, 4, 5)
print(first)   # 1
print(middle)  # [2, 3, 4]
print(last)    # 5

# Swapping variables
a, b = 10, 20
print(f"Before swap: a = {a}, b = {b}")  # Before swap: a = 10, b = 20
a, b = b, a  # Swapping using tuple packing and unpacking
print(f"After swap: a = {a}, b = {b}")   # After swap: a = 20, b = 10

# Returning multiple values from a function
def get_dimensions():
    return (1920, 1080)  # Return width and height as a tuple

width, height = get_dimensions()
print(f"Width: {width}, Height: {height}")  # Width: 1920, Height: 1080
```

### Example 4: Converting Between Tuples and Lists
```python
# Converting tuple to list
tuple_data = (1, 2, 3, 4, 5)
list_data = list(tuple_data)
print(list_data)  # [1, 2, 3, 4, 5]

# Modifying the list
list_data.append(6)
list_data[0] = 0
print(list_data)  # [0, 2, 3, 4, 5, 6]

# Converting back to tuple
new_tuple = tuple(list_data)
print(new_tuple)  # (0, 2, 3, 4, 5, 6)

# Creating a tuple from a string
letters = tuple("Python")
print(letters)  # ('P', 'y', 't', 'h', 'o', 'n')

# Using zip to create tuples from multiple iterables
names = ["Alice", "Bob", "Charlie"]
ages = [25, 30, 35]
people = tuple(zip(names, ages))
print(people)  # (('Alice', 25), ('Bob', 30), ('Charlie', 35))
```

### Example 5: Named Tuples
```python
from collections import namedtuple

# Creating a named tuple type
Person = namedtuple('Person', ['name', 'age', 'city'])

# Creating instances
alice = Person('Alice', 30, 'New York')
bob = Person(name='Bob', age=25, city='Boston')

# Accessing elements by index
print(alice[0])  # Alice

# Accessing elements by field name
print(alice.name)  # Alice
print(bob.city)    # Boston

# Unpacking named tuple
name, age, city = alice
print(f"{name} is {age} years old and lives in {city}")
# Alice is 30 years old and lives in New York

# Converting to dictionary
alice_dict = alice._asdict()
print(alice_dict)  # {'name': 'Alice', 'age': 30, 'city': 'New York'}

# Creating a new instance with one field replaced
charlie = bob._replace(name='Charlie', city='Chicago')
print(charlie)  # Person(name='Charlie', age=25, city='Chicago')
```

## Practice Questions

1. **Basic:** Write a program that creates a tuple of your favorite colors and prints each color using a for loop.

2. **Intermediate:** Create a function that takes a list of tuples where each tuple contains a student's name and their score, and returns the name of the student with the highest score.

3. **Challenge:** Implement a function that takes a nested tuple (containing tuples within it) and returns the sum of all numeric values at any level of nesting.

4. **Applied:** Write a program that maintains a history of user inputs as a tuple. Each time the user enters a new value, create a new tuple by adding the new value to the existing history tuple. Allow the user to see the entire history or a specific past input by index.

5. **Advanced:** Create a function called `find_common_elements` that takes any number of tuples as arguments and returns a tuple containing elements that appear in all of the input tuples. Your function should work for tuples containing any hashable elements (strings, numbers, etc.).