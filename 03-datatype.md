# Python Data Types

## Definition

Data types in Python classify the type of data a variable can hold. Python has several built-in data types that define the operations possible on the data and the way it's stored in memory.

## Syntax

Python determines data type automatically when you assign a value:

```python
# No explicit syntax for declaring type
variable_name = value  # Type is inferred from the value
```

To check the data type:

```python
type(variable_name)
```

## Types of Data Types

### 1. Numeric Data Types

#### Integer (int)
```python
age = 25
count = -10
binary = 0b1010  # Binary representation
octal = 0o12     # Octal representation
hex_num = 0xFF   # Hexadecimal representation
```

#### Float
```python
height = 5.9
pi = 3.14159
scientific = 1.5e3  # 1.5 * 10^3 = 1500.0
```

#### Complex
```python
complex_num = 3 + 4j
real_part = complex_num.real      # 3.0
imaginary_part = complex_num.imag # 4.0
```

### 2. Text Data Type

#### String (str)
```python
name = "Python"
message = 'Hello, World!'
multi_line = """This is a
multi-line string"""

# String operations
print(name[0])     # P (accessing character by index)
print(name[0:2])   # Py (slicing)
print(len(name))   # 6 (string length)
```

### 3. Boolean Data Type

#### Boolean (bool)
```python
is_active = True
has_permission = False

# Boolean operations
print(not is_active)    # False
print(is_active and has_permission)  # False
print(is_active or has_permission)   # True
```

### 4. Sequence Data Types

#### List (mutable ordered collection)
```python
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
mixed = ["hello", 42, True, 3.14]

# List operations
fruits.append("orange")     # Add item
fruits[0] = "grape"        # Modify item
first_fruit = fruits[0]    # Access item
```

#### Tuple (immutable ordered collection)
```python
coordinates = (10, 20)
colors = ("red", "blue", "green")
single_item = (42,)  # Note the comma for single item tuple

# Tuple operations
x, y = coordinates    # Unpacking
first_color = colors[0]  # Access item
# colors[0] = "yellow"  # This would raise an error (immutable)
```

#### Range
```python
numbers = range(5)        # 0, 1, 2, 3, 4
start_stop = range(1, 6)  # 1, 2, 3, 4, 5
with_step = range(0, 10, 2)  # 0, 2, 4, 6, 8

print(list(numbers))  # Convert to list to see values
```

### 5. Mapping Data Type

#### Dictionary (dict)
```python
person = {
    "name": "Alice",
    "age": 30,
    "city": "London"
}

# Dictionary operations
print(person["name"])        # Access value by key
person["email"] = "alice@example.com"  # Add new key-value pair
person["age"] = 31          # Modify existing value
keys = person.keys()        # Get all keys
values = person.values()    # Get all values
```

### 6. Set Data Types

#### Set (unordered collection of unique items)
```python
colors = {"red", "blue", "green"}
numbers = {1, 2, 3, 4, 5}

# Set operations
colors.add("yellow")       # Add item
colors.add("red")         # Adding duplicate (will be ignored)
colors.remove("blue")     # Remove item
is_red_present = "red" in colors  # Check membership
```

#### Frozen Set (immutable set)
```python
immutable_colors = frozenset(["red", "blue", "green"])
# immutable_colors.add("yellow")  # This would raise an error
```

## Examples

### Example 1: Numeric Data Types

```python
# Integer
age = 25
print(type(age))  # Output: <class 'int'>

# Float
height = 5.9
print(type(height))  # Output: <class 'float'>

# Complex
complex_num = 3 + 4j
print(type(complex_num))  # Output: <class 'complex'>
```

### Example 2: String Operations

```python
name = "Python"
message = 'Hello, World!'
multi_line = """This is a
multi-line string"""

print(type(name))  # Output: <class 'str'>
print(name[0])     # Output: P (accessing character by index)
print(name[0:2])   # Output: Py (slicing)
print(len(name))   # Output: 6 (string length)
```

### Example 3: Boolean Operations

```python
is_active = True
has_permission = False

print(type(is_active))  # Output: <class 'bool'>
print(not is_active)    # Output: False
print(is_active and has_permission)  # Output: False
print(is_active or has_permission)   # Output: True
```

### Example 4: Collection Data Types

```python
# List (mutable ordered collection)
fruits = ["apple", "banana", "cherry"]
print(type(fruits))  # Output: <class 'list'>
fruits.append("orange")
print(fruits)  # Output: ['apple', 'banana', 'cherry', 'orange']

# Tuple (immutable ordered collection)
coordinates = (10, 20)
print(type(coordinates))  # Output: <class 'tuple'>
# coordinates[0] = 15  # This would raise an error

# Range
numbers = range(5)
print(list(numbers))  # Output: [0, 1, 2, 3, 4]
```

### Example 5: Dictionary and Set

```python
# Dictionary (key-value pairs)
person = {
    "name": "Alice",
    "age": 30,
    "city": "London"
}
print(type(person))  # Output: <class 'dict'>
print(person["name"])  # Output: Alice

# Set (unordered collection of unique items)
colors = {"red", "blue", "green"}
print(type(colors))  # Output: <class 'set'>
colors.add("red")  # Adding duplicate (will be ignored)
print(colors)  # Output: {'red', 'blue', 'green'}
```

## Important Notes for Placement Preparation

1. **Mutability**: Lists, dictionaries, and sets are mutable; strings, tuples, and frozensets are immutable
2. **Type Checking**: Use `type()` or `isinstance()` to check data types
3. **Memory Efficiency**: Choose appropriate data types for memory optimization
4. **Common Operations**: Know the basic operations for each data type
5. **Type Conversion**: Understand how to convert between different data types