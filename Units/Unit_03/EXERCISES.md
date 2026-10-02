# Unit 3 — Constructors and Initializer Lists: Exercises

These exercises focus on establishing a valid object at the moment it is
created. Show the selected constructor and resulting state when tracing. For
implementation work, include declarations, initializer lists, validation, and
client code that covers every constructor.

## 1. Select a constructor

Given default, one-argument, and two-argument constructors for `Point`, write
five object declarations. For each declaration, identify the selected
constructor and the resulting coordinates.

## 2. Diagnose invalid construction

Explain what is wrong with constructing an object first and calling `init`
later. Give one example of client code that can observe the object between
those two steps.

## 3. Implement valid construction

Implement a `Course` class with a name, maximum number of students, and current
enrolment. Provide a parameterized constructor and a delegating default
constructor. Use initializer lists and reject impossible initial values.

## 4. Initialization order

Create two small member classes that print from their constructors. Place them
inside a third class. Predict the construction order when the initializer list
mentions the members in the reverse order, then verify your prediction.

## 5. Optional extension

Add a `const` data member to `Course` and explain why assignment in the
constructor body is not a valid replacement for initialization.

## Completion check

You should be able to choose and implement constructors and explain why
initializer lists are part of object construction rather than ordinary later
assignment.
