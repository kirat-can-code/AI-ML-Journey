NumPy Complete Practical Lesson

(Keith Galli NumPy Tutorial — Structured Notes)

🟦 Day 1 — NumPy Foundations & Core Array Operations

Goal: Build a strong mental model of NumPy arrays, indexing, memory, and performance.

Lesson 0 — What is NumPy & Why It Exists

NumPy is a multi-dimensional array library for Python.

It allows efficient work with:

1D arrays → Vectors

2D arrays → Matrices

3D+ arrays → Tensors

NumPy is the foundation of:

Pandas

SciPy

Matplotlib

Machine Learning libraries

Why NumPy instead of Python lists?
1️⃣ Speed

Python lists store objects → slower

NumPy stores raw values → faster

2️⃣ Fixed Data Types

One data type per array

No runtime type checking

3️⃣ Contiguous Memory

Data stored next to each other in memory

Enables:

SIMD (Single Instruction, Multiple Data)

CPU cache efficiency

📌 Mental Model

NumPy arrays = tightly packed boxes
Python lists = scattered boxes with labels

🧪 Practice 0

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


📌 Nested lists → higher dimensions

🧪 Practice 2

Create a 1D array: [10, 20, 30]

Create a 3×2 float array

Lesson 3 — Array Properties
a.ndim       # number of dimensions
a.shape      # shape
a.dtype      # data type
a.size       # number of elements
a.itemsize   # bytes per element
a.nbytes     # total memory used

a = np.array([1, 2, 3], dtype=np.int16)


🧪 Practice 3

Create an int8 array

Observe memory usage differences

Lesson 4 — Indexing & Slicing (Basics)
a = np.array([
    [1, 2, 3, 4, 5, 6, 7],
    [8, 9,10,11,12,13,14]
])

Basic Indexing
a[1, 5]   # → 13

Row & Column Access
a[0, :]   # first row
a[:, 2]   # third column

Slicing with Steps
a[0, 1:6:2]   # → [2, 4, 6]


🧪 Practice 4

Extract [9, 10, 11]

Extract every second element from first row

Lesson 15 — Advanced Indexing 🚀

Advanced indexing allows selecting arbitrary elements using index arrays.
It does not behave like simple slicing.

15.1 Indexing with Index Arrays
a[[0, 1, 2], [2, 3, 4]]


📌 Meaning:

Select:

Row 0 → Column 2

Row 1 → Column 3

Row 2 → Column 4

✅ Output is a 1D array of matched pairs
❌ Not a submatrix

15.2 Mixing Index Lists + Slicing
a[[0, 4, 5], 3:]


📌 Meaning:

Pick rows: 0, 4, 5

Pick columns: from index 3 to the end

✅ Output is a new 2D array

🔑 Key Difference
Feature	Basic Slicing	Advanced Indexing
Uses	: ranges	Lists / arrays
Output	View (often)	Copy (always)
Shape	Predictable	Can change
Power	Medium	🔥 Very High

🧪 Practice 15

Select diagonal elements using index arrays

Extract non-contiguous rows & columns

✅ Day 1 Coverage Summary

✔ NumPy fundamentals
✔ Memory model & performance
✔ Array creation & properties
✔ Indexing, slicing, and modification
✔ Boolean masking
✔ Advanced indexing (core NumPy superpower)
