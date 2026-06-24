# Loops: Teaching Computers to Work Without Getting Tired

## Learning Objectives

After completing this chapter, you should be able to:

* Understand why loops are needed.
* Differentiate between `for` and `while` loops.
* Trace loop execution step-by-step.
* Write programs using loops.
* Apply loops in Healthcare, IIoT, Edge AI, and Machine Learning applications.

---

# The Story So Far

Our Smart IIoT Healthcare System can now:

```text
Variables
    ↓
Store Data

Data Types
    ↓
Understand Data

Operators
    ↓
Analyze Data

Conditions
    ↓
Make Decisions
```

Example:

```python
heart_rate = 120

if heart_rate > 100:
    print("Alert Doctor")
```

Great.

The system can now make decisions.

But a new problem appears.

---

# The Problem

Hospitals do not check patients only once.

They monitor patients continuously.

Imagine a patient in the ICU.

Every second the system checks:

```text
Heart Rate
Temperature
Oxygen Level
Blood Pressure
```

Question:

Should we write this?

```python
check_patient()
check_patient()
check_patient()
check_patient()
check_patient()
check_patient()
```

What if monitoring must continue for:

```text
1 hour
1 day
1 month
```

Impossible.

Computers need a way to repeat tasks automatically.

This led to the invention of:

# Loops

---

# Human Analogy

Imagine a security guard.

Every hour:

```text
Check Gate
Check Visitors
Check Cameras
```

The guard repeats the same task.

Humans repeat actions.

Computers use Loops to repeat actions.

---

# Formal Definition

A **Loop** is a programming structure that repeatedly executes a block of code until a specified condition is met.

Simple definition:

> Loops teach computers how to repeat work automatically.

---

# Big Picture

```text
Task
  ↓
Repeat
  ↓
Repeat
  ↓
Repeat
  ↓
Stop
```

Without loops:

```text
Huge Amount of Repeated Code
```

With loops:

```text
Small Code
+
Many Repetitions
```

---

# Why Loops Matter

Without loops:

```python
print("Monitoring")
print("Monitoring")
print("Monitoring")
print("Monitoring")
print("Monitoring")
```

With loops:

```python
for i in range(5):
    print("Monitoring")
```

Same result.

Much better code.

---

# Types of Loops in Python

Python mainly provides:

```text
for Loop
while Loop
```

---

# The for Loop

Used when we know how many times something should repeat.

### Syntax

```python
for variable in sequence:
    statement
```

---

# Example 1

```python
for i in range(5):
    print("Monitoring Patient")
```

Output:

```text
Monitoring Patient
Monitoring Patient
Monitoring Patient
Monitoring Patient
Monitoring Patient
```

---

# How Python Thinks

```text
Start
  │
  ▼

i = 0
  │
  ▼

Print
  │
  ▼

i = 1
  │
  ▼

Print
  │
  ▼

i = 2
  │
  ▼

Print
  │
  ▼

Continue...
```

---

# Understanding range()

```python
range(5)
```

Produces:

```text
0 1 2 3 4
```

Notice:

```text
Starts at 0
Stops before 5
```

---

# Example 2

```python
for i in range(1,6):
    print(i)
```

Output:

```text
1
2
3
4
5
```

---

# Real Healthcare Example

Monitor patient 10 times.

```python
for i in range(10):
    print("Checking Heart Rate")
```

---

# Real IIoT Example

100 sensors in a factory.

```python
for sensor in range(100):
    print("Checking Sensor")
```

---

# The while Loop

Used when we do NOT know how many repetitions are required.

The loop continues while a condition remains True.

### Syntax

```python
while condition:
    statement
```

---

# Example

```python
count = 1

while count <= 5:
    print(count)
    count += 1
```

Output:

```text
1
2
3
4
5
```

---

# How Python Thinks

```text
count = 1
      │
      ▼

count <= 5 ?
      │
   True
      │
      ▼

Print
      │
      ▼

count = count + 1
      │
      ▼

Check Again
```

---

# Visual Flow of a While Loop

```text
          Start
            │
            ▼

     Condition True?
         /      \
      Yes        No
       │          │
       ▼          ▼

 Execute Code    Stop
       │
       ▼

 Back To Condition
```

This diagram is one of the most important in programming.

---

# for vs while

| for                 | while               |
| ------------------- | ------------------- |
| Known repetitions   | Unknown repetitions |
| Simpler             | More flexible       |
| Uses sequence/range | Uses condition      |

---

# Example Comparison

### for

```python
for i in range(5):
    print(i)
```

### while

```python
i = 0

while i < 5:
    print(i)
    i += 1
```

Both produce:

```text
0
1
2
3
4
```

---

# Infinite Loop

A loop that never stops.

Example:

```python
while True:
    print("Monitoring")
```

Python will continue forever.

---

# Why Infinite Loops Are Dangerous

```text
High CPU Usage

Program Freeze

System Crash
```

Always ensure the condition eventually becomes False.

---

# Applications of Loops

## Smart Healthcare

```python
while True:
    monitor_patient()
```

Continuous monitoring.

---

## Smart Factory

```python
while True:
    monitor_machine()
```

Continuous equipment monitoring.

---

## Edge AI

```python
while True:
    process_camera_frame()
```

Real-time vision processing.

---

## Machine Learning

```python
for epoch in range(100):
```

Training neural networks.

---

## LLM Training

```python
for epoch in range(10):
```

Training over datasets repeatedly.

---

# Common Beginner Mistakes

## Mistake 1

Forgetting to update the variable.

```python
count = 1

while count <= 5:
    print(count)
```

Infinite loop.

---

## Mistake 2

Wrong indentation.

```python
for i in range(5):
print(i)
```

Incorrect.

---

## Mistake 3

Misunderstanding range()

```python
range(5)
```

Produces:

```text
0 1 2 3 4
```

Not:

```text
1 2 3 4 5
```

---

# Quick Revision

```text
Need Repetition
       ↓
Use Loops

Known Repetitions
       ↓
for Loop

Unknown Repetitions
       ↓
while Loop
```

---

# Chapter Summary

```text
Variables
      ↓
Store Data

Data Types
      ↓
Understand Data

Operators
      ↓
Analyze Data

Conditions
      ↓
Make Decisions

Loops
      ↓
Repeat Decisions
```

Loops allow computers to perform repetitive work automatically, making them essential for monitoring systems, automation, AI, and large-scale software.

---

# One-Line Takeaway

> Conditions decide what to do. Loops decide how many times to do it.

---

# Next Topic

## Functions

Our Smart IIoT Healthcare System can now:

```text
Store Data
Understand Data
Analyze Data
Make Decisions
Repeat Tasks
```

But we are still writing the same code again and again.

How can we create reusable blocks of code?

This leads to **Functions**.
