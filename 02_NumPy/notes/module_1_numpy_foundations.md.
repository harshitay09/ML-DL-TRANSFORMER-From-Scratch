# NUMPY FOR MACHINE LEARNING, DEEP LEARNING & LLMS

## Module 1 — Foundations

---

# How to Read This Notebook

For every topic ask:

```text
WHY?
↓
INTUITION
↓
VISUALIZATION
↓
NUMPY CODE
↓
ML APPLICATION
↓
INTERVIEW QUESTION
```

Do not memorize NumPy.

Understand why the concept exists.

---

# 1. WHY NUMPY EXISTS

## The Problem

Suppose we want to store one million numbers.

Python:

```python
numbers = [1,2,3,4,5]
```

Looks simple.

Internally Python stores:

```text
Object Metadata
+
Type Information
+
Reference Address
+
Actual Value
```

for EVERY element.

Memory becomes expensive.

---

## Visualization

Python List

```text
┌─────┐      ┌─────┐
│ ptr │ ───► │  5  │
└─────┘      └─────┘

┌─────┐      ┌─────┐
│ ptr │ ───► │  7  │
└─────┘      └─────┘

┌─────┐      ┌─────┐
│ ptr │ ───► │  2  │
└─────┘      └─────┘
```

Data scattered in memory.

---

NumPy Array

```text
┌───┬───┬───┬───┐
│ 5 │ 7 │ 2 │ 9 │
└───┴───┴───┴───┘
```

Data stored continuously.

---

## Why Faster?

```text
Contiguous Memory
+
Vectorization
+
C Backend
+
CPU Cache Friendly
```

---

## ML Connection

Everything becomes numbers.

```text
Dataset
Image
Audio
Embeddings
Weights
Activations
```

Everything eventually becomes:

```python
numpy.ndarray
```

---

# 2. NDARRAY

## Definition

ndarray = N-Dimensional Array

---

## Visualization

### 1D

```python
a = np.array([1,2,3])
```

```text
1 ─── 2 ─── 3
```

---

### 2D

```python
A = np.array([
 [1,2,3],
 [4,5,6]
])
```

```text
┌───┬───┬───┐
│ 1 │ 2 │ 3 │
├───┼───┼───┤
│ 4 │ 5 │ 6 │
└───┴───┴───┘
```

---

### 3D

```python
T = np.zeros((3,2,2))
```

```text
Layer 1

┌───┬───┐
│ 0 │ 0 │
├───┼───┤
│ 0 │ 0 │
└───┴───┘

Layer 2

┌───┬───┐
│ 0 │ 0 │
├───┼───┤
│ 0 │ 0 │
└───┴───┘

Layer 3

┌───┬───┐
│ 0 │ 0 │
├───┼───┤
│ 0 │ 0 │
└───┴───┘
```

Think:

```text
3D = Stack of Matrices
```

---

# 3. SHAPE

## Why?

Shape tells us how data is organized.

Without shape:

```text
1 2 3 4 5 6
```

Computer doesn't know:

```text
Vector?
Matrix?
Image?
Dataset?
```

---

## Example

```python
A = np.array([
 [10,20,30],
 [40,50,60]
])
```

Shape:

```python
A.shape
```

Output:

```python
(2,3)
```

---

## Visualization

```text
          FEATURES
      ┌────┬────┬────┐
      │ 10 │ 20 │ 30 │
      ├────┼────┼────┤
      │ 40 │ 50 │ 60 │
      └────┴────┴────┘
        SAMPLES
```

Meaning:

```text
2 Samples

3 Features
```

---

## ML Interpretation

```python
X.shape
```

```python
(1000,20)
```

Means:

```text
1000 Training Examples

20 Features Each
```

---

# 4. DIMENSIONS (ndim)

## Definition

Number of axes required to describe data.

---

## 1D

```python
a = np.array([1,2,3])
```

```text
1 ── 2 ── 3
```

Dimensions:

```python
1
```

---

## 2D

```python
A = np.array([
 [1,2],
 [3,4]
])
```

```text
Rows ↓

1 2
3 4

    → Columns
```

Dimensions:

```python
2
```

---

## 3D

```python
(Depth, Rows, Columns)
```

Example:

```python
(32,28,28)
```

Meaning:

```text
32 matrices

Each matrix is 28 × 28
```

---

## ML Examples

```text
1D → Feature Vector

2D → Dataset Matrix

3D → RGB Image

4D → Batch of Images

5D → Video Data
```

---

# 5. AXIS

## Most Important NumPy Concept

Many people memorize:

```python
axis=0
axis=1
```

Never memorize.

Visualize.

---

Array:

```python
A = np.array([
 [1,2,3],
 [4,5,6]
])
```

```text
            Axis=1 →
        ┌───┬───┬───┐
Axis=0  │ 1 │ 2 │ 3 │
   ↓    ├───┼───┼───┤
        │ 4 │ 5 │ 6 │
        └───┴───┴───┘
```

---

## axis=0

Move vertically.

```python
A.sum(axis=0)
```

```text
1
│
▼
4
=
5

2
│
▼
5
=
7

3
│
▼
6
=
9
```

Output:

```python
[5 7 9]
```

---

## axis=1

Move horizontally.

```python
A.sum(axis=1)
```

```text
1 → 2 → 3 = 6

4 → 5 → 6 = 15
```

Output:

```python
[ 6 15 ]
```

---

## ML Application

Feature Mean:

```python
X.mean(axis=0)
```

Sample Mean:

```python
X.mean(axis=1)
```

---

# 6. DATA TYPES (dtype)

## Why?

Memory matters.

---

## Example

```python
a = np.array([1,2,3])

a.dtype
```

Output:

```python
int64
```

---

## Common Types

```text
int32
int64

float32
float64

bool
```

---

## ML Rule

Most deep learning uses:

```python
float32
```

because GPUs are optimized for it.

---

# 7. ARRAY CREATION

## zeros()

```python
np.zeros((3,3))
```

```text
0 0 0
0 0 0
0 0 0
```

---

## ones()

```python
np.ones((3,3))
```

```text
1 1 1
1 1 1
1 1 1
```

---

## eye()

Identity Matrix

```python
np.eye(3)
```

```text
1 0 0
0 1 0
0 0 1
```

Used in Linear Algebra.

---

## arange()

```python
np.arange(0,10,2)
```

```text
0 2 4 6 8
```

---

## linspace()

```python
np.linspace(0,1,5)
```

```text
0.00 0.25 0.50 0.75 1.00
```

---

# 8. SIZE

## Definition

Total number of elements.

Example:

```python
A.shape
```

```python
(2,3)
```

Visualization:

```text
┌───┬───┬───┐
│ • │ • │ • │
├───┼───┼───┤
│ • │ • │ • │
└───┴───┴───┘
```

Count:

```text
6 Elements
```

Output:

```python
A.size
```

```python
6
```

---

# 9. RESHAPE

## Core Idea

Same data.

Different interpretation.

---

Original

```python
a = np.arange(12)
```

```text
0 1 2 3 4 5 6 7 8 9 10 11
```

Memory:

```text
┌─┬─┬─┬─┬─┬─┬─┬─┬─┬─┬──┬──┐
│0│1│2│3│4│5│6│7│8│9│10│11│
└─┴─┴─┴─┴─┴─┴─┴─┴─┴─┴──┴──┘
```

---

Reshape

```python
a.reshape(3,4)
```

```text
┌──┬──┬──┬──┐
│0 │1 │2 │3 │
├──┼──┼──┼──┤
│4 │5 │6 │7 │
├──┼──┼──┼──┤
│8 │9 │10│11│
└──┴──┴──┴──┘
```

Data unchanged.

Only structure changed.

---

## ML Example

Image:

```text
28 × 28
```

Flatten:

```text
784 Features
```

for Neural Networks.

---

# 10. FLATTEN vs RAVEL

## flatten()

```python
b = A.flatten()
```

```text
Creates NEW Memory
```

Visualization:

```text
A ─────────► New Copy
```

---

## ravel()

```python
b = A.ravel()
```

```text
Uses Existing Memory
```

Visualization:

```text
A
│
└────► Same Memory
```

---

# FINAL ML VISUALIZATION

Dataset

```python
X.shape = (1000,20)
```

```text
1000 Samples

20 Features
```

Weights

```python
W.shape = (20,5)
```

```text
20 Inputs

5 Neurons
```

Matrix Multiplication

```python
X @ W
```

```text
(1000,20)
      @
(20,5)

      =
(1000,5)
```

This single shape calculation powers:

```text
Linear Regression
Logistic Regression
Neural Networks
Transformers
LLMs
```

---

# MODULE 1 REVISION BOX

```text
ndarray
=
N-Dimensional Array

shape
=
Data Organization

ndim
=
Number of Dimensions

axis
=
Direction of Operation

dtype
=
Data Type

size
=
Total Elements

reshape
=
Change Interpretation

flatten
=
Copy

ravel
=
View

Golden Formula

y = X @ W + b
```

