# Python Dictionary 

## 1. What is a Dictionary?

A **dictionary** in Python is an unordered collection of key-value pairs. It's a mutable data type that stores data in the form of `{key: value}` pairs, where each key is unique and maps to a specific value.

### Key Characteristics:
- **Unordered**: Items don't have a defined order (Python 3.7+ maintains insertion order)
- **Mutable**: Can be modified after creation
- **Indexed by keys**: Access values using keys instead of numeric indices
- **No duplicate keys**: Each key must be unique
- **Keys must be immutable**: strings, numbers, tuples (not lists)

### Syntax:
```python
# Empty dictionary
my_dict = {}
my_dict = dict()

# Dictionary with initial values
student = {
    "name": "John",
    "age": 20,
    "grade": "A"
}
```

## 2. Why Use Dictionaries?

### Advantages:
1. **Fast Lookup**: O(1) average time complexity for access, insertion, and deletion
2. **Readable Code**: Key-value pairs make code more intuitive
3. **Flexible Keys**: Can use strings, numbers, or tuples as keys
4. **No Size Limit**: Can grow dynamically
5. **Memory Efficient**: Optimized storage for key-value relationships

### Use Cases:
- Storing configuration settings
- Caching/memoization
- Database-like operations
- Counting occurrences
- Mapping relationships
- JSON-like data structures

## 3. Basic Operations

### Creating Dictionaries
```python
# Different ways to create dictionaries
dict1 = {"a": 1, "b": 2, "c": 3}
dict2 = dict(a=1, b=2, c=3)
dict3 = dict([("a", 1), ("b", 2), ("c", 3)])
dict4 = {x: x**2 for x in range(5)}  # Dictionary comprehension
```

### Accessing Values
```python
student = {"name": "Alice", "age": 22, "city": "NYC"}

# Method 1: Using square brackets
print(student["name"])  # Alice

# Method 2: Using get() method (safer)
print(student.get("name"))  # Alice
print(student.get("phone", "Not found"))  # Not found (default value)
```

### Adding/Updating Items
```python
student = {"name": "Bob", "age": 21}

# Adding new key-value pair
student["city"] = "Boston"

# Updating existing value
student["age"] = 22

# Using update() method
student.update({"grade": "B+", "major": "CS"})
print(student)  # {'name': 'Bob', 'age': 22, 'city': 'Boston', 'grade': 'B+', 'major': 'CS'}
```

### Removing Items
```python
student = {"name": "Carol", "age": 23, "city": "LA", "grade": "A"}

# Method 1: del keyword
del student["city"]

# Method 2: pop() method (returns the removed value)
grade = student.pop("grade")  # Returns "A"

# Method 3: popitem() (removes last inserted item)
last_item = student.popitem()

# Method 4: clear() (removes all items)
student.clear()
```

## 4. Dictionary Methods

### Essential Methods:
```python
data = {"x": 10, "y": 20, "z": 30}

# Get all keys
print(data.keys())    # dict_keys(['x', 'y', 'z'])

# Get all values
print(data.values())  # dict_values([10, 20, 30])

# Get all key-value pairs
print(data.items())   # dict_items([('x', 10), ('y', 20), ('z', 30)])

# Copy dictionary
new_data = data.copy()

# Check if key exists
if "x" in data:
    print("Key 'x' exists")

# Get length
print(len(data))  # 3
```

## 5. Advanced Dictionary Operations

### Dictionary Comprehension
```python
# Basic comprehension
squares = {x: x**2 for x in range(1, 6)}
# {1: 1, 2: 4, 3: 9, 4: 16, 5: 25}

# Conditional comprehension
even_squares = {x: x**2 for x in range(1, 11) if x % 2 == 0}
# {2: 4, 4: 16, 6: 36, 8: 64, 10: 100}

# From two lists
keys = ['a', 'b', 'c']
values = [1, 2, 3]
combined = {k: v for k, v in zip(keys, values)}
# {'a': 1, 'b': 2, 'c': 3}
```

### Nested Dictionaries
```python
students = {
    "student1": {"name": "John", "grades": [85, 90, 78]},
    "student2": {"name": "Jane", "grades": [92, 88, 84]},
    "student3": {"name": "Bob", "grades": [76, 81, 89]}
}

# Accessing nested values
print(students["student1"]["name"])  # John
print(students["student2"]["grades"][0])  # 92

# Adding to nested dictionary
students["student1"]["age"] = 20
```

### Merging Dictionaries
```python
# Python 3.9+
dict1 = {"a": 1, "b": 2}
dict2 = {"c": 3, "d": 4}
merged = dict1 | dict2  # {'a': 1, 'b': 2, 'c': 3, 'd': 4}

# Python 3.5+
merged = {**dict1, **dict2}

# Traditional method
merged = dict1.copy()
merged.update(dict2)
```

### DefaultDict and Counter
```python
from collections import defaultdict, Counter

# DefaultDict - provides default values for missing keys
dd = defaultdict(int)
dd['a'] += 1  # No KeyError, starts from 0

# Counter - counts occurrences
text = "hello world"
char_count = Counter(text)
print(char_count)  # Counter({'l': 3, 'o': 2, 'h': 1, 'e': 1, ' ': 1, 'w': 1, 'r': 1, 'd': 1})
```

## 6. Common Patterns and Techniques

### Frequency Counting
```python
def count_frequency(items):
    freq = {}
    for item in items:
        freq[item] = freq.get(item, 0) + 1
    return freq

numbers = [1, 2, 2, 3, 3, 3, 4]
print(count_frequency(numbers))  # {1: 1, 2: 2, 3: 3, 4: 1}
```

### Group By Pattern
```python
def group_by_length(words):
    groups = {}
    for word in words:
        length = len(word)
        if length not in groups:
            groups[length] = []
        groups[length].append(word)
    return groups

words = ["cat", "dog", "elephant", "bird", "lion"]
print(group_by_length(words))
# {3: ['cat', 'dog'], 8: ['elephant'], 4: ['bird', 'lion']}
```

### Caching/Memoization
```python
cache = {}

def fibonacci(n):
    if n in cache:
        return cache[n]
    
    if n <= 1:
        result = n
    else:
        result = fibonacci(n-1) + fibonacci(n-2)
    
    cache[n] = result
    return result
```

## 7. Performance Considerations

### Time Complexity:
- **Access**: O(1) average, O(n) worst case
- **Insertion**: O(1) average, O(n) worst case
- **Deletion**: O(1) average, O(n) worst case
- **Search**: O(1) average for keys, O(n) for values

### Best Practices:
1. Use immutable objects as keys
2. Prefer `get()` over direct access when key might not exist
3. Use dictionary comprehensions for better readability
4. Consider `defaultdict` for grouping operations
5. Use `in` operator to check key existence

## 8. Practice Questions

### Question 1: Basic Dictionary Operations
**Problem**: Create a function that takes a list of students with their scores and returns a dictionary with student names as keys and their average scores as values.

```python
def calculate_averages(student_data):
    """
    Input: [("Alice", [85, 90, 78]), ("Bob", [92, 88, 84]), ("Carol", [76, 81, 89])]
    Output: {"Alice": 84.33, "Bob": 88.0, "Carol": 82.0}
    """
    # Your solution here
    pass
```

**Solution**:
```python
def calculate_averages(student_data):
    result = {}
    for name, scores in student_data:
        result[name] = round(sum(scores) / len(scores), 2)
    return result
```

### Question 2: Dictionary Manipulation
**Problem**: Given two dictionaries, merge them. If a key exists in both dictionaries, sum their values.

```python
def merge_sum_dicts(dict1, dict2):
    """
    Input: dict1 = {"a": 1, "b": 2, "c": 3}, dict2 = {"b": 3, "c": 4, "d": 5}
    Output: {"a": 1, "b": 5, "c": 7, "d": 5}
    """
    # Your solution here
    pass
```

**Solution**:
```python
def merge_sum_dicts(dict1, dict2):
    result = dict1.copy()
    for key, value in dict2.items():
        result[key] = result.get(key, 0) + value
    return result
```

### Question 3: Nested Dictionary Processing
**Problem**: Given a nested dictionary representing a company structure, find all employees in a specific department.

```python
def find_employees_in_department(company, target_dept):
    """
    Input: 
    company = {
        "Engineering": {"Alice": "Senior", "Bob": "Junior"},
        "Marketing": {"Carol": "Manager", "David": "Associate"},
        "Engineering": {"Eve": "Senior"}
    }
    target_dept = "Engineering"
    Output: ["Alice", "Bob", "Eve"]
    """
    # Your solution here
    pass
```

**Solution**:
```python
def find_employees_in_department(company, target_dept):
    if target_dept in company:
        return list(company[target_dept].keys())
    return []
```

### Question 4: Dictionary Comprehension Challenge
**Problem**: Create a dictionary that maps each word in a sentence to its length, but only include words longer than 3 characters.

```python
def word_length_dict(sentence):
    """
    Input: "The quick brown fox jumps over the lazy dog"
    Output: {"quick": 5, "brown": 5, "jumps": 5, "over": 4, "lazy": 4}
    """
    # Your solution here
    pass
```

**Solution**:
```python
def word_length_dict(sentence):
    words = sentence.split()
    return {word: len(word) for word in words if len(word) > 3}
```

### Question 5: Advanced Dictionary Problem
**Problem**: Implement a function that finds the most frequent element(s) in a list and returns both the element(s) and their frequency.

```python
def most_frequent_elements(lst):
    """
    Input: [1, 2, 2, 3, 3, 3, 4, 4, 4]
    Output: ([3, 4], 3)  # Elements [3, 4] appear 3 times each
    """
    # Your solution here
    pass
```

**Solution**:
```python
def most_frequent_elements(lst):
    if not lst:
        return ([], 0)
    
    freq_count = {}
    for item in lst:
        freq_count[item] = freq_count.get(item, 0) + 1
    
    max_freq = max(freq_count.values())
    most_frequent = [key for key, freq in freq_count.items() if freq == max_freq]
    
    return (most_frequent, max_freq)
```

## 9. Common Interview Questions

1. **Difference between list and dictionary?**
2. **How to handle missing keys in a dictionary?**
3. **What happens if you use a mutable object as a dictionary key?**
4. **How to sort a dictionary by keys/values?**
5. **What is the time complexity of dictionary operations?**

## 10. Quick Reference

```python
# Creation
d = {"key": "value"}
d = dict(key="value")

# Access
value = d["key"]
value = d.get("key", default)

# Modify
d["key"] = new_value
d.update({"key": "value"})

# Remove
del d["key"]
value = d.pop("key")
d.clear()

# Iteration
for key in d:
for key, value in d.items():
for value in d.values():

# Comprehension
{k: v for k, v in iterable}
```

---

**Remember**: Practice these concepts with real coding problems. Dictionaries are fundamental in Python and appear in almost every technical interview!