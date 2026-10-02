# Unit 6 — Rule of Three and Operators: Exercises

For every class that owns dynamic memory, draw the owned resource before and
after copying or assignment. Implementation answers must include tests that
would expose shallow copying, self-assignment errors, and invalid indexing.
When selecting an operator form, explain the decision rather than only giving
working syntax.

## 1. Find the ownership error

A `TextBuffer` stores `char* data` allocated with `new[]` and defines only a
destructor. Explain what happens when one buffer is copied and both objects are
destroyed. Identify every missing special member function.

## 2. Implement deep copying

Implement the Rule of Three for an `IntBuffer` that owns a dynamic integer
array. Test copying, self-assignment, assignment between different sizes, and
independence after modification.

## 3. Design natural operators

For a `Fraction` class, implement `==`, `<`, `+`, and `<<`. Decide which
operators should be members and which should be non-members. Your explanation
must address symmetry and access to private data.

## 4. Checked subscript

Add const and non-const `operator[]` overloads to `IntBuffer`. Decide how an
invalid index is reported and demonstrate both reading and writing through the
operator.

## 5. Optional extension

Implement copy assignment using a temporary replacement so that allocation
failure does not destroy the original value. Explain the order of operations.

## Completion check

You should be able to prove that copies are independent and that each operator
preserves the class invariant and behaves naturally for its callers.
