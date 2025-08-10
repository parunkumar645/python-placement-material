# Recursion and Lambda Functions in Python

## Recursion

### Definition
Recursion is a programming technique where a function calls itself to solve a problem. A recursive function has two main components:
1. A base case that stops the recursion
2. A recursive case that continues the recursion by calling the function itself

### Why Use Recursion
1. Simplifies solving complex problems that can be broken down into simpler versions of the same problem
2. Creates cleaner and more elegant code for certain algorithms
3. Naturally implements mathematical concepts that are defined recursively
4. Effectively works with recursive data structures like trees
5. Can replace complex nested loops in some cases

### Examples

#### Example 1: Simple Countdown
```python
def countdown(n):
    # Base case
    if n <= 0:
        print("Blast off!")
    # Recursive case
    else:
        print(n)
        countdown(n-1)  # Function calls itself

# Call the function
countdown(5)
```
This function counts down from a number to 1, then prints "Blast off!".

#### Example 2: Calculate Factorial
```python
def factorial(n):
    # Base case
    if n == 0 or n == 1:
        return 1
    # Recursive case
    else:
        return n * factorial(n-1)  # Function calls itself

# Call the function
result = factorial(5)
print(f"5! = {result}")
```
This function calculates factorial (5! = 5×4×3×2×1 = 120).

#### Example 3: Sum of Numbers
```python
def sum_numbers(n):
    # Base case
    if n <= 0:
        return 0
    # Recursive case
    else:
        return n + sum_numbers(n-1)  # Function calls itself

# Call the function
result = sum_numbers(5)
print(f"Sum from 1 to 5 = {result}")
```
This function calculates the sum of numbers from 1 to n.

#### Example 4: Fibonacci Sequence
```python
def fibonacci(n):
    # Base cases
    if n <= 0:
        return 0
    elif n == 1:
        return 1
    # Recursive case
    else:
        return fibonacci(n-1) + fibonacci(n-2)  # Function calls itself twice

# Call the function
for i in range(8):
    print(f"Fibonacci({i}) = {fibonacci(i)}")
```
This function calculates the nth Fibonacci number.

#### Example 5: Print Elements of a List
```python
def print_list(my_list, index=0):
    # Base case
    if index >= len(my_list):
        return
    # Recursive case
    else:
        print(my_list[index])
        print_list(my_list, index + 1)  # Function calls itself

# Call the function
print_list(["apple", "banana", "cherry"])
```
This function prints each element of a list using recursion.

## Lambda Functions

### Definition
Lambda functions are small, anonymous (unnamed) functions defined using the `lambda` keyword. They can have any number of arguments but only one expression. The expression is evaluated and returned when the lambda function is called.

### Why Use Lambda Functions
1. Create simple functions without using the `def` keyword
2. Write compact, one-line functions for simple operations
3. Use functions in places where a function is needed temporarily
4. Pass functions as arguments to other functions
5. Create function closures and callbacks

### Examples

#### Example 1: Simple Lambda Function
```python
# Regular function
def square(x):
    return x * x

# Equivalent lambda function
square_lambda = lambda x: x * x

# Using both functions
print("Regular function:", square(5))
print("Lambda function:", square_lambda(5))
```
This example compares a regular function and a lambda function that square a number.

#### Example 2: Lambda with Multiple Arguments
```python
# Lambda function with multiple arguments
add = lambda a, b: a + b

# Using the lambda function
result = add(3, 5)
print("Sum:", result)
```
This example creates a lambda function that adds two numbers.

#### Example 3: Lambda with Conditional Expression
```python
# Lambda function with conditional
is_even = lambda x: True if x % 2 == 0 else False

# Using the lambda function
print("Is 4 even?", is_even(4))
print("Is 7 even?", is_even(7))
```
This example creates a lambda function that checks if a number is even.

#### Example 4: Lambda with Built-in Functions
```python
# List of numbers
numbers = [1, 5, 4, 3, 2, 6]

# Using lambda with sorted()
sorted_numbers = sorted(numbers, key=lambda x: x)
print("Sorted numbers:", sorted_numbers)

# Using lambda with filter()
even_numbers = list(filter(lambda x: x % 2 == 0, numbers))
print("Even numbers:", even_numbers)

# Using lambda with map()
squared_numbers = list(map(lambda x: x * x, numbers))
print("Squared numbers:", squared_numbers)
```
This example demonstrates using lambda functions with built-in functions like sorted(), filter(), and map().

#### Example 5: Lambda as a Quick Calculator
```python
# Dictionary of lambda operations
operations = {
    'add': lambda a, b: a + b,
    'subtract': lambda a, b: a - b,
    'multiply': lambda a, b: a * b,
    'divide': lambda a, b: a / b if b != 0 else "Cannot divide by zero"
}

# Using the lambda calculator
print("5 + 3 =", operations['add'](5, 3))
print("5 - 3 =", operations['subtract'](5, 3))
print("5 * 3 =", operations['multiply'](5, 3))
print("5 / 3 =", operations['divide'](5, 3))
```
This example creates a simple calculator using a dictionary of lambda functions.

## Practice Questions

### Recursion Practice
1. Write a recursive function to calculate the sum of digits in a positive number. For example, sum_digits(123) should return 6 (1+2+3).

2. Create a recursive function to count down from 10 to 1 and print each number.

3. Write a recursive function that prints each character of a string one by one.

4. Create a recursive function to find the maximum number in a list.

5. Write a recursive function to reverse a string. For example, reverse("hello") should return "olleh".

### Lambda Practice
1. Create a lambda function that returns the square of a number, and use it to calculate the square of 7.

2. Write a lambda function that takes two arguments and returns their product.

3. Create a lambda function to check if a number is positive, and test it with both positive and negative numbers.

4. Use the `sorted()` function with a lambda to sort a list of words by their length: ["apple", "banana", "cherry", "date"].

5. Create a list of numbers and use `filter()` with a lambda function to get only the numbers greater than 10.