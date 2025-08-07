# Python Sets

## Definition
A set in Python is an unordered collection of unique, immutable elements. Sets are defined by enclosing comma-separated values within curly braces `{}` or by using the `set()` constructor. The elements in a set cannot be duplicated, and while sets themselves are mutable (can be modified), the elements they contain must be immutable (like numbers, strings, or tuples, but not lists or dictionaries).

## Why Use Sets?
1. **Uniqueness**: Sets automatically eliminate duplicate values, making them ideal for storing unique elements.
2. **Fast Membership Testing**: Checking if an item exists in a set is much faster than in lists, especially for large collections.
3. **Mathematical Operations**: Sets support mathematical operations like union, intersection, and difference, making them perfect for comparison tasks.
4. **Data Deduplication**: Sets provide an efficient way to remove duplicates from sequences.
5. **Problem Solving**: Sets simplify solutions for many algorithmic problems where we need to track unique occurrences or find common/different elements.

## Examples

### Example 1: Creating and Basic Operations
```python
# Creating sets
empty_set = set()  # Empty set (cannot use {} as that creates an empty dictionary)
numbers = {1, 2, 3, 4, 5}
fruits = {'apple', 'banana', 'cherry'}

# Creating a set from an iterable
letters = set('hello')  # {'h', 'e', 'l', 'o'}
print(letters)  # Note: duplicates ('l') are removed and order is not preserved

# Adding elements
fruits.add('orange')
print(fruits)  # {'cherry', 'orange', 'apple', 'banana'} (order may vary)

# Adding multiple elements
fruits.update(['grape', 'kiwi'])
print(fruits)  # {'cherry', 'orange', 'grape', 'apple', 'kiwi', 'banana'} (order may vary)

# Removing elements
fruits.remove('banana')  # Raises KeyError if element doesn't exist
print(fruits)

fruits.discard('mango')  # No error if element doesn't exist
print(fruits)

popped = fruits.pop()  # Removes and returns an arbitrary element
print(popped)
print(fruits)

# Clearing a set
fruits.clear()
print(fruits)  # set()
```

### Example 2: Set Operations
```python
A = {1, 2, 3, 4, 5}
B = {4, 5, 6, 7, 8}

# Union (all elements from both sets)
union1 = A | B
union2 = A.union(B)
print(union1)  # {1, 2, 3, 4, 5, 6, 7, 8}
print(union2)  # {1, 2, 3, 4, 5, 6, 7, 8}

# Intersection (elements common to both sets)
intersection1 = A & B
intersection2 = A.intersection(B)
print(intersection1)  # {4, 5}
print(intersection2)  # {4, 5}

# Difference (elements in first set but not in second)
difference1 = A - B
difference2 = A.difference(B)
print(difference1)  # {1, 2, 3}
print(difference2)  # {1, 2, 3}

# Symmetric difference (elements in either set but not in both)
sym_diff1 = A ^ B
sym_diff2 = A.symmetric_difference(B)
print(sym_diff1)  # {1, 2, 3, 6, 7, 8}
print(sym_diff2)  # {1, 2, 3, 6, 7, 8}
```

### Example 3: Set Methods and Relations
```python
A = {1, 2, 3}
B = {1, 2, 3, 4, 5}
C = {6, 7, 8}

# Testing if a set is a subset of another
print(A.issubset(B))  # True - all elements of A are in B
print(A <= B)  # True - same as issubset
print(A < B)   # True - A is a proper subset of B (A ≠ B)

# Testing if a set is a superset of another
print(B.issuperset(A))  # True - all elements of A are in B
print(B >= A)  # True - same as issuperset
print(B > A)   # True - B is a proper superset of A (B ≠ A)

# Testing if sets are disjoint (have no elements in common)
print(A.isdisjoint(C))  # True
print(A.isdisjoint(B))  # False

# Testing if sets are equal
D = {3, 2, 1}  # Same elements as A but different order
print(A == D)  # True - sets with the same elements are equal regardless of order
print(A == B)  # False - sets contain different elements
```

### Example 4: Set Comprehensions and Common Use Cases
```python
# Set comprehension
squares = {x**2 for x in range(10)}
print(squares)  # {0, 1, 4, 9, 16, 25, 36, 49, 64, 81}

# Set comprehension with condition
even_squares = {x**2 for x in range(10) if x % 2 == 0}
print(even_squares)  # {0, 4, 16, 36, 64}

# Finding unique elements in a list
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]
unique_numbers = set(numbers)
print(unique_numbers)  # {1, 2, 3, 4}

# Counting unique elements
text = "mississippi"
unique_chars = set(text)
print(f"'{text}' has {len(unique_chars)} unique characters: {unique_chars}")
# 'mississippi' has 4 unique characters: {'m', 'i', 'p', 's'}

# Finding common elements across multiple lists
list1 = [1, 2, 3, 4]
list2 = [3, 4, 5, 6]
list3 = [4, 5, 6, 7]
common_elements = set(list1) & set(list2) & set(list3)
print(common_elements)  # {4}
```

### Example 5: Immutable Sets (Frozensets)
```python
# Creating a frozenset
regular_set = {1, 2, 3}
frozen = frozenset([1, 2, 3])

print(regular_set)  # {1, 2, 3}
print(frozen)       # frozenset({1, 2, 3})

# Attempting to modify (will cause error)
try:
    frozen.add(4)  # AttributeError: 'frozenset' object has no attribute 'add'
except AttributeError as e:
    print(f"Error: {e}")

# Using frozenset as a dictionary key
fs1 = frozenset([1, 2])
fs2 = frozenset([3, 4])
set_dict = {
    fs1: "First Set",
    fs2: "Second Set"
}
print(set_dict[fs1])  # "First Set"

# Set operations work with frozensets
A = frozenset([1, 2, 3])
B = frozenset([3, 4, 5])
print(A.union(B))         # frozenset({1, 2, 3, 4, 5})
print(A.intersection(B))  # frozenset({3})
print(A.difference(B))    # frozenset({1, 2})

# Converting between sets and frozensets
regular = set(frozen)  # Convert frozenset to regular set
frozen_again = frozenset(regular)  # Convert regular set to frozenset
```

## Practice Questions

1. **Basic:** Write a program that takes two lists as input and prints all the unique elements from both lists combined (with no duplicates).

2. **Intermediate:** Create a function called `find_unique_characters` that takes a string as input and returns a set of characters that appear exactly once in the string.

3. **Challenge:** Write a function that takes a list of integers and returns a set of all possible sums created by adding any two distinct numbers from the list.

4. **Applied:** Create a program that simulates a simple contact management system. Use sets to track unique phone numbers and email addresses, and provide functionality to find contacts with either duplicate phone numbers or duplicate email addresses.

5. **Advanced:** Implement a function called `powerset` that takes a set as input and returns the power set (the set of all possible subsets, including the empty set and the set itself). For example, powerset({1, 2}) should return a set containing {}, {1}, {2}, and {1, 2} (represented as frozensets).