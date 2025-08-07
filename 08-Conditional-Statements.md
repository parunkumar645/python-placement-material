# Conditional Statements in Python

## Definition
Conditional statements in Python are programming constructs that allow the execution of different code blocks based on whether specified conditions evaluate to True or False. These statements help create decision-making capabilities within programs, enabling different paths of execution depending on various conditions.

## Why Use Conditional Statements
Conditional statements are essential in programming for several reasons:
1. **Decision making**: They allow programs to make decisions and execute different code blocks based on conditions.
2. **Flow control**: They help control the flow of program execution.
3. **Error handling**: They facilitate error checking and appropriate responses.
4. **Data validation**: They enable validation of input data before processing.
5. **Optimization**: They allow for efficient resource allocation by executing only necessary code.

## Examples

### Example 1: Basic if statement
```python
# Checking if a number is positive
number = 10
if number > 0:
    print("The number is positive")
```
This example demonstrates the simplest form of a conditional statement. The program checks if the number is greater than zero and prints a message if true.

### Example 2: if-else statement
```python
# Determining if a number is even or odd
number = 15
if number % 2 == 0:
    print(f"{number} is an even number")
else:
    print(f"{number} is an odd number")
```
Here, the program checks if a number is divisible by 2. If true, it prints that the number is even; otherwise, it prints that the number is odd.

### Example 3: if-elif-else chain
```python
# Grade classification
score = 85
if score >= 90:
    grade = "A"
elif score >= 80:
    grade = "B"
elif score >= 70:
    grade = "C"
elif score >= 60:
    grade = "D"
else:
    grade = "F"
print(f"The grade is {grade}")
```
This example demonstrates how to handle multiple conditions. The program determines a letter grade based on a numerical score using a chain of if-elif-else statements.

### Example 4: Nested conditional statements
```python
# Determining eligibility for a discount
age = 25
is_student = True
if age < 30:
    if is_student:
        print("You qualify for the young student discount")
    else:
        print("You qualify for the young adult discount")
else:
    print("Standard pricing applies")
```
This example shows how conditional statements can be nested within each other. The program first checks the age and then checks student status to determine discount eligibility.

### Example 5: Conditional expressions (ternary operator)
```python
# Determining the larger of two numbers
a = 15
b = 20
larger = a if a > b else b
print(f"The larger number is {larger}")
```
This example demonstrates Python's ternary operator, a compact way to write simple if-else statements in a single line.

## Practice Questions

1. Write a program that takes a user's age as input and determines if they are eligible to vote (18 years or older).

2. Create a program that checks if a year entered by the user is a leap year. (Hint: A leap year is divisible by 4 but not by 100 unless it is also divisible by 400.)

3. Write a program that takes a number as input and determines if it is positive, negative, or zero.

4. Create a program that takes three numbers as input and prints the largest among them.

5. Write a program that calculates the Body Mass Index (BMI) of a person from their weight (in kg) and height (in meters), and then categorizes them as:
   - Underweight (BMI < 18.5)
   - Normal weight (18.5 ≤ BMI < 25)
   - Overweight (25 ≤ BMI < 30)
   - Obese (BMI ≥ 30)