# Unit 2 — Encapsulation and Interfaces: Exercises

## 1. Find the invariant — 10 minutes

For each class, write one condition that must always remain true: `BankAccount`,
`Temperature`, and `ExamGrade`. Then name the public operation most likely to
break that condition.

## 2. Improve an interface — 20 minutes

The following interface exposes its representation:

```cpp
class Ticket {
public:
    std::string owner;
    double price;
    bool used;
};
```

Redesign it with private state and purposeful operations. Do not add a setter
for every field. Your answer must explain which changes clients are allowed to
make and which changes the class prevents.

## 3. Const correctness — 25 minutes

Implement a `Counter` class with `increment`, `reset`, `value`, and `isZero`.
Declare every observer as `const`. Demonstrate that observers can be called on
a `const Counter`, while modifying operations cannot.

## 4. Validation task — 30 minutes

Implement a `TimeOfDay` class that stores hours and minutes. Reject invalid
values and guarantee that every visible object represents a valid time. Write
tests for the boundary values `00:00`, `23:59`, `24:00`, and `12:60`.

## 5. Optional extension — 15 minutes

Add a `minutesUntil(const TimeOfDay& other) const` observer. State what should
happen when `other` represents an earlier time on the same day.

