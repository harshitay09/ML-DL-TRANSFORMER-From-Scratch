# Chapter 8: Dictionaries – Storing Structured Information

## Learning Objectives

After completing this chapter, you should be able to:

* Explain why Dictionaries are needed.
* Define a Dictionary and its components.
* Create, access, update, and remove Dictionary entries.
* Use Dictionaries with Conditions, Loops, and Functions.
* Understand the limitations of Lists that led to Dictionaries.
* Model real-world entities using Dictionaries.

---

# 8.1 Introduction

In previous chapters, we introduced Variables, Lists, Loops, Conditions, and Functions.

Using these concepts, we developed a simple Smart Healthcare System.

Patient information was stored using multiple Lists.

```python
patient_names = ["Harshita", "Aman", "Riya"]

heart_rates = [110, 75, 130]

oxygen_levels = [92, 98, 88]
```

This approach works for small examples.

However, as software systems become larger and more complex, several limitations emerge.

Understanding these limitations is essential because Dictionaries were created specifically to address them.

---

# 8.2 Limitations of Lists

## Limitation 1: Information Is Distributed

A patient is a single entity.

However, patient information is distributed across multiple Lists.

```text
Patient Name   → List 1

Heart Rate     → List 2

Oxygen Level   → List 3
```

To retrieve information for one patient, multiple Lists must be accessed.

```python
patient_names[0]

heart_rates[0]

oxygen_levels[0]
```

Output:

```text
Harshita
110
92
```

Although these values belong to the same patient, they are stored separately.

---

## Limitation 2: Relationships Depend on Position

Lists maintain relationships through indexes.

```text
Index 0

Harshita
110
92
```

represents one patient.

If one List changes length:

```python
patient_names = ["Harshita"]

heart_rates = [110, 75]
```

the relationship becomes invalid.

The system can no longer determine who owns the value:

```text
75
```

Data integrity is compromised.

---

## Limitation 3: Lack of Meaning

Consider:

```python
heart_rates[0]
```

The value is retrieved through position.

However, the position itself has no semantic meaning.

Real-world systems operate using concepts such as:

```text
Name

Age

Heart Rate

Temperature

Blood Pressure
```

Data should be accessible through meaning rather than position.

---

## Limitation 4: Poor Scalability

Suppose a hospital decides to track:

```text
Blood Pressure

Temperature

Weight

Diagnosis

Medication
```

Using Lists:

```python
patient_names = []

heart_rates = []

oxygen_levels = []

blood_pressures = []

temperatures = []

weights = []
```

The number of Lists continues to grow.

Maintenance becomes increasingly difficult.

---

## Limitation 5: Real-World Objects Have Attributes

A patient is not simply:

```text
110
92
38.5
```

A patient possesses attributes.

```text
Name

Age

Heart Rate

Oxygen Level

Temperature

Blood Pressure
```

These attributes naturally belong together.

A suitable data structure should store them together.

---

# 8.3 Motivation for Dictionaries

Software engineers required a structure capable of:

```text
Keeping Related Data Together

Associating Meaning With Data

Reducing Dependence On Indexes

Improving Readability

Representing Real-World Objects
```

This requirement led to the Dictionary.

---

# 8.4 Definition of a Dictionary

A **Dictionary** is a collection of key–value pairs.

Each value is associated with a unique key.

General Syntax:

```python
dictionary_name = {
    key1: value1,
    key2: value2
}
```

Example:

```python
patient = {
    "name": "Harshita",
    "heart_rate": 110,
    "oxygen": 92
}
```

---

# 8.5 Keys and Values

In a Dictionary:

```python
patient = {
    "name": "Harshita",
    "heart_rate": 110,
    "oxygen": 92
}
```

```text
"name"        → Key

"Harshita"    → Value

"heart_rate"  → Key

110           → Value
```

A key acts as a label that identifies the associated value.

---

# 8.6 Visual Representation

```python
patient = {
    "name": "Harshita",
    "heart_rate": 110,
    "oxygen": 92
}
```

Representation:

```text
┌────────────┬──────────┐
│ name       │ Harshita │
├────────────┼──────────┤
│ heart_rate │ 110      │
├────────────┼──────────┤
│ oxygen     │ 92       │
└────────────┴──────────┘
```

Unlike Lists, information is accessed through keys rather than indexes.

---

# 8.7 Creating Dictionaries

### Healthcare Example

```python
patient = {
    "name": "Harshita",
    "heart_rate": 110,
    "oxygen": 92,
    "temperature": 38.5
}
```

### Industrial IoT Example

```python
machine = {
    "id": "M101",
    "temperature": 85,
    "status": "Running"
}
```

---

# 8.8 Accessing Values

Syntax:

```python
dictionary[key]
```

Example:

```python
print(patient["name"])
```

Output:

```text
Harshita
```

```python
print(patient["oxygen"])
```

Output:

```text
92
```

---

# 8.9 Adding Entries

```python
patient["blood_pressure"] = "140/90"
```

Updated Dictionary:

```python
{
    "name": "Harshita",
    "heart_rate": 110,
    "oxygen": 92,
    "blood_pressure": "140/90"
}
```

---

# 8.10 Updating Entries

```python
patient["oxygen"] = 95
```

Updated:

```text
oxygen → 95
```

---

# 8.11 Removing Entries

```python
del patient["temperature"]
```

The corresponding key–value pair is removed.

---

# 8.12 Dictionaries and Conditions

```python
patient = {
    "name": "Harshita",
    "oxygen": 88
}
```

```python
if patient["oxygen"] < 90:
    print("Emergency Alert")
```

Output:

```text
Emergency Alert
```

---

# 8.13 Dictionaries and Functions

```python
def check_patient(patient):

    if patient["oxygen"] < 90:
        return "Emergency"

    return "Normal"
```

Calling:

```python
patient = {
    "name": "Harshita",
    "oxygen": 88
}

print(check_patient(patient))
```

Output:

```text
Emergency
```

---

# 8.14 Lists of Dictionaries

A hospital manages multiple patients.

A common design is:

```python
patients = [

    {
        "name": "Harshita",
        "heart_rate": 110,
        "oxygen": 92
    },

    {
        "name": "Aman",
        "heart_rate": 75,
        "oxygen": 98
    },

    {
        "name": "Riya",
        "heart_rate": 130,
        "oxygen": 88
    }

]
```

This structure combines:

```text
List
    +
Dictionary
```

and is widely used in real-world software systems.

---

# 8.15 Smart Healthcare Case Study

```python
def next_appointment(patient):

    if patient["heart_rate"] > 120:
        return "Visit in 1 Day"

    elif patient["heart_rate"] > 100:
        return "Visit in 7 Days"

    return "Visit in 30 Days"
```

Processing:

```python
for patient in patients:

    print(
        patient["name"],
        "-",
        next_appointment(patient)
    )
```

Output:

```text
Harshita - Visit in 7 Days

Aman - Visit in 30 Days

Riya - Visit in 1 Day
```

---

# 8.16 Applications

## Smart Healthcare

* Electronic Health Records
* Patient Monitoring
* Clinical Decision Support

## Industrial IoT (IIoT)

* Sensor Monitoring
* Asset Management
* Predictive Maintenance

## Machine Learning

* Feature Storage
* Dataset Representation
* Metadata Management

## Large Language Models

* Chat History
* Prompt Storage
* Agent Memory Systems

---

# 8.17 Best Practices

### Use Descriptive Keys

Prefer:

```python
patient["heart_rate"]
```

instead of:

```python
patient["x"]
```

### Store Related Information Together

```python
patient = {
    "name": "Harshita",
    "oxygen": 92
}
```

### Use Dictionaries for Real-World Records

Whenever information naturally consists of:

```text
Attribute → Value
```

a Dictionary is usually the appropriate structure.

---

# 8.18 Common Errors

### Accessing a Missing Key

```python
print(patient["salary"])
```

Produces an error if the key does not exist.

### Misspelled Keys

```python
patient["oxgen"]
```

instead of:

```python
patient["oxygen"]
```

### Confusing Lists and Dictionaries

List:

```python
heart_rates[0]
```

Dictionary:

```python
patient["heart_rate"]
```

---

# 8.19 Summary

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

Programs
      ↓
Model Real-World Systems
```

Dictionaries provide a meaningful way to represent entities and their attributes, making them one of the most important data structures in Python and modern software development.

---

## Key Takeaway

> Lists organize data by position. Dictionaries organize data by meaning.

---

## Next Chapter

# Tuples

Lists and Dictionaries are mutable structures.

The next chapter introduces Tuples, an immutable data structure used when data should remain unchanged after creation.
