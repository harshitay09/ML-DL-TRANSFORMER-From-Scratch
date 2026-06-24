# Chapter 7: Lists – Managing Collections of Data

## Learning Objectives

After completing this chapter, you should be able to:

* Explain why Lists are needed.
* Create and access Lists.
* Understand indexing.
* Add, update, and remove elements.
* Use Lists with Loops, Conditions, and Functions.
* Process multiple Lists together.
* Build simple real-world systems using Lists.

---

# 7.1 Introduction

In previous chapters, we learned:

```text
Variables   → Store Data

Data Types  → Represent Information

Operators   → Perform Computations

Conditions  → Make Decisions

Loops       → Repeat Tasks

Functions   → Reuse Solutions
```

Let us continue building our Smart Healthcare Assistant.

The system should:

```text
✓ Store Patient Information

✓ Monitor Health Measurements

✓ Detect Possible Issues

✓ Recommend Appointments
```

---

# 7.2 The Problem

Suppose the system manages only one patient.

```python
patient_name = "Harshita"

heart_rate = 110

oxygen_level = 92

temperature = 38.5
```

This approach works.

However, hospitals rarely manage one patient.

Consider:

```text
100 Patients

1000 Patients

10000 Patients
```

Using variables:

```python
patient1_name = "Harshita"

patient2_name = "Aman"

patient3_name = "Riya"
```

quickly becomes difficult to manage.

Variables are designed to store a single value.

Real-world systems often require storing many related values together.

This requirement leads to:

# Lists

---

# 7.3 Definition of a List

A **List** is an ordered and mutable collection of elements stored inside a single variable.

### Simple Definition

> A List stores multiple values inside one variable.

Example:

```python
patient_names = [
    "Harshita",
    "Aman",
    "Riya"
]
```

One variable.

Multiple values.

---

# 7.4 Visualizing a List

```python
patient_names = [
    "Harshita",
    "Aman",
    "Riya"
]
```

Representation:

```text
┌──────────┬────────┬────────┐
│ Harshita │ Aman   │ Riya   │
└──────────┴────────┴────────┘
      0         1        2
```

Each position is called an:

```text
Index
```

---

# 7.5 Indexing

Python uses **Zero-Based Indexing**.

```text
Index:       0         1        2

Value:   Harshita    Aman     Riya
```

Accessing elements:

```python
print(patient_names[0])
```

Output:

```text
Harshita
```

Accessing the second element:

```python
print(patient_names[1])
```

Output:

```text
Aman
```

---

# 7.6 Lists and Data Types

Lists can store different data types.

### String List

```python
patient_names = [
    "Harshita",
    "Aman",
    "Riya"
]
```

### Integer List

```python
heart_rates = [
    110,
    75,
    130
]
```

### Float List

```python
temperatures = [
    38.5,
    36.8,
    39.1
]
```

### Boolean List

```python
critical_status = [
    True,
    False,
    True
]
```

### Mixed List

```python
patient = [
    "Harshita",
    24,
    True
]
```

---

# 7.7 Why Lists Matter

Consider a hospital database.

Without Lists:

```python
patient1 = "Harshita"
patient2 = "Aman"
patient3 = "Riya"
```

With Lists:

```python
patient_names = [
    "Harshita",
    "Aman",
    "Riya"
]
```

Lists make data easier to store, manage, and process.

---

# 7.8 Basic List Operations

## Finding Length

```python
patient_names = [
    "Harshita",
    "Aman",
    "Riya"
]

print(len(patient_names))
```

Output:

```text
3
```

---

## Adding Elements

```python
patient_names.append("Rahul")
```

Before:

```text
[Harshita][Aman][Riya]
```

After:

```text
[Harshita][Aman][Riya][Rahul]
```

---

## Updating Elements

```python
patient_names[0] = "Harshitha"
```

Result:

```python
['Harshitha', 'Aman', 'Riya']
```

---

## Removing Elements

```python
patient_names.remove("Aman")
```

Result:

```python
['Harshitha', 'Riya']
```

---

# 7.9 Lists and Loops

Suppose we want to display all patient names.

Without Loops:

```python
print(patient_names[0])

print(patient_names[1])

print(patient_names[2])
```

Not scalable.

With Loops:

```python
for patient in patient_names:

    print(patient)
```

Output:

```text
Harshita

Aman

Riya
```

### Execution Flow

```text
List
 ↓

Loop
 ↓

Visit Every Element
 ↓

Process Data
```

---

# 7.10 Lists and Conditions

Suppose the hospital wants to identify patients with abnormal heart rates.

```python
heart_rates = [
    110,
    75,
    130
]
```

```python
for rate in heart_rates:

    if rate > 100:

        print("High Risk")
```

Output:

```text
High Risk

High Risk
```

### Processing Model

```text
List
 ↓

Loop
 ↓

Condition
 ↓

Decision
```

---

# 7.11 Lists and Functions

Functions allow us to reuse logic.

```python
def check_risk(rate):

    if rate > 100:
        return "High Risk"

    return "Normal"
```

Using the Function:

```python
for rate in heart_rates:

    print(check_risk(rate))
```

Output:

```text
High Risk

Normal

High Risk
```

### Processing Pipeline

```text
List
 ↓

Loop
 ↓

Function
 ↓

Condition
 ↓

Output
```

---

# 7.12 Multiple Lists Working Together

A hospital stores different information about each patient.

```python
patient_names = [
    "Harshita",
    "Aman",
    "Riya"
]

heart_rates = [
    110,
    75,
    130
]

oxygen_levels = [
    92,
    98,
    88
]
```

Representation:

```text
Index          0         1        2

Name       Harshita    Aman     Riya

Heart Rate   110        75      130

Oxygen        92        98       88
```

All values at the same index belong to the same patient.

Example:

```text
Index 0

Harshita
110
92
```

represents one patient record.

---

# 7.13 Processing Multiple Lists

```python
for i in range(len(patient_names)):

    if heart_rates[i] > 100:

        print(patient_names[i], "High Risk")
```

Output:

```text
Harshita High Risk

Riya High Risk
```

---

# 7.14 Smart Healthcare Case Study

Let us build a simple healthcare recommendation system.

```python
patient_names = [
    "Harshita",
    "Aman",
    "Riya"
]

heart_rates = [
    110,
    75,
    130
]

oxygen_levels = [
    92,
    98,
    88
]
```

Function:

```python
def next_appointment(rate, oxygen):

    if rate > 120 or oxygen < 90:
        return "Visit in 1 Day"

    elif rate > 100 or oxygen < 95:
        return "Visit in 7 Days"

    return "Visit in 30 Days"
```

System:

```python
for i in range(len(patient_names)):

    print(
        patient_names[i],
        "-",
        next_appointment(
            heart_rates[i],
            oxygen_levels[i]
        )
    )
```

Output:

```text
Harshita - Visit in 7 Days

Aman - Visit in 30 Days

Riya - Visit in 1 Day
```

### Complete System Flow

```text
Patient Data
      ↓

Lists
      ↓

Loop
      ↓

Function
      ↓

Condition
      ↓

Diagnosis
      ↓

Appointment Recommendation
```

---

# 7.15 Applications of Lists

## Smart Healthcare

```python
heart_rates = [72, 85, 110, 95]
```

Applications:

* Patient Monitoring
* ICU Systems
* Medical Analytics

---

## Industrial IoT (IIoT)

```python
machine_temps = [65, 70, 90, 75]
```

Applications:

* Sensor Monitoring
* Predictive Maintenance
* Fault Detection

---

## Machine Learning

```python
features = [age, weight, blood_pressure]
```

Applications:

* Feature Storage
* Dataset Processing
* Model Training

---

## Large Language Models

```python
tokens = ["Machine", "Learning", "is", "fun"]
```

Applications:

* Token Processing
* Language Modeling
* Text Generation

---

# 7.16 Best Practices

### Store Related Data Together

Prefer:

```python
temps = [25, 27, 30]
```

instead of:

```python
temp1 = 25
temp2 = 27
temp3 = 30
```

---

### Combine Lists with Loops

```python
for item in my_list:

    process(item)
```

This is one of the most common patterns in programming.

---

### Use Meaningful Names

Prefer:

```python
heart_rates
```

instead of:

```python
x
```

---

# 7.17 Common Errors

### Index Out of Range

```python
heart_rates = [72, 85, 110]

print(heart_rates[3])
```

Error.

Valid indexes:

```text
0 1 2
```

---

### Forgetting Parentheses

Incorrect:

```python
patient_names.append
```

Correct:

```python
patient_names.append("Rahul")
```

---

### Confusing Index and Value

```python
patient_names[0]
```

means:

```text
Value at Position 0
```

not:

```text
Value 0
```

---

# 7.18 Summary

```text
Variables
      ↓
Store One Value

Lists
      ↓
Store Multiple Values

Loops
      ↓
Process Values

Conditions
      ↓
Make Decisions

Functions
      ↓
Reuse Logic

Programs
      ↓
Solve Real Problems
```

Lists are among the most important data structures in programming and form the foundation for advanced topics such as NumPy, Pandas, Machine Learning, Deep Learning, and Large Language Models.

---

## Key Takeaway

> Variables store individual values. Lists store collections of related values and enable efficient processing of real-world data.

---

## Next Chapter

# Dictionaries

Lists help us manage many values.

However, patient data naturally consists of **key–value pairs**:

```text
Name         → Harshita

Heart Rate   → 110

Oxygen Level → 92
```

To store such structured records efficiently, we use **Dictionaries**.
