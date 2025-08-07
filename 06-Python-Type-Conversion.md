# Python Type Conversion

## Definition
Type conversion (also called type casting) is the process of converting a value from one data type to another in Python. Python provides two types of type conversion:
1. **Implicit Type Conversion** (Automatic): Python automatically converts one data type to another without user intervention.
2. **Explicit Type Conversion** (Manual): The user manually converts one data type to another using built-in functions.

## Syntax

### Implicit Type Conversion
No specific syntax - Python handles it automatically when needed.

### Explicit Type Conversion
```python
# General format# Python Type Conversion

## Definition
Type conversion (also called type casting) is the process of converting a value from one data type to another in Python. Python provides two types of type conversion:
1. **Implicit Type Conversion** (Automatic): Python automatically converts one data type to another without user intervention.
2. **Explicit Type Conversion** (Manual): The user manually converts one data type to another using built-in functions.

## Syntax

### Implicit Type Conversion
No specific syntax - Python handles it automatically when needed.

### Explicit Type Conversion
```python
# General format
new_variable = target_datatype(expression)

# Examples
int_value = int(expression)     # Convert to integer
float_value = float(expression) # Convert to float
str_value = str(expression)     # Convert to string
```

## Common Type Conversion Functions

| Function  | Description                                                | Example              |
|-----------|------------------------------------------------------------|----------------------|
| `int()`   | Converts to integer                                        | `int("10")` → `10`   |
| `float()` | Converts to floating-point number                          | `float("10.5")` → `10.5` |
| `str()`   | Converts to string                                         | `str(10)` → `"10"`   |
| `bool()`  | Converts to boolean                                        | `bool(1)` → `True`   |
| `list()`  | Converts to list                                           | `list("abc")` → `['a', 'b', 'c']` |
| `tuple()` | Converts to tuple                                          | `tuple([1,2,3])` → `(1, 2, 3)` |
| `set()`   | Converts to set (removes duplicates)                       | `set([1,2,2,3])` → `{1, 2, 3}` |
| `dict()`  | Converts to dictionary                                     | `dict([('a',1),('b',2)])` → `{'a': 1, 'b': 2}` |
| `complex()` | Creates a complex number                                 | `complex(1, 2)` → `1+2j` |
| `ord()`   | Converts character to integer (Unicode code point)         | `ord('A')` → `65`    |
| `chr()`   | Converts integer (Unicode code point) to character         | `chr(65)` → `'A'`    |
| `hex()`   | Converts integer to hexadecimal string                     | `hex(255)` → `'0xff'` |
| `oct()`   | Converts integer to octal string                           | `oct(8)` → `'0o10'`  |
| `bin()`   | Converts integer to binary string                          | `bin(2)` → `'0b10'`  |

## Examples

### Example 1: Implicit Type Conversion (Type Coercion)
```python
# Integer and float
num_int = 10
num_float = 3.5
result = num_int + num_float  # Integer is implicitly converted to float
print(result)  # Output: 13.5
print(type(result))  # Output: <class 'float'>

# Boolean and integer
bool_value = True
result = bool_value + 10  # True is implicitly converted to 1
print(result)  # Output: 11
print(type(result))  # Output: <class 'int'>
```

### Example 2: Explicit Type Conversion - Numeric Types
```python
# String to integer
str_num = "42"
int_num = int(str_num)
print(int_num)  # Output: 42
print(type(int_num))  # Output: <class 'int'>

# String to float
str_float = "3.14"
float_num = float(str_float)
print(float_num)  # Output: 3.14
print(type(float_num))  # Output: <class 'float'>

# Float to integer (truncates decimal part)
pi = 3.14159
int_pi = int(pi)
print(int_pi)  # Output: 3

# Integer/float to string
num = 100
str_num = str(num)
print(str_num)  # Output: "100"
print(type(str_num))  # Output: <class 'str'>
```

### Example 3: Explicit Type Conversion - Collections
```python
# String to list (splits into characters)
text = "hello"
char_list = list(text)
print(char_list)  # Output: ['h', 'e', 'l', 'l', 'o']

# List to tuple
numbers = [1, 2, 3, 4, 5]
num_tuple = tuple(numbers)
print(num_tuple)  # Output: (1, 2, 3, 4, 5)

# List to set (removes duplicates)
numbers_with_duplicates = [1, 2, 2, 3, 4, 4, 5]
unique_numbers = set(numbers_with_duplicates)
print(unique_numbers)  # Output: {1, 2, 3, 4, 5}

# List of tuples to dictionary
key_value_pairs = [('a', 1), ('b', 2), ('c', 3)]
dictionary = dict(key_value_pairs)
print(dictionary)  # Output: {'a': 1, 'b': 2, 'c': 3}
```

### Example 4: Type Conversion in User Input
```python
# Getting numeric input from user
age_str = input("Enter your age: ")  # User enters: 25
age = int(age_str)
print(f"In 5 years, you will be {age + 5} years old.")
# Output: In 5 years, you will be 30 years old.

# Getting multiple numeric inputs
x, y = map(int, input("Enter two numbers separated by space: ").split())
# User enters: 10 20
print(f"Sum: {x + y}")  # Output: Sum: 30

# Converting user input to appropriate types
name = input("Enter your name: ")  # String input
height = float(input("Enter your height in meters: "))  # Float input
is_student = input("Are you a student? (yes/no): ").lower() == "yes"  # Boolean input
print(f"Name: {name}, Height: {height}m, Student: {is_student}")
```

### Example 5: Common Conversion Patterns and Errors
```python
# Rounding vs. truncating
x = 3.7
print(int(x))      # Output: 3 (truncates, doesn't round)
print(round(x))    # Output: 4 (rounds to nearest integer)

# Converting between number systems
decimal = 42
# Decimal to binary, octal, hexadecimal
print(bin(decimal))  # Output: '0b101010'
print(oct(decimal))  # Output: '0o52'
print(hex(decimal))  # Output: '0x2a'

# Converting back to decimal
binary_str = "101010"
octal_str = "52"
hex_str = "2a"
print(int(binary_str, 2))  # Output: 42
print(int(octal_str, 8))   # Output: 42
print(int(hex_str, 16))    # Output: 42

# Handling conversion errors
try:
    # This will raise an error - can't convert alphabetic string to int
    num = int("hello")
except ValueError as e:
    print(f"Error: {e}")  # Output: Error: invalid literal for int() with base 10: 'hello'

# Safely converting with default values
def safe_int_convert(value, default=0):
    try:
        return int(value)
    except (ValueError, TypeError):
        return default

print(safe_int_convert("42"))     # Output: 42
print(safe_int_convert("hello"))  # Output: 0
print(safe_int_convert(None))     # Output: 0
```

## Practice Questions

1. Write a program that takes a string input from the user containing a decimal number and converts it to:
   a) An integer (truncating any decimal part)
   b) A rounded integer
   c) A string without decimal places

2. Create a function that safely converts various inputs to integers. The function should handle:
   - Strings containing valid integers
   - Strings containing floats
   - None values
   - Boolean values
   - Lists/tuples containing a single numeric value
   - Invalid inputs (return a default value)

3. Write a program that prompts the user to enter a temperature in Fahrenheit and converts it to Celsius using the formula: C = (F - 32) * 5/9. Make sure to properly handle type conversion and format the output to 1 decimal place.

4. Given a hexadecimal color code (e.g., "#FF5733"), write a program to convert it to its RGB values (as integers). The output should be in the format: "RGB: (255, 87, 51)".

5. Create a program that asks the user to enter a list of numbers separated by commas. Convert the input to:
   a) A list of numbers
   b) A tuple of numbers
   c) A set that contains only unique numbers
   d) A dictionary where the keys are the positions (0, 1, 2...) and the values are the numbers
   
   For example, if the user enters "5,2,8,2,1", your program should display:
   - List: [5, 2, 8, 2, 1]
   - Tuple: (5, 2, 8, 2, 1)
   - Set: {1, 2, 5, 8}
   - Dictionary: {0: 5, 1: 2, 2: 8, 3: 2, 4: 1}
new_variable = target_datatype(expression)

# Examples
int_value = int(expression)     # Convert to integer
float_value = float(expression) # Convert to float
str_value = str(expression)     # Convert to string
```

## Common Type Conversion Functions

| Function  | Description                                                | Example              |
|-----------|------------------------------------------------------------|----------------------|
| `int()`   | Converts to integer                                        | `int("10")` → `10`   |
| `float()` | Converts to floating-point number                          | `float("10.5")` → `10.5` |
| `str()`   | Converts to string                                         | `str(10)` → `"10"`   |
| `bool()`  | Converts to boolean                                        | `bool(1)` → `True`   |
| `list()`  | Converts to list                                           | `list("abc")` → `['a', 'b', 'c']` |
| `tuple()` | Converts to tuple                                          | `tuple([1,2,3])` → `(1, 2, 3)` |
| `set()`   | Converts to set (removes duplicates)                       | `set([1,2,2,3])` → `{1, 2, 3}` |
| `dict()`  | Converts to dictionary                                     | `dict([('a',1),('b',2)])` → `{'a': 1, 'b': 2}` |
| `complex()` | Creates a complex number                                 | `complex(1, 2)` → `1+2j` |
| `ord()`   | Converts character to integer (Unicode code point)         | `ord('A')` → `65`    |
| `chr()`   | Converts integer (Unicode code point) to character         | `chr(65)` → `'A'`    |
| `hex()`   | Converts integer to hexadecimal string                     | `hex(255)` → `'0xff'` |
| `oct()`   | Converts integer to octal string                           | `oct(8)` → `'0o10'`  |
| `bin()`   | Converts integer to binary string                          | `bin(2)` → `'0b10'`  |

## Examples

### Example 1: Implicit Type Conversion (Type Coercion)
```python
# Integer and float
num_int = 10
num_float = 3.5
result = num_int + num_float  # Integer is implicitly converted to float
print(result)  # Output: 13.5
print(type(result))  # Output: <class 'float'>

# Boolean and integer
bool_value = True
result = bool_value + 10  # True is implicitly converted to 1
print(result)  # Output: 11
print(type(result))  # Output: <class 'int'>
```

### Example 2: Explicit Type Conversion - Numeric Types
```python
# String to integer
str_num = "42"
int_num = int(str_num)
print(int_num)  # Output: 42
print(type(int_num))  # Output: <class 'int'>

# String to float
str_float = "3.14"
float_num = float(str_float)
print(float_num)  # Output: 3.14
print(type(float_num))  # Output: <class 'float'>

# Float to integer (truncates decimal part)
pi = 3.14159
int_pi = int(pi)
print(int_pi)  # Output: 3

# Integer/float to string
num = 100
str_num = str(num)
print(str_num)  # Output: "100"
print(type(str_num))  # Output: <class 'str'>
```

### Example 3: Explicit Type Conversion - Collections
```python
# String to list (splits into characters)
text = "hello"
char_list = list(text)
print(char_list)  # Output: ['h', 'e', 'l', 'l', 'o']

# List to tuple
numbers = [1, 2, 3, 4, 5]
num_tuple = tuple(numbers)
print(num_tuple)  # Output: (1, 2, 3, 4, 5)

# List to set (removes duplicates)
numbers_with_duplicates = [1, 2, 2, 3, 4, 4, 5]
unique_numbers = set(numbers_with_duplicates)
print(unique_numbers)  # Output: {1, 2, 3, 4, 5}

# List of tuples to dictionary
key_value_pairs = [('a', 1), ('b', 2), ('c', 3)]
dictionary = dict(key_value_pairs)
print(dictionary)  # Output: {'a': 1, 'b': 2, 'c': 3}
```

### Example 4: Type Conversion in User Input
```python
# Getting numeric input from user
age_str = input("Enter your age: ")  # User enters: 25
age = int(age_str)
print(f"In 5 years, you will be {age + 5} years old.")
# Output: In 5 years, you will be 30 years old.

# Getting multiple numeric inputs
x, y = map(int, input("Enter two numbers separated by space: ").split())
# User enters: 10 20
print(f"Sum: {x + y}")  # Output: Sum: 30

# Converting user input to appropriate types
name = input("Enter your name: ")  # String input
height = float(input("Enter your height in meters: "))  # Float input
is_student = input("Are you a student? (yes/no): ").lower() == "yes"  # Boolean input
print(f"Name: {name}, Height: {height}m, Student: {is_student}")
```

### Example 5: Common Conversion Patterns and Errors
```python
# Rounding vs. truncating
x = 3.7
print(int(x))      # Output: 3 (truncates, doesn't round)
print(round(x))    # Output: 4 (rounds to nearest integer)

# Converting between number systems
decimal = 42
# Decimal to binary, octal, hexadecimal
print(bin(decimal))  # Output: '0b101010'
print(oct(decimal))  # Output: '0o52'
print(hex(decimal))  # Output: '0x2a'

# Converting back to decimal
binary_str = "101010"
octal_str = "52"
hex_str = "2a"
print(int(binary_str, 2))  # Output: 42
print(int(octal_str, 8))   # Output: 42
print(int(hex_str, 16))    # Output: 42

# Handling conversion errors
try:
    # This will raise an error - can't convert alphabetic string to int
    num = int("hello")
except ValueError as e:
    print(f"Error: {e}")  # Output: Error: invalid literal for int() with base 10: 'hello'

# Safely converting with default values
def safe_int_convert(value, default=0):
    try:
        return int(value)
    except (ValueError, TypeError):
        return default

print(safe_int_convert("42"))     # Output: 42
print(safe_int_convert("hello"))  # Output: 0
print(safe_int_convert(None))     # Output: 0
```

## Practice Questions

1. Write a program that takes a string input from the user containing a decimal number and converts it to:
   a) An integer (truncating any decimal part)
   b) A rounded integer
   c) A string without decimal places

2. Create a function that safely converts various inputs to integers. The function should handle:
   - Strings containing valid integers
   - Strings containing floats
   - None values
   - Boolean values
   - Lists/tuples containing a single numeric value
   - Invalid inputs (return a default value)

3. Write a program that prompts the user to enter a temperature in Fahrenheit and converts it to Celsius using the formula: C = (F - 32) * 5/9. Make sure to properly handle type conversion and format the output to 1 decimal place.

4. Given a hexadecimal color code (e.g., "#FF5733"), write a program to convert it to its RGB values (as integers). The output should be in the format: "RGB: (255, 87, 51)".

5. Create a program that asks the user to enter a list of numbers separated by commas. Convert the input to:
   a) A list of numbers
   b) A tuple of numbers
   c) A set that contains only unique numbers
   d) A dictionary where the keys are the positions (0, 1, 2...) and the values are the numbers
   
   For example, if the user enters "5,2,8,2,1", your program should display:
   - List: [5, 2, 8, 2, 1]
   - Tuple: (5, 2, 8, 2, 1)
   - Set: {1, 2, 5, 8}
   - Dictionary: {0: 5, 1: 2, 2: 8, 3: 2, 4: 1}