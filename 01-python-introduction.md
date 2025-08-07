# Python Introduction

## What is Python?

Python is a high-level, interpreted programming language known for its simplicity and readability. Created by Guido van Rossum and first released in 1991, Python emphasizes code readability with its notable use of significant whitespace. It's a versatile language that supports multiple programming paradigms, including procedural, object-oriented, and functional programming.

## Why Python?

* **Simplicity and Readability**: Python's clean syntax makes it easy to learn and maintain
* **Versatility**: Can be used for web development, data analysis, AI, scientific computing, and more
* **Large Standard Library**: Comes with a rich set of modules and packages
* **Active Community**: Extensive support from a large community of developers
* **Cross-platform**: Runs on Windows, macOS, Linux, and more

## Examples of Basic Python Code

### 1. Hello World

```python
print("Hello, World!")
```

### 2. Variables and Simple Calculations

```python
# Defining variables
x = 10
y = 5

# Basic operations
addition = x + y
subtraction = x - y
multiplication = x * y
division = x / y

print(f"Addition: {addition}")
print(f"Subtraction: {subtraction}")
print(f"Multiplication: {multiplication}")
print(f"Division: {division}")
```

### 3. Using Strings

```python
name = "Python"
version = 3.10
message = name + " version " + str(version)
print(message)

# String methods
print(name.upper())
print(name.lower())
print(len(name))
```

### 4. Conditional Statements

```python
age = 20
if age >= 18:
    print("Adult")
else:
    print("Minor")
```

### 5. Loops

```python
# For loop
for i in range(5):
    print(i)

# While loop
count = 0
while count < 5:
    print(count)
    count += 1
```