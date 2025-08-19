# NumPy Teaching Materials

## Definition
NumPy (Numerical Python) is a fundamental library for scientific computing in Python. It provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays efficiently. NumPy serves as the foundation for many other Python data science and machine learning libraries.

## Why Use NumPy?
1. **Performance**: NumPy operations are executed in optimized, pre-compiled C code, making them much faster than equivalent Python code.
2. **Memory Efficiency**: NumPy arrays consume less memory and provide better data locality than Python lists.
3. **Vectorization**: Allows performing operations on entire arrays without explicit loops, resulting in cleaner, more readable code.
4. **Broadcasting**: Enables arithmetic operations between arrays of different shapes.
5. **Mathematical Functions**: Provides comprehensive mathematical functions for array operations.
6. **Integration**: Forms the foundation for the Python scientific computing ecosystem (pandas, matplotlib, scikit-learn, etc.).

## Where NumPy Is Used
1. **Data Analysis**: Manipulating and processing large datasets
2. **Machine Learning**: As a foundation for many ML libraries
3. **Scientific Research**: Physics, chemistry, biology, astronomy
4. **Financial Analysis**: Stock market data processing and modeling
5. **Image Processing**: Working with images as multi-dimensional arrays
6. **Signal Processing**: Audio and other signal analysis
7. **Mathematics and Statistics**: Linear algebra, probability, etc.
8. **Engineering Applications**: Simulations and modeling

## Examples

### 1. Installing NumPy
```python
# Using pip
pip install numpy

# Import numpy
import numpy as np
```

### 2. Creating Arrays
```python
# Creating arrays from Python lists
arr1 = np.array([1, 2, 3, 4, 5])
print(arr1)  # Output: [1 2 3 4 5]

# Creating a 2D array (matrix)
arr2 = np.array([[1, 2, 3], [4, 5, 6]])
print(arr2)
# Output:
# [[1 2 3]
#  [4 5 6]]

# Creating arrays with specific values
zeros = np.zeros((3, 4))  # 3x4 array of zeros
ones = np.ones((2, 3))    # 2x3 array of ones
empty = np.empty((2, 2))  # 2x2 uninitialized array

# Creating sequences
seq1 = np.arange(10)      # 0 to 9
seq2 = np.arange(2, 10, 2)  # 2, 4, 6, 8
lin_space = np.linspace(0, 1, 5)  # 5 evenly spaced points between 0 and 1

# Creating arrays with specific data types
int_array = np.array([1, 2, 3], dtype=np.int32)
float_array = np.array([1, 2, 3], dtype=np.float64)
```

### 3. Array Operations
```python
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])

# Element-wise operations
print(a + b)  # Output: [5 7 9]
print(a - b)  # Output: [-3 -3 -3]
print(a * b)  # Output: [4 10 18]
print(a / b)  # Output: [0.25 0.4 0.5]

# Scalar operations
print(a * 2)  # Output: [2 4 6]
print(a + 10) # Output: [11 12 13]

# Matrix operations
c = np.array([[1, 2], [3, 4]])
d = np.array([[5, 6], [7, 8]])

# Matrix multiplication
print(np.dot(c, d))
# Output:
# [[19 22]
#  [43 50]]

# Using the @ operator (Python 3.5+)
print(c @ d)
# Output:
# [[19 22]
#  [43 50]]
```

### 4. Indexing & Slicing
```python
arr = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]])

# Accessing elements
print(arr[0, 0])    # Output: 1
print(arr[2, 3])    # Output: 12

# Slicing
print(arr[0:2, 1:3])
# Output:
# [[2 3]
#  [6 7]]

# Using conditions for indexing
print(arr[arr > 5])  # Output: [ 6  7  8  9 10 11 12]

# Boolean masking
mask = (arr % 2 == 0)  # Create a boolean mask for even numbers
print(arr[mask])  # Output: [ 2  4  6  8 10 12]

# Changing values
arr[0, 0] = 100
print(arr)
# Output:
# [[100   2   3   4]
#  [  5   6   7   8]
#  [  9  10  11  12]]
```

### 5. Basic Math
```python
a = np.array([1, 2, 3, 4])

# Basic statistics
print(np.sum(a))        # Output: 10
print(np.mean(a))       # Output: 2.5
print(np.std(a))        # Output: 1.118...
print(np.var(a))        # Output: 1.25
print(np.min(a))        # Output: 1
print(np.max(a))        # Output: 4

# Trigonometric functions
angles = np.array([0, np.pi/2, np.pi])
print(np.sin(angles))   # Output: [0.0, 1.0, 0.0]
print(np.cos(angles))   # Output: [1.0, 0.0, -1.0]

# Exponential and logarithmic
print(np.exp(a))        # e^a for each element
print(np.log(a))        # natural log of each element
print(np.log10(a))      # base-10 log of each element
```

### 6. Useful Functions
```python
# Reshaping arrays
a = np.arange(12)
b = a.reshape(3, 4)  # Reshape to 3x4 matrix
print(b)
# Output:
# [[ 0  1  2  3]
#  [ 4  5  6  7]
#  [ 8  9 10 11]]

# Transposing arrays
print(b.T)
# Output:
# [[ 0  4  8]
#  [ 1  5  9]
#  [ 2  6 10]
#  [ 3  7 11]]

# Stacking arrays
a = np.array([1, 2, 3])
b = np.array([4, 5, 6])
print(np.vstack((a, b)))
# Output:
# [[1 2 3]
#  [4 5 6]]

print(np.hstack((a, b)))
# Output: [1 2 3 4 5 6]

# Splitting arrays
x = np.arange(9)
print(np.split(x, 3))
# Output: [array([0, 1, 2]), array([3, 4, 5]), array([6, 7, 8])]

# Finding unique elements
arr = np.array([1, 1, 2, 3, 3, 3, 4, 5, 5])
print(np.unique(arr))  # Output: [1 2 3 4 5]
```

### 7. Random Numbers
```python
# Generate random numbers
rand_nums = np.random.rand(5)  # 5 random numbers between 0 and 1
print(rand_nums)

# Random integers
rand_ints = np.random.randint(1, 100, 5)  # 5 random integers between 1 and 100
print(rand_ints)

# Normal distribution
normal_dist = np.random.normal(0, 1, 5)  # 5 samples from standard normal distribution
print(normal_dist)

# Setting seed for reproducibility
np.random.seed(42)
print(np.random.rand(3))  # Will always produce the same output
```

## Practice Questions

### Basic Level
1. What will be the output of the following code?
   ```python
   arr = np.array([1, 2, 3, 4, 5])
   print(arr[1:4])
   ```

2. How would you create a 3x3 array filled with zeros?

3. Write code to compute the sum of all elements in the array `np.array([5, 10, 15, 20])`.

4. What's the difference between `np.zeros(3)` and `np.zeros((3,))`?

5. How do you find the shape of an array?

### Intermediate Level
1. Write code to create a 1D array containing values from 10 to 30 with a step of 5.

2. Given array `a = np.array([[1, 2, 3], [4, 5, 6]])`, how would you select the element with value 5?

3. How would you find the mean of each column in a 2D array?
   ```python
   arr = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])
   # Write code to find column means
   ```

4. Write code to create a 3x3 identity matrix.

5. How would you find all elements in an array that are greater than 5?
   ```python
   arr = np.array([3, 6, 2, 8, 1, 9, 4, 7])
   # Write code to find elements > 5
   ```

### Advanced Level
1. Given two arrays, how would you find the elements that exist in both arrays?
   ```python
   arr1 = np.array([1, 2, 3, 4, 5])
   arr2 = np.array([3, 4, 5, 6, 7])
   # Write code to find common elements
   ```

2. Write code to normalize an array (subtract the mean and divide by standard deviation).
   ```python
   arr = np.array([10, 15, 8, 25, 12])
   # Write code to normalize the array
   ```

3. How would you compute the dot product of two 1D arrays?

4. Write code to reshape a 1D array of 12 elements into a 3D array with shape (2, 2, 3).

5. How would you find the indices of the 3 largest values in an array?
   ```python
   arr = np.array([5, 12, 3, 19, 7, 15, 8, 9])
   # Write code to find indices of 3 largest values
   ```

## Answer Key

### Basic Level
1. `[2 3 4]`
2. `np.zeros((3, 3))`
3. `np.sum(np.array([5, 10, 15, 20]))` or `np.array([5, 10, 15, 20]).sum()`
4. They are the same. Both create a 1D array with 3 zeros.
5. `array.shape`

### Intermediate Level
1. `np.arange(10, 31, 5)` or `np.array([10, 15, 20, 25, 30])`
2. `a[1, 1]`
3. `np.mean(arr, axis=0)`
4. `np.eye(3)` or `np.identity(3)`
5. `arr[arr > 5]`

### Advanced Level
1. `np.intersect1d(arr1, arr2)`
2. `(arr - arr.mean()) / arr.std()`
3. `np.dot(array1, array2)` or `array1 @ array2`
4. `arr.reshape(2, 2, 3)`
5. `np.argsort(arr)[-3:]`