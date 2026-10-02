# Unit 8 — Runtime Polymorphism and Abstract Classes: Exercises

The purpose of these exercises is to design clients that depend on an abstract
interface rather than on concrete types. Include the complete base interface,
at least two derived classes, and client code that works through base pointers
or references. Do not use type checks to choose behavior.

## 1. Complete an abstract interface

Define an abstract `Shape` class with `area()` and `print()` operations and a
virtual destructor. Explain why a `Shape` object cannot be created directly.

## 2. Add concrete types

Implement `Rectangle` and `Triangle`. Store both behind base-class pointers and
print their areas without testing their concrete types. Include at least one
call through a base reference.

## 3. Extend without modifying clients

Add a `Circle` class to the hierarchy. Show that the loop that processes all
shapes does not need a new `if` statement. Explain which design property makes
this possible.

## 4. Diagnose a polymorphic collection

Explain why `std::vector<Shape>` is unsuitable and why
`std::vector<Shape*>` requires careful ownership decisions. Propose a safe
container type for owning shapes and state which later unit provides it.

## 5. Optional extension

Add a second pure virtual operation that returns a textual description. Decide
whether it should return by value or by reference and justify the lifetime
implications.

## Completion check

You should be able to extend a hierarchy with a new concrete type without
rewriting the client loop that processes base-class objects.
