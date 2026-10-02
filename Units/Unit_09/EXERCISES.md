# Unit 9 — Exception Handling: Exercises

## 1. Trace propagation — 20 minutes

Write three functions `main → process → load`. Throw a standard exception in
`load`, catch it only in `main`, and use small local trace objects to predict
the destruction order during stack unwinding.

## 2. Order catch handlers — 15 minutes

Given handlers for `std::exception` and `std::out_of_range`, decide which must
appear first. Demonstrate the consequence of reversing them and explain the
rule in terms of inheritance.

## 3. Define a useful custom exception — 30 minutes

Create an `InsufficientBalanceError` that reports the requested amount and the
available balance. Throw it from a withdrawal operation and display its
context in the handler.

## 4. Preserve valid state — 35 minutes

Implement a two-step operation that validates all requirements before changing
an object. Write a failing test and demonstrate that the object retains its
original value after the exception.

## 5. Optional extension — 20 minutes

Compare returning an error code with throwing an exception for one operation.
Discuss caller obligations, ignored errors, and separation of normal and error
paths.

