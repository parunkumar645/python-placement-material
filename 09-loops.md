# Loops and Control Statements in Python (Simplified)

## For Loops

### Definition
A for loop in Python repeats a block of code for each item in a sequence (like a list or string).

### Why Use For Loops
1. To perform the same action on each item in a list
2. To repeat code a specific number of times
3. To process each character in a string
4. To make your program more efficient with less repetitive code

### Examples

#### Example 1: Basic for loop with a list
```python
fruits = ["apple", "banana", "orange"]
for fruit in fruits:
    print(fruit)
```
This prints each fruit on a new line.

#### Example 2: Using range() function
```python
# Print numbers from 1 to 5
for number in range(1, 6):
    print(number)
```
This prints numbers 1, 2, 3, 4, and 5.

#### Example 3: Simple sum calculation
```python
# Calculate the sum of numbers from 1 to 5
sum = 0
for number in range(1, 6):
    sum = sum + number
print("The sum is:", sum)
```
This calculates 1+2+3+4+5 and prints "The sum is: 15".

## While Loops

### Definition
A while loop repeats a block of code as long as a condition is True.

### Why Use While Loops
1. When you don't know in advance how many times to repeat code
2. When you need to repeat until a specific condition is met
3. When you want to create an infinite loop with a way to break out

### Examples

#### Example 1: Basic while loop
```python
# Count from 1 to 5
count = 1
while count <= 5:
    print(count)
    count = count + 1
```
This prints numbers 1, 2, 3, 4, and 5.

#### Example 2: Simple user input validation
```python
# Ask for a positive number
number = int(input("Enter a positive number: "))
while number <= 0:
    number = int(input("That's not positive. Try again: "))
print("You entered:", number)
```
This keeps asking for input until the user enters a positive number.

#### Example 3: Simple addition calculator
```python
total = 0
number = 1
while number != 0:
    number = int(input("Enter a number (0 to stop): "))
    total = total + number
print("Sum of all numbers:", total)
```
This adds all numbers entered until the user enters 0.

## Break and Continue Statements

### Definition
- **break**: Exits the loop immediately
- **continue**: Skips the current iteration and goes to the next one

### Examples

#### Example 1: Using break
```python
# Exit loop when finding the number 5
for number in range(1, 11):
    print(number)
    if number == 5:
        print("Found 5! Stopping.")
        break
```
This prints numbers 1 through 5, then stops.

#### Example 2: Using continue
```python
# Skip even numbers
for number in range(1, 11):
    if number % 2 == 0:
        continue
    print(number)
```
This prints only odd numbers: 1, 3, 5, 7, 9.

## Practice Questions

1. Write a program that uses a for loop to print numbers from 1 to 10.

2. Create a program that uses a for loop to print the multiplication table of 5 (5×1, 5×2, etc. up to 5×10).

3. Write a program that asks the user for a name and prints each letter of the name on a new line using a for loop.

4. Create a program using a while loop that counts down from 10 to 1, then prints "Blast off!".

5. Write a program that uses a while loop to ask the user to guess a secret number (let's say 7). Give them hints if they're wrong and congratulate them when they get it right.

6. Create a program that uses break to exit a loop when the user enters the word "exit".

7. Write a program that uses continue to skip printing numbers that are divisible by 3 when counting from 1 to 20.