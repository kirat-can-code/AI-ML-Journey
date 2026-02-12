NumPy Complete Practical Lesson (Keith Galli NumPy Tutorial, notes)
Lesson 0 — What is NumPy & Why It Exists
What NumPy is

NumPy is a multi-dimensional array library for Python.

It lets you work with:

1D arrays (vectors)

2D arrays (matrices)

3D+ arrays (tensors)

It is the foundation of:

Pandas

SciPy

Matplotlib

Machine Learning libraries

Why NumPy instead of Python lists?
1️⃣ Speed

Python lists store objects → slow

NumPy stores raw values → fast

2️⃣ Fixed data types

NumPy arrays contain one data type

No type checking during iteration

3️⃣ Contiguous memory

NumPy stores data next to each other

Enables:

SIMD (Single Instruction Multiple Data)

CPU cache efficiency

📌 Mental model

NumPy arrays are like tightly packed boxes.
Python lists are scattered boxes with labels.

🧪 Practice 0

Answer mentally:

Why is NumPy faster than lists?

Why is contiguous memory important?

Lesson 1 — Installing & Importing NumPy
pip install numpy

import numpy as np

Lesson 2 — Creating NumPy Arrays
2.1 One-Dimensional Array
a = np.array([1, 2, 3])
print(a)

2.2 Two-Dimensional Array
b = np.array([
    [1.5, 2.5, 3.5],
    [4.5, 5.5, 6.5]
])
print(b)


📌 Nest lists → higher dimensions

🧪 Practice 2

Create:

A 1D array with values [10, 20, 30]

A 2D array (3×2) of floats

Lesson 3 — Array Properties
a.ndim      # number of dimensions
a.shape     # shape
a.dtype     # data type
a.size      # number of elements
a.itemsize  # bytes per element
a.nbytes    # total bytes

Example
a = np.array([1, 2, 3], dtype=np.int16)

🧪 Practice 3

Create an array with int8

Check how memory usage changes

Lesson 4 — Indexing & Slicing
4.1 Basic Indexing
arr[row, column]

a = np.array([
    [1, 2, 3, 4, 5, 6, 7],
    [8, 9,10,11,12,13,14]
])

a[1, 5]   # → 13

4.2 Row & Column Access
a[0, :]   # first row
a[:, 2]   # third column

4.3 Slicing with Steps
a[0, 1:6:2]  # 2, 4, 6

🧪 Practice 4

From the matrix above:

Extract [9, 10, 11]

Extract every second element from first row

Lesson 5 — Modifying Values
a[1, 5] = 20

Replace entire column
a[:, 2] = 5

Replace with sequence
a[:, 2] = [1, 2]

🧪 Practice 5

Replace one column with zeros

Replace one row with [9,9,9,9,9,9,9]

Lesson 6 — 3D Arrays (Think “Outside → Inside”)
b = np.array([
    [[1,2],[3,4]],
    [[5,6],[7,8]]
])


Access value 4:

b[0, 1, 1]

🧪 Practice 6

Extract [3,4,7,8]

Replace them with [9,9,8,8]

Lesson 7 — Creating Special Arrays
np.zeros((3,3))
np.ones((2,3))
np.full((2,2), 99)
np.eye(3)

Random
np.random.rand(3,2)
np.random.randint(0, 10, size=(3,3))

🧪 Practice 7

Create a 4×4 matrix of 7s

Create random integers between 10–50

Lesson 8 — Copy vs Reference ⚠️ (Very Important)

❌ Wrong:

b = a


✅ Correct:

b = a.copy()

🧪 Practice 8

Prove to yourself that .copy() works

Lesson 9 — Element-Wise Math
a + 2
a * 2
a ** 2
np.sin(a)


Array + Array:

a + b

🧪 Practice 9

Square all elements

Compute sine of an array

Lesson 10 — Linear Algebra
Matrix multiplication
np.matmul(a, b)

Determinant
np.linalg.det(matrix)

Inverse
np.linalg.inv(matrix)

🧪 Practice 10

Multiply two compatible matrices

Find determinant of identity matrix

Lesson 11 — Statistics
np.min(arr)
np.max(arr)
np.sum(arr)


Axis:

np.sum(arr, axis=0)  # columns
np.sum(arr, axis=1)  # rows

🧪 Practice 11

Find row-wise max

Find column-wise sum

Lesson 12 — Reshaping & Stacking
arr.reshape((4,2))
np.vstack([a, b])
np.hstack([a, b])

🧪 Practice 12

Reshape a 1D array into 2D

Stack two matrices vertically

Lesson 13 — Loading Data from Files
data = np.genfromtxt("data.txt", delimiter=",")
data = data.astype(np.int32)

Lesson 14 — Boolean Masking (Power Feature)
data[data > 50]


Multiple conditions:

data[(data > 50) & (data < 100)]

🧪 Practice 14

Extract values > 30

Extract values between 10 and 20

Lesson 15 — Advanced Indexing
a[[0,1,2], [2,3,4]]


Mix slicing + lists:

a[[0,4,5], 3:]
