# Data Types: How Computers Understand Information

## Why Do We Need Data Types?

Imagine a Smart Hospital receives:

```text id="1"
Patient Name = Harshita
Heart Rate = 92
Temperature = 37.5
Critical Status = True
```

Should a computer treat all these values the same way?

No.

A name is text, a heart rate is a number, a temperature is a decimal, and a critical status is a True/False value.

Computers must understand the nature of information before processing it.

This leads to **Data Types**.

---

## Human Analogy

Your brain automatically understands:

```text id="2"
Name → Text
Age → Number
CGPA → Decimal
Student? → Yes/No
```

Computers do the same using Data Types.

---

## Definition

A **Data Type** is a classification that tells the computer:

* What kind of information is stored.
* How it should be represented.
* What operations can be performed on it.

---

## Common Python Data Types

### Integer (int)

```python id="3"
age = 25
```

Whole numbers.

### Float

```python id="4"
cgpa = 8.75
```

Decimal numbers.

### String (str)

```python id="5"
name = "Harshita"
```

Text data.

### Boolean (bool)

```python id="6"
is_student = True
```

True or False values.

---

## Real-World Examples

| Domain       | Example             |
| ------------ | ------------------- |
| IoT          | temperature = 34.2  |
| Healthcare   | heart_rate = 92     |
| Industry 4.0 | machine_temp = 68.4 |
| ML           | loss = 0.25         |
| LLM          | token_count = 512   |

---

## Key Insight

```text id="7"
Variables answer:
Where is data stored?

Data Types answer:
What kind of data is stored?
```

Without Data Types, computers cannot correctly process information.

---

## Next Topic

**Operators** → How computers perform calculations and make decisions using data.
