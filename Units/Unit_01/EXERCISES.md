# Unit 1 — From Procedural Programming to OOP: Exercises

These exercises practise the change from separate data and functions to
objects that combine state and behavior. For written questions, give a short
reason for every choice. For programming questions, submit the header,
implementation, and a small `main` that demonstrates the required behavior.
Complete the prediction work before running any code.

## 1. Identify state and behavior

A music application stores a song title, artist, and duration. List the state
that belongs inside a `Song` object and three operations that belong to the
class. Explain why a function that prints the entire playlist does not belong
to one `Song` object.

## 2. Trace object use

Given a `Song` class with `play()` and `print()` member functions, write four
statements that create two objects and call both operations. Mark the object,
member function, and arguments in every call.

## 3. Convert a struct to a class

Convert this public structure into a class with private data and a small public
interface. Put declarations in `Book.hpp`, implementations in `Book.cpp`, and
demonstration code in `main.cpp`.

```cpp
struct Book {
    std::string title;
    int pages;
};
```

Your program must create two books and print their details without accessing
data members directly.

## 4. Optional extension

Add a `readPages(int amount)` operation that records reading progress without
allowing progress to exceed the number of pages. State the rule the object must
preserve.

## Completion check

You should be able to explain why an operation belongs to a class, create and
use objects, and separate a class interface from its implementation.
