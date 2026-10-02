# Unit 1 — From Procedural Programming to OOP: Exercises

Complete the first two exercises before running any code.

## 1. Identify state and behavior — 10 minutes

A music application stores a song title, artist, and duration. List the state
that belongs inside a `Song` object and three operations that belong to the
class. Explain why a function that prints the entire playlist does not belong
to one `Song` object.

## 2. Trace object use — 15 minutes

Given a `Song` class with `play()` and `print()` member functions, write four
statements that create two objects and call both operations. Mark the object,
member function, and arguments in every call.

## 3. Convert a struct to a class — 30 minutes

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

## 4. Optional extension — 20 minutes

Add a `readPages(int amount)` operation that records reading progress without
allowing progress to exceed the number of pages. State the rule the object must
preserve.

