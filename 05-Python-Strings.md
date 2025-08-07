# Python Strings

## Definition
A string in Python is a sequence of characters enclosed within quotation marks. Strings are immutable data types, which means once a string is created, it cannot be modified. Python allows strings to be enclosed in single quotes (`'...'`), double quotes (`"..."`), or triple quotes (`'''...'''` or `"""..."""`) for multi-line strings.

## Why Use Strings?
1. **Text Representation**: Strings allow you to store and manipulate text data in your programs.
2. **Data Processing**: They are essential for working with user input, file content, and internet data.
3. **Rich Operations**: Python provides numerous built-in methods to manipulate strings efficiently.
4. **Universal Compatibility**: Strings can represent almost any kind of data and can be easily converted to other data types.
5. **Human-readable Output**: They are used to display information to users in a readable format.

## Examples

### Example 1: String Creation and Basic Operations
```python
# Creating strings
name = "Python"
message = 'Learning strings is fun!'
multi_line = """This is a
multi-line
string."""

# String concatenation
greeting = "Hello, " + name + "!"
print(greeting)  # Output: Hello, Python!

# String repetition
repeat = name * 3
print(repeat)  # Output: PythonPythonPython

# String length
print(len(name))  # Output: 6
```

### Example 2: String Indexing and Slicing
```python
text = "Python Programming"

# Indexing (accessing individual characters)
first_char = text[0]     # P
last_char = text[-1]     # g

print(f"First character: {first_char}")
print(f"Last character: {last_char}")

# Slicing (extracting substrings)
first_word = text[0:6]   # Python
second_word = text[7:]   # Programming

print(f"First word: {first_word}")
print(f"Second word: {second_word}")

# Stride
every_second = text[::2]  # Pto rgamn
print(f"Every second character: {every_second}")

# Reverse string
reversed_text = text[::-1]  # gnimmargorP nohtyP
print(f"Reversed text: {reversed_text}")
```

### Example 3: String Methods
```python
message = "  Python is Amazing!  "

# Case methods
print(message.upper())      # PYTHON IS AMAZING!  
print(message.lower())      # python is amazing!  
print(message.title())      # Python Is Amazing!  

# Removing whitespace
print(message.strip())      # Python is Amazing!
print(message.lstrip())     # Python is Amazing!  
print(message.rstrip())     #   Python is Amazing!

# Checking content
print("Python" in message)  # True
print(message.startswith("Python"))  # False (because of leading spaces)
print(message.strip().startswith("Python"))  # True

# Finding substrings
print(message.find("is"))   # 9
print(message.count("a"))   # 1 (case sensitive)
```

### Example 4: String Formatting
```python
name = "Alice"
age = 25
height = 1.75

# Using f-strings (Python 3.6+)
info1 = f"Name: {name}, Age: {age}, Height: {height:.2f}m"
print(info1)  # Name: Alice, Age: 25, Height: 1.75m

# Using format() method
info2 = "Name: {}, Age: {}, Height: {:.2f}m".format(name, age, height)
print(info2)  # Name: Alice, Age: 25, Height: 1.75m

# Using % operator (older style)
info3 = "Name: %s, Age: %d, Height: %.2fm" % (name, age, height)
print(info3)  # Name: Alice, Age: 25, Height: 1.75m
```

### Example 5: String Methods for Analysis and Modification
```python
sentence = "Python programming is both fun and challenging"

# Splitting strings
words = sentence.split()
print(words)  # ['Python', 'programming', 'is', 'both', 'fun', 'and', 'challenging']

# Joining strings
rejoined = "-".join(words)
print(rejoined)  # Python-programming-is-both-fun-and-challenging

# Replacing substrings
modified = sentence.replace("challenging", "rewarding")
print(modified)  # Python programming is both fun and rewarding

# Checking string properties
print(sentence.isalpha())  # False (contains spaces)
print("Python".isalpha())  # True
print("123".isdigit())     # True
print("Python3".isalnum()) # True
```

## Practice Questions

1. **Basic:** Write a program that takes a user's name as input and prints "Hello, [name]!".

2. **Intermediate:** Create a function called `count_vowels` that takes a string as input and returns the number of vowels (a, e, i, o, u) in the string.

3. **Challenge:** Write a function called `is_palindrome` that checks if a given string is a palindrome (reads the same forwards and backwards, ignoring case and non-alphanumeric characters).

4. **Applied:** Create a program that takes a sentence as input and returns the same sentence with each word reversed, but the order of words remains the same. For example, "Python is fun" should become "nohtyP si nuf".

5. **Advanced:** Write a function called `password_strength` that evaluates a password string and returns a score from 0-5 based on:
   - Length (at least 8 characters)
   - Contains uppercase letters
   - Contains lowercase letters
   - Contains numbers
   - Contains special characters
   
   For each criterion met, add 1 to the score.