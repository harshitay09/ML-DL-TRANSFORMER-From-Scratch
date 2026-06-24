# Conditional Statements (`if`, `elif`, `else`)

## Why Do We Need Conditions?

Let's continue building our Smart IIoT Healthcare System.

So far, our system can:

```text
Variables   → Store Data

Data Types  → Understand Data

Operators   → Analyze Data
```

Example:

```python
heart_rate = 120

print(heart_rate > 100)
```

Output:

```text
True
```

The computer successfully analyzed the patient's heart rate.

But a problem still exists.

The computer knows something is wrong.

Now what?

Should it:

* Alert the doctor?
* Notify the nurse?
* Continue monitoring?
* Ignore the reading?

The computer can analyze information, but it cannot decide what action to take.

To make decisions, computers use **Conditional Statements**.

---

## How Humans Use Conditions

Without realizing it, we use conditions every day.

```text
If it rains
    Carry an umbrella

If battery < 20%
    Charge the phone

If marks >= 40
    Pass

Else
    Fail
```

Humans naturally think:

```text
Condition
     ↓
Decision
     ↓
Action
```

Computers follow exactly the same process.

---

## What Is a Conditional Statement?

A Conditional Statement allows a computer to choose between different actions based on a condition.

In simple words:

> Conditions teach computers how to make decisions.

---

## The Big Picture

```text
Patient Data
      ↓

Analyze Data
      ↓

Condition
      ↓

Decision
      ↓

Action
```

Example:

```text
Heart Rate = 120
       ↓

heart_rate > 100
       ↓

True
       ↓

Alert Doctor
```

This is the basic idea behind every intelligent system.

---

# The `if` Statement

Suppose the hospital rule is:

```text
If Heart Rate > 100
    Alert Doctor
```

Python code:

```python
heart_rate = 120

if heart_rate > 100:
    print("Alert Doctor")
```

Output:

```text
Alert Doctor
```

### How Python Thinks

```text
heart_rate > 100 ?
        │
      True
        │
        ▼

Alert Doctor
```

If the condition is True, the code inside the `if` block runs.

---

# The `else` Statement

What if the patient's heart rate is normal?

We still want the system to respond.

```python
heart_rate = 80

if heart_rate > 100:
    print("Alert Doctor")
else:
    print("Patient Stable")
```

Output:

```text
Patient Stable
```

### Decision Flow

```text
Condition
    │
    ▼

Is it True?
   /     \
 Yes      No
  │        │
  ▼        ▼

Alert   Stable
Doctor  Patient
```

The `else` block runs when the condition is False.

---

# The `elif` Statement

Sometimes there are more than two possibilities.

Hospital Policy:

```text
Heart Rate > 120
    Critical

Heart Rate > 100
    High Risk

Otherwise
    Normal
```

Python code:

```python
heart_rate = 115

if heart_rate > 120:
    print("Critical")

elif heart_rate > 100:
    print("High Risk")

else:
    print("Normal")
```

Output:

```text
High Risk
```

### Decision Tree

```text
               Start
                 │
                 ▼

       heart_rate > 120 ?
            /      \
         Yes        No
          │          │
          ▼          ▼

      Critical   heart_rate >100 ?
                      /      \
                   Yes        No
                    │          │
                    ▼          ▼

                High Risk    Normal
```

---

## Conditions in Real Systems

### Smart Healthcare

```python
oxygen_level = 85

if oxygen_level < 90:
    print("Emergency Alert")
```

Used for:

* Patient Monitoring
* ICU Systems
* Remote Healthcare

---

### Smart Factory (IIoT)

```python
machine_temp = 95

if machine_temp > 80:
    print("Machine Overheating")
```

Used for:

* Fault Detection
* Predictive Maintenance
* Safety Monitoring

---

### Edge AI

```python
confidence_score = 0.95

if confidence_score > 0.90:
    print("Accept Detection")
```

Used for:

* Smart Cameras
* Object Detection
* Autonomous Systems

---

## Common Beginner Mistakes

### Mistake 1

```python
if marks = 40:
```

Wrong.

```python
if marks == 40:
```

Correct.

Remember:

```text
=   Assigns a value

==  Compares a value
```

---

### Mistake 2

Forgetting the colon.

Wrong:

```python
if marks > 40
```

Correct:

```python
if marks > 40:
```

---

### Mistake 3

Wrong indentation.

Wrong:

```python
if marks > 40:
print("Pass")
```

Correct:

```python
if marks > 40:
    print("Pass")
```

Python uses indentation to identify code blocks.

---

## Quick Check

Predict the output before running.

```python
marks = 75

if marks >= 40:
    print("Pass")
else:
    print("Fail")
```

What will be printed?

---

## One-Line Summary

```text
Variables → Store Data

Data Types → Understand Data

Operators → Analyze Data

Conditions → Decide What To Do
```

Conditions are the bridge between **analysis** and **action**.

Without conditions, a computer can observe the world.

With conditions, a computer can respond to the world.

---

## What Comes Next?

Our Smart IIoT Healthcare System can now make decisions.

But hospitals and factories monitor systems continuously.

Checking conditions once is not enough.

We need a way to repeat tasks automatically.

This leads to the next topic:

# Loops
