# Data-science-libraries
<hr>
# Comprehensive NumPy Notes: Beginner to Advanced

## Introduction to NumPy

**NumPy** (Numerical Python) is a powerful library for numerical and scientific computing in Python. It enables efficient operations on large multi-dimensional arrays and matrices, as well as a wide range of mathematical functions.

## 1. Getting Started

### Installation

```bash
pip install numpy
```

### Importing NumPy

```python
import numpy as np
```

## 2. Arrays in NumPy

### Array Creation

- **1D Array:**  
  ```python
  arr = np.array([1, 2, 3, 4])
  ```
- **2D Array (Matrix):**  
  ```python
  mat = np.array([[1, 2], [3, 4]])
  ```

### Array Initialization Methods

| Function         | Description                       | Example                               |
|------------------|-----------------------------------|---------------------------------------|
| np.zeros((r, c)) | Array of all zeros                | `np.zeros((2,3))`                     |
| np.ones((r, c))  | Array of all ones                 | `np.ones((3,2))`                      |
| np.eye(n)        | Identity matrix                   | `np.eye(3)`                           |
| np.arange(s,e,s) | Sequence of numbers               | `np.arange(0,10,2)`                   |
| np.linspace(a,b,n)| n evenly spaced values from a-b  | `np.linspace(0,1,5)`                  |

## 3. Array Properties & Data Types

- **Shape:**  
  ```python
  arr.shape
  ```
- **Dimensions:**  
  ```python
  arr.ndim
  ```
- **Data type (dtype):**  
  ```python
  arr.dtype
  ```
- **Changing data type:**  
  ```python
  arr = np.array([1, 2, 3], dtype=np.float32)
  ```

## 4. Indexing, Slicing, and Iteration

### Indexing

```python
arr = np.array([10, 20, 30])
print(arr[1])  # 20
```

### Slicing

```python
print(arr[0:2])  # [10 20]
```

### Multidimensional Indexing

```python
mat = np.array([[1,2,3],[4,5,6]])
print(mat[1,2])      # 6 (row 1, column 2)
print(mat[:,0])      # [1 4]
```

## 5. Array Manipulation

### Reshaping

```python
a = np.arange(6)         # [0 1 2 3 4 5]
b = a.reshape((2, 3))    # [[0 1 2], [3 4 5]]
```

### Stacking

```python
x = np.array([1, 2])
y = np.array([3, 4])
np.vstack((x, y))        # Vertical stack
np.hstack((x, y))        # Horizontal stack
```

### Splitting

```python
arr = np.arange(8)
np.split(arr, 4)  # Split into 4 equal arrays
```

## 6. Arithmetic and Mathematical Operations

### Element-wise Operations

```python
a = np.array([1,2,3])
b = np.array([4,5,6])
print(a + b)        # [5 7 9]
print(a * b)        # [4 10 18]
```

### Universal Functions

```python
np.sqrt(a)          # [1. 1.414 1.732]
np.exp(a)           # [2.718 7.389 20.086]
np.sin(a)           # Applies sine element-wise
```

## 7. Aggregation Functions

```python
mat = np.array([[1,2,3],[4,5,6]])
print(mat.sum())             # 21
print(mat.mean(axis=0))      # [2.5 3.5 4.5] (column-wise mean)
print(mat.max(axis=1))       # [3 6]   (row-wise max)
```

## 8. Advanced Array Operations

### Broadcasting

- Allows operations on arrays of different shapes:
  ```python
  arr = np.array([1,2,3])
  print(arr + 5)     # [6 7 8]
  ```

### Boolean Indexing & Filtering

```python
data = np.array([10, 20, 30, 40])
mask = data > 20
filtered = data[mask]         # [30 40]
```

## 9. Linear Algebra

NumPy provides comprehensive linear algebra functions.

```python
A = np.array([[1,2], [3,4]])
B = np.array([[2,0], [1,2]])
print(np.dot(A, B))            # Matrix multiplication
print(np.linalg.inv(A))        # Matrix inverse
print(np.linalg.eig(A))        # Eigenvalues & eigenvectors
```

## 10. Random Module

- Generate random numbers:

```python
np.random.rand(3,2)            # 3x2 array of random floats in [0,1)
np.random.randint(0, 10, (2,3))# 2x3 array of random integers from 0 to 9
np.random.seed(42)             # For reproducibility
```

## 11. Useful Array Functions

- `np.unique(arr)`: Unique elements
- `np.sort(arr)`: Sort elements
- `np.where(arr > 3)`: Index positions where condition holds
- `np.argsort(arr)`: Indices for sorted array

## 12. Missing Data Handling

- Use `np.nan` for missing values:
  ```python
  arr = np.array([1, 2, np.nan, 4])
  print(np.isnan(arr))         # Boolean mask for nan
  ```

## 13. Saving and Loading Arrays

```python
np.save('my_array.npy', arr)
loaded_arr = np.load('my_array.npy')
```

## 14. Practical Example: Data Processing

### Example 1: Matrix Normalization

```python
data = np.random.randint(1, 100, (5,3))
mean = data.mean(axis=0)
std = data.std(axis=0)
normalized = (data - mean) / std
print(normalized)
```

### Example 2: Outlier Removal

```python
arr = np.array([10, 20, 30, 1000])
filtered = arr[arr = 100
```

### Example 3: Conditional Replacement

```python
arr = np.array([1, 2, 3, 4, 5])
arr[arr > 3] = 0
print(arr)  # [1 2 3 0 0]
```

## 15. Applications of NumPy

- **Data Science & Analysis:** Efficient manipulation of large datasets
- **Machine Learning:** Fast operations for tensors, feature engineering, and pre-processing
- **Scientific Simulation:** Physical modeling, simulations, computational statistics

## 16. Best Practices

- Prefer array operations over loops for efficiency.
- Use boolean masking for filtering.
- Always set `np.random.seed()` when reproducibility is needed.
