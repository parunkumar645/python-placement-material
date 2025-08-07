# Python Input and Output

## Definition
Input and output operations in Python allow programs to interact with users, files, and other systems by receiving data (input) and presenting results (output). These operations are fundamental for creating interactive programs and processing data.

## Input Operations

### 1. `input()` Function

#### Definition
The `input()` function allows a program to get user input from the command line. It reads a line from input (usually keyboard) and returns it as a string.

#### Syntax
```python
variable_name = input(prompt)
```
- `prompt`: Optional string displayed to the user before input
- `variable_name`: Variable that stores the input value

#### Key Points
- Always returns input as a string, even if numbers are entered
- Program execution pauses until the user provides input
- To get numeric input, explicit type conversion is required

## Output Operations

### 1. `print()` Function

#### Definition
The `print()` function displays specified output to the console or standard output device.

#### Syntax
```python
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```
- `*objects`: One or more objects to print (comma-separated)
- `sep`: Separator between objects (default is space)
- `end`: What to print at the end (default is newline)
- `file`: Output stream (default is console)
- `flush`: Whether to force buffer flush (default is False)

### 2. String Formatting

#### a. f-strings (Python 3.6+)
```python
name = "Alice"
age = 30
print(f"My name is {name} and I am {age} years old.")
```

#### b. `.format()` Method
```python
name = "Bob"
age = 25
print("My name is {} and I am {} years old.".format(name, age))
```

#### c. % Operator (older style)
```python
name = "Charlie"
age = 35
print("My name is %s and I am %d years old." % (name, age))
```

## File Input/Output

### 1. Opening Files

#### Syntax
```python
file_object = open(filename, mode)
```

#### Common Modes
- `'r'`: Read (default) - open for reading
- `'w'`: Write - open for writing (creates new file or truncates existing)
- `'a'`: Append - open for writing at end of file
- `'b'`: Binary mode (added to other modes)
- `'t'`: Text mode (default)
- `'+'`: Update mode (read and write)

### 2. Reading Files

```python
# Read entire file
with open('filename.txt', 'r') as file:
    content = file.read()

# Read line by line
with open('filename.txt', 'r') as file:
    for line in file:
        print(line, end='')
        
# Read all lines as a list
with open('filename.txt', 'r') as file:
    lines = file.readlines()
```

### 3. Writing Files

```python
# Write string to file
with open('filename.txt', 'w') as file:
    file.write('Hello, World!\n')
    file.write('This is a new line.')
    
# Write multiple lines
lines = ['Line 1', 'Line 2', 'Line 3']
with open('filename.txt', 'w') as file:
    file.writelines(line + '\n' for line in lines)
```

### 4. Context Manager (`with` statement)

```python
# Recommended way to handle files
with open('filename.txt', 'r') as file:
    content = file.read()
# File is automatically closed when exiting the block
```

## Examples

### Example 1: Basic Input and Output
```python
# Getting text input
name = input("Enter your name: ")
print("Hello, " + name + "!")

# Getting numeric input
age_str = input("Enter your age: ")
age = int(age_str)  # Convert string to integer
print(f"In 10 years, you will be {age + 10} years old.")
```

### Example 2: Formatting Output
```python
# Different ways to format strings
name = "Alice"
age = 30
height = 1.75
is_student = True

# f-strings (Python 3.6+)
print(f"Name: {name}, Age: {age}, Height: {height:.2f}m, Student: {is_student}")

# .format() method
print("Name: {}, Age: {}, Height: {:.2f}m, Student: {}".format(name, age, height, is_student))

# % operator
print("Name: %s, Age: %d, Height: %.2fm, Student: %s" % (name, age, height, is_student))

# Using print parameters
print("Statistics:", name, age, height, is_student, sep=" | ")
print("This is line 1", end=" >>> ")
print("This is line 2")
```

### Example 3: Working with User Input
```python
# Simple calculator
num1 = float(input("Enter first number: "))
num2 = float(input("Enter second number: "))
operation = input("Enter operation (+, -, *, /): ")

if operation == '+':
    result = num1 + num2
elif operation == '-':
    result = num1 - num2
elif operation == '*':
    result = num1 * num2
elif operation == '/':
    if num2 != 0:
        result = num1 / num2
    else:
        result = "Error: Division by zero"
else:
    result = "Error: Invalid operation"

print(f"Result: {result}")
```

### Example 4: Reading from a File
```python
# Reading a file and analyzing content
try:
    with open('sample.txt', 'r') as file:
        content = file.read()
        
        # Basic text analysis
        char_count = len(content)
        word_count = len(content.split())
        line_count = content.count('\n') + 1  # +1 for the last line
        
        print(f"File Statistics:")
        print(f"- Characters: {char_count}")
        print(f"- Words: {word_count}")
        print(f"- Lines: {line_count}")
        
        # Print first 50 characters
        print("\nPreview:")
        print(content[:50] + "..." if len(content) > 50 else content)
        
except FileNotFoundError:
    print("Error: File not found.")
except Exception as e:
    print(f"An error occurred: {e}")
```

### Example 5: Writing to a File
```python
# Creating a simple log file
import datetime

def log_activity(activity):
    timestamp = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
    log_entry = f"[{timestamp}] {activity}\n"
    
    with open('activity_log.txt', 'a') as log_file:
        log_file.write(log_entry)
    
    print(f"Activity logged: {activity}")

# Sample usage
log_activity("Program started")
name = input("Enter your name: ")
log_activity(f"User {name} logged in")
# ... more program code ...
log_activity("Program ended")

# Reading the log file
print("\nCurrent log contents:")
try:
    with open('activity_log.txt', 'r') as log_file:
        print(log_file.read())
except FileNotFoundError:
    print("Log file not found.")
```

## Practice Questions

1. Write a program that asks the user for their name, age, and favorite color. Then print a message in the format: "Hello, [name]! You are [age] years old and your favorite color is [color]."

2. Create a program that asks the user to enter 5 numbers (one at a time), stores them in a list, and then displays:
   - The numbers entered
   - The sum of the numbers
   - The average of the numbers
   - The maximum and minimum values

3. Write a program that prompts the user to enter a filename. The program should read the file and count the occurrences of each word, then display the 5 most common words and their counts. Handle cases where the file doesn't exist.

4. Create a program that generates a simple quiz. The program should:
   - Ask the user for their name
   - Present 3 multiple-choice questions (with options a, b, c, d)
   - Grade the answers and show the final score
   - Write the results to a file named "quiz_results.txt" in the format: "[Name] - [Score]/3 - [Date/Time]"

5. Write a program that simulates a simple address book. The program should:
   - Allow users to add contacts (name, phone, email)
   - Display all contacts
   - Search for a contact by name
   - Save contacts to a file called "contacts.txt"
   - Load contacts from "contacts.txt" when the program starts
   
   Use file I/O operations to ensure the contacts persist between program runs.