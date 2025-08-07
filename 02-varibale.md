# Python Variables

## Definition

Variables in Python are named containers that store data values. They are used to reference and manipulate data within a program. Python uses dynamic typing, which means you don't need to declare a variable's type before using it.

## Syntax

```python
variable_name = value
```

- Variable names must start with a letter or underscore
- Can contain letters, numbers, and underscores
- Cannot use reserved keywords
- Case-sensitive (age and Age are different variables)

## Examples

### Example 1: Basic Variable Assignment

```python
name = "John"
age = 25
print(name)  # Output: John
print(age)   # Output: 25
```

### Example 2: Multiple Assignment

```python
x, y, z = 10, 20, 30
print(x)  # Output: 10
print(y)  # Output: 20
print(z)  # Output: 30
```

### Example 3: Changing Variable Values

```python
counter = 1
print(counter)  # Output: 1
counter = counter + 1
print(counter)  # Output: 2
counter += 1    # Shorthand for counter = counter + 1
print(counter)  # Output: 3
```

### Example 4: Variable Naming Conventions

```python
# Valid variable names
student_name = "Alice"
_private = "Hidden"
total2 = 100

# Invalid variable names (would cause errors)
# 2total = 200      # Cannot start with a number
# my-var = 300      # Hyphens not allowed
# class = "Python"  # Cannot use reserved keywords
```

### Example 5: Type Conversion

```python
num_str = "42"
num_int = int(num_str)
print(num_str)     # Output: 42 (as string)
print(num_int)     # Output: 42 (as integer)
print(num_int + 8) # Output: 50 (numeric addition)
print(num_str + "8") # Output: 428 (string concatenation)
```

## Key Points for Placement Preparation

1. **Variable Naming Rules**: Remember the rules for valid variable names
2. **Multiple Assignment**: Know how to assign multiple variables in one line
3. **Variable Scope**: Understand local vs global variables
4. **Memory Management**: Python handles memory allocation automatically
5. **Dynamic Typing**: Variables can change type during runtime