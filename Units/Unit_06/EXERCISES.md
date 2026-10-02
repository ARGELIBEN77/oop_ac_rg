# Unit 6 — Rule of Three and Operators: Exercises

## 1. Find the ownership error — 20 minutes

A `TextBuffer` stores `char* data` allocated with `new[]` and defines only a
destructor. Explain what happens when one buffer is copied and both objects are
destroyed. Identify every missing special member function.

## 2. Implement deep copying — 45 minutes

Implement the Rule of Three for an `IntBuffer` that owns a dynamic integer
array. Test copying, self-assignment, assignment between different sizes, and
independence after modification.

## 3. Design natural operators — 35 minutes

For a `Fraction` class, implement `==`, `<`, `+`, and `<<`. Decide which
operators should be members and which should be non-members. Your explanation
must address symmetry and access to private data.

## 4. Checked subscript — 25 minutes

Add const and non-const `operator[]` overloads to `IntBuffer`. Decide how an
invalid index is reported and demonstrate both reading and writing through the
operator.

## 5. Optional extension — 20 minutes

Implement copy assignment using a temporary replacement so that allocation
failure does not destroy the original value. Explain the order of operations.

