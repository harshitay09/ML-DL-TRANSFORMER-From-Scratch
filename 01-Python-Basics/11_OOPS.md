Chapter 10 — Why Do We Need Object-Oriented Programming?

So far, we've learned several ways to organize programs.

Concept	Problem It Solves
Variables	Store a single value
Lists	Store many values
Dictionaries	Store related values using names
Functions	Reuse logic and avoid repetition

At this point, we can already build many useful programs.

So a natural question is:

If variables, dictionaries, functions, and loops are enough, why was Object-Oriented Programming (OOP) invented?

To answer this, let's continue building our Hospital Management System.

Step 1 — A Small Hospital

Initially, the hospital only has a few patients.

patients = [
    {
        "name": "Harshita",
        "age": 24,
        "heart_rate": 110,
        "oxygen": 95
    },
    {
        "name": "Aman",
        "age": 30,
        "heart_rate": 78,
        "oxygen": 99
    }
]

To display patient information, we write a function.

def display(patient):
    print(patient["name"])
    print(patient["heart_rate"])

And use a loop.

for patient in patients:
    display(patient)

For a small program, this solution is simple, readable, and completely acceptable.

At this stage, OOP is unnecessary.

Step 2 — The Software Evolves

As the hospital grows, each patient now has more information.

Patient
├── Name
├── Age
├── Doctor
├── Insurance
├── Reports
├── Medicines
├── Bill
├── Room Number
└── Emergency Contact

The software also gains new features.

display(patient)

update_vitals(patient)

calculate_bill(patient)

book_appointment(patient)

generate_report(patient)

discharge(patient)

Notice something?

Every function operates on the same patient.

The patient is the center of the entire system.

Step 3 — The Real Issue

Now imagine 100 developers working on this project.

Anyone can write:

patient["heart_rate"] = -50

or

del patient["doctor"]

or

patient["bill"] = "abc"

Python doesn't stop them.

The problem isn't that dictionaries are bad.

The problem is that there are no rules governing how patient data should be accessed or modified.

As the project grows, maintaining consistency becomes increasingly difficult.

Step 4 — A Better Way to Organize

Computer scientists noticed a pattern.

Every patient has:

Data
Operations performed on that data

Instead of keeping them separate,

Patient Data

↓

Functions

they combined them into a single unit.

Patient

├── Data
│     name
│     age
│     doctor
│
└── Methods
      display()
      update_vitals()
      calculate_bill()

This unit is called an object.

The blueprint used to create such objects is called a class.

Why This Matters

Instead of writing

calculate_bill(patient)

we can write

patient.calculate_bill()

Instead of

update_vitals(patient)

we write

patient.update_vitals()

The patient object now manages its own data and behavior.

This makes the code easier to understand because everything related to a patient is kept together.

When Should You Use OOP?
Situation	Best Choice
100-line script	Functions
Data analysis notebook	Functions + Dictionaries
Automation script	Functions
Hospital Management System	OOP
Banking Software	OOP
Game Engine	OOP
Machine Learning Library	Mostly OOP

OOP is not a replacement for functions.

It is a way to organize large software systems.

Functions still exist inside classes.

Key Takeaways
Variables organize values.
Lists organize collections.
Dictionaries organize related information.
Functions organize logic.
OOP organizes entire systems.

As software grows, the challenge shifts from writing code to organizing code.

That is the problem OOP was designed to solve.
