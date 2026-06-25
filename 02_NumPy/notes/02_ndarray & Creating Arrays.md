# ndarray & Creating Arrays

## What is an ndarray?

An **ndarray (N-dimensional array)** is NumPy's core data structure.

Unlike Python lists, an `ndarray`:

- Stores elements of the **same data type (`dtype`)**
- Uses **contiguous memory** for efficient storage
- Supports **fast mathematical and matrix operations**

> **Think of an ndarray as a high-performance container designed for numerical computing.**

---

## Array Dimensions

An ndarray can have one or more dimensions.

| Dimension | Name | Example | Shape |
|:---------:|------|---------|:-----:|
| 0D | Scalar | `np.array(5)` | `()` |
| 1D | Vector | `np.array([1,2,3])` | `(3,)` |
| 2D | Matrix | `np.array([[1,2],[3,4]])` | `(2,2)` |
| 3D | Tensor | `np.array([[[1],[2]],[[3],[4]]])` | `(2,2,1)` |

### Visualization

```text
0D (Scalar)

5


1D (Vector)

[1 2 3]


2D (Matrix)

1 2
3 4


3D (Tensor)

Layer 1        Layer 2

1 2            5 6
3 4            7 8
```

---

# Creating Arrays

NumPy provides several functions to create arrays for different use cases.

---

## 1. From a Python List

Convert an existing list into an ndarray.

```python
import numpy as np

arr = np.array([1, 2, 3])
```

**Result**

```text
array([1, 2, 3])
```

---

## 2. Zeros

Creates an array filled with zeros.

```python
np.zeros((2,3))
```

**Result**

```text
array([[0., 0., 0.],
       [0., 0., 0.]])
```

**Common Use**

- Weight initialization
- Empty matrices
- Placeholder arrays

---

## 3. Ones

Creates an array filled with ones.

```python
np.ones((2,3))
```

**Result**

```text
array([[1., 1., 1.],
       [1., 1., 1.]])
```

---

## 4. Full

Creates an array filled with a specified value.

```python
np.full((2,3), 7)
```

**Result**

```text
array([[7, 7, 7],
       [7, 7, 7]])
```

---

## 5. Identity Matrix

Creates a square identity matrix.

```python
np.eye(3)
```

**Result**

```text
array([[1., 0., 0.],
       [0., 1., 0.],
       [0., 0., 1.]])
```

Used extensively in **Linear Algebra**.

---

## 6. Range of Values

Creates equally spaced values using a fixed step.

```python
np.arange(0, 10, 2)
```

**Result**

```text
array([0, 2, 4, 6, 8])
```

Syntax

```python
np.arange(start, stop, step)
```

---

## 7. Evenly Spaced Values

Creates a fixed number of equally spaced values.

```python
np.linspace(0, 1, 5)
```

**Result**

```text
array([0.  , 0.25, 0.5 , 0.75, 1.  ])
```

Syntax

```python
np.linspace(start, stop, number_of_values)
```

---

## 8. Random Values

Creates an array with random values between 0 and 1.

```python
np.random.rand(2,3)
```

**Example Result**

```text
array([[0.54, 0.91, 0.18],
       [0.72, 0.33, 0.60]])
```

Used in:

- Machine Learning
- Simulations
- Weight Initialization

---

# Comparison of Array Creation Functions

| Function | Description | Example |
|-----------|-------------|---------|
| `array()` | Create an array from existing data | `np.array([1,2,3])` |
| `zeros()` | Fill with zeros | `np.zeros((2,3))` |
| `ones()` | Fill with ones | `np.ones((2,3))` |
| `full()` | Fill with a constant value | `np.full((2,3),7)` |
| `eye()` | Identity matrix | `np.eye(3)` |
| `arange()` | Fixed step values | `np.arange(0,10,2)` |
| `linspace()` | Fixed number of values | `np.linspace(0,1,5)` |
| `random.rand()` | Random numbers | `np.random.rand(2,3)` |

---

# Key Takeaways

- `ndarray` is NumPy's fundamental data structure.
- It stores homogeneous data in contiguous memory.
- Arrays can be 0D, 1D, 2D, 3D, or higher.
- NumPy provides specialized functions to create arrays efficiently.
- Choosing the appropriate array creation function simplifies implementation and improves code readability.
