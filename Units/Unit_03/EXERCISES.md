# Unit 3 — Constructors and Initializer Lists: Exercises

## 1. Select a constructor — 15 minutes

Given default, one-argument, and two-argument constructors for `Point`, write
five object declarations. For each declaration, identify the selected
constructor and the resulting coordinates.

## 2. Diagnose invalid construction — 20 minutes

Explain what is wrong with constructing an object first and calling `init`
later. Give one example of client code that can observe the object between
those two steps.

## 3. Implement valid construction — 35 minutes

Implement a `Course` class with a name, maximum number of students, and current
enrolment. Provide a parameterized constructor and a delegating default
constructor. Use initializer lists and reject impossible initial values.

## 4. Initialization order — 20 minutes

Create two small member classes that print from their constructors. Place them
inside a third class. Predict the construction order when the initializer list
mentions the members in the reverse order, then verify your prediction.

## 5. Optional extension — 20 minutes

Add a `const` data member to `Course` and explain why assignment in the
constructor body is not a valid replacement for initialization.

