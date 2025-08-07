# Python Operators

## Definition

Operators in Python are special symbols that perform operations on variables and values. They are used to perform mathematical, logical, bitwise operations, and more on operands.

## Syntax

```python
operand1 operator operand2
```

Some operators are unary (require only one operand):

```python
operator operand  # Prefix unary operator
operand operator  # Postfix unary operator
```

## Types of Operators

### 1. Arithmetic Operators

| Operator | Name | Description | Example |
|----------|------|-------------|---------|
| + | Addition | Adds two operands | 5 + 3 = 8 |
| - | Subtraction | Subtracts right operand from left | 5 - 3 = 2 |
| * | Multiplication | Multiplies two operands | 5 * 3 = 15 |
| / | Division | Divides left operand by right (result is float) | 5 / 3 = 1.6666... |
| // | Floor Division | Divides and returns quotient as integer | 5 // 3 = 1 |
| % | Modulus | Returns remainder of division | 5 % 3 = 2 |
| ** | Exponentiation | Left operand raised to power of right | 5 ** 3 = 125 |

#### Example: Arithmetic Operators

```python
a = 10
b = 3

print(a + b)   # Addition: 13
print(a - b)   # Subtraction: 7
print(a * b)   # Multiplication: 30
print(a / b)   # Division: 3.3333...
print(a // b)  # Floor Division: 3
print(a % b)   # Modulus: 1
print(a ** b)  # Exponentiation: 1000
```

### 2. Comparison (Relational) Operators

| Operator | Name | Description | Example |
|----------|------|-------------|---------|
| == | Equal | True if operands are equal | 5 == 5 is True |
| != | Not Equal | True if operands are not equal | 5 != 3 is True |
| > | Greater Than | True if left operand is greater than right | 5 > 3 is True |
| < | Less Than | True if left operand is less than right | 5 < 3 is False |
| >= | Greater Than or Equal | True if left operand is greater than or equal to right | 5 >= 5 is True |
| <= | Less Than or Equal | True if left operand is less than or equal to right | 5 <= 3 is False |

#### Example: Comparison Operators

```python
x = 5
y = 10

print(x == y)  # Equal to: False
print(x != y)  # Not equal to: True
print(x > y)   # Greater than: False
print(x < y)   # Less than: True
print(x >= y)  # Greater than or equal to: False
print(x <= y)  # Less than or equal to: True
```

### 3. Logical Operators

| Operator | Name | Description | Example |
|----------|------|-------------|---------|
| and | Logical AND | True if both operands are true | True and False is False |
| or | Logical OR | True if either operand is true | True or False is True |
| not | Logical NOT | True if operand is false | not True is False |

#### Example: Logical Operators

```python
p = True
q = False

print(p and q)  # Logical AND: False
print(p or q)   # Logical OR: True
print(not p)    # Logical NOT: False

# Real-world example
age = 25
has_id = True
can_enter = age >= 21 and has_id
print(can_enter)  # Output: True
```

### 4. Assignment Operators

| Operator | Description | Example | Equivalent to |
|----------|-------------|---------|--------------|
| = | Assigns value | x = 5 | x = 5 |
| += | Add and assign | x += 3 | x = x + 3 |
| -= | Subtract and assign | x -= 3 | x = x - 3 |
| *= | Multiply and assign | x *= 3 | x = x * 3 |
| /= | Divide and assign | x /= 3 | x = x / 3 |
| //= | Floor divide and assign | x //= 3 | x = x // 3 |
| %= | Modulus and assign | x %= 3 | x = x % 3 |
| **= | Exponentiate and assign | x **= 3 | x = x ** 3 |

#### Example: Assignment Operators

```python
x = 10

x += 5   # x = x + 5
print(x)  # Output: 15

x -= 3   # x = x - 3
print(x)  # Output: 12

x *= 2   # x = x * 2
print(x)  # Output: 24

x /= 4   # x = x / 4
print(x)  # Output: 6.0 (result is float)

x //= 2  # x = x // 2
print(x)  # Output: 3.0 (still float because x was float)

y = 13
y %= 5   # y = y % 5
print(y)  # Output: 3
```

### 5. Bitwise Operators

| Operator | Name | Description |
|----------|------|-------------|
| & | Bitwise AND | Performs bit by bit AND operation |
| \| | Bitwise OR | Performs bit by bit OR operation |
| ^ | Bitwise XOR | Performs bit by bit XOR operation |
| ~ | Bitwise NOT | Inverts all the bits |
| << | Left Shift | Shifts left by pushing zeros in from the right |
| >> | Right Shift | Shifts right by pushing copies of the leftmost bit from the left |

#### Example: Bitwise Operators

```python
a = 10  # 1010 in binary
b = 4   # 0100 in binary

print(a & b)   # Bitwise AND: 0 (0000)
print(a | b)   # Bitwise OR: 14 (1110)
print(a ^ b)   # Bitwise XOR: 14 (1110)
print(~a)      # Bitwise NOT: -11 (complement of 1010)
print(a << 1)  # Left Shift: 20 (10100)
print(a >> 1)  # Right Shift: 5 (0101)
```

### 6. Identity Operators

| Operator | Description | Example |
|----------|-------------|---------|
| is | True if operands are identical (same object) | x is y |
| is not | True if operands are not identical (different objects) | x is not y |

#### Example: Identity Operators

```python
list1 = [1, 2, 3]
list2 = [1, 2, 3]
list3 = list1

print(list1 is list3)     # True (same object)
print(list1 is list2)     # False (different objects)
print(list1 is not list2) # True
```

### 7. Membership Operators

| Operator | Description | Example |
|----------|-------------|---------|
| in | True if value/variable is found in the sequence | 3 in [1, 2, 3] |
| not in | True if value/variable is not found in the sequence | 4 not in [1, 2, 3] |

#### Example: Membership Operators

```python
fruits = ["apple", "banana", "cherry"]
print("banana" in fruits)     # True
print("orange" not in fruits) # True

text = "Python"
print("P" in text)      # True
print("z" not in text)  # True
```

## Operator Precedence

From highest to lowest precedence:

1. `()` - Parentheses
2. `**` - Exponentiation
3. `+x`, `-x`, `~x` - Unary plus, minus, NOT
4. `*`, `/`, `//`, `%` - Multiplication, Division, Floor division, Modulus
5. `+`, `-` - Addition, Subtraction
6. `<<`, `>>` - Shifts
7. `&` - Bitwise AND
8. `^` - Bitwise XOR
9. `|` - Bitwise OR
10. `==`, `!=`, `<`, `<=`, `>`, `>=`, `is`, `is not`, `in`, `not in` - Comparisons, identity, membership
11. `not` - Boolean NOT
12. `and` - Boolean AND
13. `or` - Boolean OR

## Practice Questions for Placement Preparation

1. **Basic:** Write a program to calculate the area and perimeter of a rectangle using arithmetic operators. The length is 7 and the width is 5.

2. **Intermediate:** Create a program that categorizes a person's BMI using comparison and logical operators:
   - BMI < 18.5: "Underweight"
   - 18.5 <= BMI < 25: "Normal"
   - 25 <= BMI < 30: "Overweight"
   - BMI >= 30: "Obese"

3. **Advanced:** Given variables `a = 15` and `b = 7`, calculate the values of bitwise operations.

4. **Challenge:** Write a program that checks if a user-provided number is divisible by both 3 and 5, only by 3, only by 5, or by neither.

5. **Real-world:** Using membership and identity operators, write code to check if 'python' is in a list of programming languages and compare two identical lists.