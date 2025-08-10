# Functions in Python

## Definition
A function in Python is a reusable block of code that performs a specific task. Functions are defined using the `def` keyword, followed by the function name and parentheses `()`. They help organize code, avoid repetition, and make programs easier to understand.

## Why Use Functions
1. **Code reusability**: Write code once and use it many times
2. **Organization**: Break complex problems into smaller, manageable parts
3. **Readability**: Make code easier to understand and maintain
4. **Testing**: Test individual parts of your program separately
5. **Modularity**: Create building blocks that can be combined to build larger programs

## Examples

### Example 1: Simple Function with No Parameters
```python
# Define a function
def greet():
    print("Hello! Welcome to Python programming.")

# Call the function
greet()
```
This function simply prints a greeting message when called.

### Example 2: Function with Parameters
```python
# Define a function with parameters
def greet_person(name):
    print(f"Hello, {name}! Welcome to Python programming.")

# Call the function with an argument
greet_person("Alex")
```
This function takes a name as input and prints a personalized greeting.

### Example 3: Function with Return Value
```python
# Define a function that returns a value
def add_numbers(a, b):
    sum = a + b
    return sum

# Call the function and store the result
result = add_numbers(5, 3)
print("The sum is:", result)
```
This function adds two numbers and returns the result.

### Example 4: Function with Default Parameter Values
```python
# Define a function with default parameter value
def greet_with_message(name, message="Good day"):
    print(f"{message}, {name}!")

# Call the function with and without the optional argument
greet_with_message("Alex")  # Uses the default message
greet_with_message("Taylor", "Welcome back")  # Uses the provided message
```
This function has a parameter with a default value which is used when no argument is provided.

### Example 5: Function with Multiple Return Values
```python
# Function that returns multiple values
def calculate(a, b):
    addition = a + b
    subtraction = a - b
    multiplication = a * b
    return addition, subtraction, multiplication

# Call the function and unpack the returned values
sum_result, diff_result, product_result = calculate(10, 5)
print("Sum:", sum_result)
print("Difference:", diff_result)
print("Product:", product_result)
```
This function performs multiple calculations and returns all results at once.

## Practice Questions

1. Write a function called `print_name` that takes a person's name as a parameter and prints "My name is [name]".

2. Create a function called `square` that takes a number as a parameter and returns the square of that number.

3. Write a function called `is_even` that takes a number as a parameter and returns `True` if the number is even, and `False` if it's odd.

4. Create a function called `max_of_three` that takes three numbers as parameters and returns the largest of the three.

5. Write a function called `convert_temperature` that takes a temperature in Celsius and converts it to Fahrenheit. The formula is: Fahrenheit = (Celsius * 9/5) + 32.

6. Create a function called `count_vowels` that takes a string as a parameter and returns the number of vowels (a, e, i, o, u) in the string.

7. Write a function called `calculator` that takes two numbers and an operation (as a string: "add", "subtract", "multiply", or "divide") as parameters and returns the result of the operation.