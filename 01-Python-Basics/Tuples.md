# Chapter 9: Tuples – Protecting Data That Should Not Change

## Learning Objectives

After completing this chapter, you should be able to:

* Explain why Tuples are needed.
* Define a Tuple and identify its characteristics.
* Create and access Tuples.
* Understand the difference between Lists and Tuples.
* Determine when Tuples should be preferred over Lists.
* Use Tuples in real-world systems.

---

# 9.1 Introduction

So far, we have learned:

```text
Variables
      ↓
Store Individual Values

Lists
      ↓
Store Collections

Dictionaries
      ↓
Store Structured Information
```

Consider our Smart Healthcare System.

A patient record may be stored as:

```python
patient = {
    "name": "Harshita",
    "heart_rate": 110,
    "oxygen": 92
}
```

Patient information changes over time.

Heart rate changes.

Oxygen level changes.

Temperature changes.

Therefore, Lists and Dictionaries are useful because they allow modification.

However, not all information should change.

---

# 9.2 The Problem

Consider:

```text
Days of Week

Months of Year

GPS Coordinates

Machine Serial Numbers

Country Codes

RGB Color Values
```

Should these values change accidentally?

No.

For example:

```python
days = [
    "Monday",
    "Tuesday",
    "Wednesday"
]
```

Someone could write:

```python
days[0] = "Holiday"
```

Result:

```python
['Holiday', 'Tuesday', 'Wednesday']
```

The original information has been modified.

In many systems this is undesirable.

Engineers needed a data structure that could:

```text
Store Related Data

Prevent Accidental Modification

Improve Data Safety
```

This led to:

# Tuples

---

# 9.3 Definition of a Tuple

A **Tuple** is an ordered collection of elements that cannot be modified after creation.

### Simple Definition

> A Tuple is an immutable List.

---

# 9.4 Why Tuples Were Introduced

### Variables

Store one value.

```python
temperature = 38.5
```

---

### Lists

Store many values.

```python
temperatures = [36.5, 37.1, 38.5]
```

Problem:

```text
Can Be Modified
```

---

### Dictionaries

Store structured information.

```python
patient = {
    "name": "Harshita",
    "oxygen": 92
}
```

Problem:

```text
Can Be Modified
```

---

### Tuples

Store data that should remain constant.

```python
days = (
    "Monday",
    "Tuesday",
    "Wednesday"
)
```

Problem solved.

---

# 9.5 Creating Tuples

Syntax:

```python
tuple_name = (value1, value2, value3)
```

Example:

```python
days = (
    "Monday",
    "Tuesday",
    "Wednesday"
)
```

---

### Numeric Tuple

```python
coordinates = (
    23.2599,
    77.4126
)
```

---

### Mixed Tuple

```python
patient = (
    "Harshita",
    24,
    "Female"
)
```

---

# 9.6 Visualizing a Tuple

```python
days = (
    "Monday",
    "Tuesday",
    "Wednesday"
)
```

Representation:

```text
┌─────────┬─────────┬───────────┐
│ Monday  │ Tuesday │ Wednesday │
└─────────┴─────────┴───────────┘
     0         1          2
```

Like Lists:

```text
Ordered
Indexed
```

Unlike Lists:

```text
Cannot Be Modified
```

---

# 9.7 Accessing Tuple Elements

Tuples use indexing just like Lists.

```python
days = (
    "Monday",
    "Tuesday",
    "Wednesday"
)

print(days[0])
```

Output:

```text
Monday
```

---

```python
print(days[1])
```

Output:

```text
Tuesday
```

---

# 9.8 Immutability

The defining characteristic of Tuples is:

```text
Immutability
```

Example:

```python
days = (
    "Monday",
    "Tuesday",
    "Wednesday"
)

days[0] = "Holiday"
```

Output:

```text
TypeError
```

Python prevents modification.

---

# 9.9 Lists vs Tuples

| Feature         | List | Tuple |
| --------------- | ---- | ----- |
| Ordered         | Yes  | Yes   |
| Indexed         | Yes  | Yes   |
| Mutable         | Yes  | No    |
| Add Elements    | Yes  | No    |
| Remove Elements | Yes  | No    |
| Update Elements | Yes  | No    |

---

# 9.10 When Should You Use Tuples?

Use Lists when data changes.

Examples:

```text
Patient Records

Sensor Readings

Student Marks

Inventory Data
```

Use Tuples when data should remain constant.

Examples:

```text
Days of Week

Months

GPS Coordinates

RGB Values

Country Codes

Mathematical Constants
```

---

# 9.11 Tuples and Functions

Functions can return multiple values using Tuples.

Example:

```python
def patient_status():

    return (
        110,
        92
    )
```

Calling:

```python
result = patient_status()

print(result)
```

Output:

```text
(110, 92)
```

---

# 9.12 Tuple Unpacking

A very common Python feature.

```python
coordinates = (
    23.2599,
    77.4126
)
```

Instead of:

```python
latitude = coordinates[0]

longitude = coordinates[1]
```

We can write:

```python
latitude, longitude = coordinates
```

Result:

```text
latitude = 23.2599

longitude = 77.4126
```

This is called:

```text
Tuple Unpacking
```

---

# 9.13 Applications of Tuples

## Smart Healthcare

```python
normal_ranges = (
    60,
    100
)
```

Heart rate range.

Should not change.

---

## Industrial IoT (IIoT)

```python
machine_id = (
    "M101",
    "Plant_A"
)
```

Fixed identification.

---

## GPS Systems

```python
location = (
    23.2599,
    77.4126
)
```

Latitude and Longitude.

---

## Machine Learning

```python
input_shape = (
    224,
    224,
    3
)
```

Image dimensions.

Usually fixed.

---

## Deep Learning

```python
kernel_size = (
    3,
    3
)
```

CNN filter dimensions.

---

# 9.14 Why Professionals Use Tuples

A Tuple communicates:

```text
This Data Should Not Change
```

Benefits:

```text
Improves Safety

Reduces Bugs

Improves Readability

Clearly Expresses Intent
```

When another developer sees a Tuple, they immediately understand:

```text
Modification Is Not Expected
```

---

# 9.15 Common Errors

### Attempting Modification

```python
days[0] = "Holiday"
```

Error.

Tuples are immutable.

---

### Confusing Lists and Tuples

List:

```python
data = [1, 2, 3]
```

Tuple:

```python
data = (1, 2, 3)
```

Notice:

```text
[] → List

() → Tuple
```

---

### Forgetting Comma in Single Element Tuple

Incorrect:

```python
x = (5)
```

Python treats this as:

```python
int
```

Correct:

```python
x = (5,)
```

---

# 9.16 Evolution of Data Structures

```text
Variables
      ↓
Store One Value

Lists
      ↓
Store Collections

Dictionaries
      ↓
Store Structured Records

Tuples
      ↓
Store Fixed Collections
```

Each data structure was introduced to solve a limitation of the previous approach.

---

# 9.17 Summary

```text
Variables
      ↓
One Value

Lists
      ↓
Many Values

Dictionaries
      ↓
Named Values

Tuples
      ↓
Protected Values
```

Tuples provide a safe way to store data that should remain unchanged throughout program execution.

---

## Key Takeaway

> Lists store data that may change. Tuples store data that should remain constant.

---

## Next Chapter

# Sets

Lists allow duplicates.

Tuples allow duplicates.

What if we need a collection that stores only unique values?

This leads to **Sets**.
