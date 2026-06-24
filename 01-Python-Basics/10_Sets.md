# Chapter 10: Sets – Managing Unique Data

## Learning Objectives

After completing this chapter, you should be able to:

* Explain why Sets are needed.
* Define a Set and its characteristics.
* Create and manipulate Sets.
* Understand uniqueness and duplicate removal.
* Perform Set Operations.
* Apply Sets in Healthcare, IIoT, Machine Learning, and Data Analytics.

---

# 10.1 Introduction

So far, we have studied:

```text
Variables
      ↓
Store One Value

Lists
      ↓
Store Multiple Values

Dictionaries
      ↓
Store Structured Information

Tuples
      ↓
Store Fixed Information
```

Each data structure solved a specific problem.

However, another challenge appears in real systems.

Suppose a hospital records patient IDs.

```python
patient_ids = [
    101,
    102,
    103,
    101,
    102
]
```

Question:

```text
How many unique patients exist?
```

Answer:

```text
101
102
103
```

Only three.

The duplicates should not be counted.

Lists allow duplicates.

Tuples allow duplicates.

We need a structure that automatically stores only unique values.

This requirement led to:

# Sets

---

# 10.2 Why Lists and Tuples Were Not Enough

Consider:

```python
symptoms = [
    "Fever",
    "Cough",
    "Fever",
    "Cold",
    "Cough"
]
```

Output:

```text
Fever
Cough
Fever
Cold
Cough
```

Problems:

```text
Duplicate Data

Extra Storage

Incorrect Counting

Difficult Validation
```

Many applications require uniqueness.

Examples:

```text
Patient IDs

Employee IDs

Machine IDs

Email Addresses

Unique Words

Sensor IDs
```

Engineers needed a structure that automatically prevents duplicates.

---

# 10.3 Definition of a Set

A **Set** is an unordered collection of unique elements.

### Simple Definition

> A Set stores only distinct values.

Example:

```python
numbers = {
    1,
    2,
    3
}
```

---

# 10.4 Key Characteristics of Sets

### Unique Elements

```python
numbers = {
    1,
    2,
    2,
    3,
    3
}
```

Python stores:

```text
{1, 2, 3}
```

Duplicates are removed automatically.

---

### Unordered

Lists:

```python
[1, 2, 3]
```

Maintain order.

Sets:

```python
{1, 2, 3}
```

Do not guarantee order.

---

### Mutable

Sets can be modified.

```python
numbers.add(4)
```

Allowed.

---

# 10.5 Creating Sets

### Integer Set

```python
patient_ids = {
    101,
    102,
    103
}
```

---

### String Set

```python
symptoms = {
    "Fever",
    "Cough",
    "Cold"
}
```

---

### Mixed Set

```python
data = {
    "Patient",
    101,
    True
}
```

---

# 10.6 Visualizing a Set

```python
patient_ids = {
    101,
    102,
    103
}
```

Representation:

```text
      101

 102       103
```

Notice:

```text
No Index

No Position

Only Unique Values
```

---

# 10.7 Creating a Set from a List

Suppose duplicate records exist.

```python
patient_ids = [
    101,
    102,
    103,
    101,
    102
]
```

Convert:

```python
unique_patients = set(patient_ids)

print(unique_patients)
```

Output:

```text
{101, 102, 103}
```

One of the most common real-world uses of Sets.

---

# 10.8 Adding Elements

```python
patient_ids = {
    101,
    102
}
```

Add:

```python
patient_ids.add(103)
```

Result:

```text
{101, 102, 103}
```

---

# 10.9 Removing Elements

```python
patient_ids.remove(102)
```

Result:

```text
{101, 103}
```

---

# 10.10 Membership Testing

One major advantage of Sets is fast searching.

```python
patient_ids = {
    101,
    102,
    103
}
```

Check:

```python
print(101 in patient_ids)
```

Output:

```text
True
```

Check:

```python
print(999 in patient_ids)
```

Output:

```text
False
```

---

# 10.11 Set Operations

One of the strongest features of Sets.

---

## Union

Combines two Sets.

```python
ward_A = {
    101,
    102
}

ward_B = {
    103,
    104
}
```

```python
print(ward_A | ward_B)
```

Output:

```text
{101, 102, 103, 104}
```

Visualization:

```text
Ward A     Ward B

101        103
102        104

      ↓

All Patients
```

---

## Intersection

Common elements.

```python
A = {
    101,
    102,
    103
}

B = {
    103,
    104
}
```

```python
print(A & B)
```

Output:

```text
{103}
```

Meaning:

```text
Present In Both Sets
```

---

## Difference

Elements present in one Set but not another.

```python
print(A - B)
```

Output:

```text
{101, 102}
```

---

# 10.12 Sets and Loops

```python
symptoms = {
    "Fever",
    "Cold",
    "Cough"
}
```

```python
for symptom in symptoms:

    print(symptom)
```

Output:

```text
Fever
Cold
Cough
```

Order may vary.

---

# 10.13 Sets and Functions

```python
def count_unique(items):

    return len(set(items))
```

Example:

```python
patient_ids = [
    101,
    102,
    101,
    103
]

print(count_unique(patient_ids))
```

Output:

```text
3
```

---

# 10.14 Applications of Sets

## Smart Healthcare

```python
patient_ids = {
    101,
    102,
    103
}
```

Applications:

* Unique Patient Records
* Disease Tracking
* Hospital Analytics

---

## Industrial IoT (IIoT)

```python
sensor_ids = {
    "S1",
    "S2",
    "S3"
}
```

Applications:

* Sensor Registration
* Device Authentication
* Network Management

---

## Machine Learning

```python
labels = {
    "Dog",
    "Cat",
    "Bird"
}
```

Applications:

* Unique Classes
* Feature Selection
* Dataset Analysis

---

## Large Language Models

```python
unique_words = {
    "AI",
    "Machine",
    "Learning"
}
```

Applications:

* Vocabulary Analysis
* Token Processing
* Duplicate Removal

---

# 10.15 When to Use Which Data Structure

```text
Need Ordered Collection?
        ↓
      List

Need Structured Record?
        ↓
   Dictionary

Need Fixed Data?
        ↓
      Tuple

Need Unique Data?
        ↓
       Set
```

---

# 10.16 Best Practices

### Use Sets for Uniqueness

Good:

```python
unique_ids = {
    101,
    102,
    103
}
```

Bad:

```python
ids = [
    101,
    102,
    103,
    101
]
```

when duplicates are not desired.

---

### Use Membership Testing

```python
if sensor_id in sensors:
```

Sets are optimized for this operation.

---

### Convert Lists to Sets When Needed

```python
unique_values = set(data)
```

Simple and efficient.

---

# 10.17 Common Errors

### Using Indexes

Wrong:

```python
patient_ids[0]
```

Error.

Sets do not support indexing.

---

### Expecting Order

Wrong assumption:

```text
First Element
Second Element
Third Element
```

Sets are unordered.

---

### Duplicate Storage

```python
{
    1,
    1,
    1
}
```

Python stores:

```text
{1}
```

Only one copy exists.

---

# 10.18 Evolution of Data Structures

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
Store Fixed Data

Sets
      ↓
Store Unique Data
```

Each structure solves a different problem in software design.

---

# 10.19 Summary

```text
Variables     → One Value

Lists         → Many Values

Dictionaries  → Meaningful Records

Tuples        → Fixed Data

Sets          → Unique Data
```

Sets are powerful data structures used whenever uniqueness, membership testing, and duplicate elimination are important.

---

## Key Takeaway

> Lists preserve order. Dictionaries preserve meaning. Tuples preserve stability. Sets preserve uniqueness.

---

## Next Chapter

# Strings

So far we have stored and processed data.

However, a large amount of real-world information exists as text:

```text
Patient Names

Doctor Notes

Emails

Messages

Documents

LLM Prompts
```

Understanding and manipulating text leads to the next topic:

**Strings**.
