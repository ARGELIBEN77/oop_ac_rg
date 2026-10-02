# Unit 7 — Inheritance and Binding: Exercises

## 1. Is-a or has-a? — 15 minutes

Decide whether inheritance is appropriate for each pair: `Car`/`Engine`,
`SavingsAccount`/`BankAccount`, `Square`/`Rectangle`, and
`Playlist`/`Song`. Justify each answer using substitutability rather than
shared fields.

## 2. Correct the override — 20 minutes

```cpp
class Device {
public:
    virtual void print() const;
};

class Phone : public Device {
public:
    void print();
};
```

Explain why `Phone::print` does not override the base operation. Correct the
declaration and use `override` to make the compiler verify it.

## 3. Observe slicing — 30 minutes

Create a base `Ticket` and a derived `VipTicket` with an additional benefit.
Pass the derived object once by value and once by `const Ticket&`. Record which
parts of the object remain visible and explain the difference.

## 4. Safe destruction — 30 minutes

Build a two-class hierarchy in which the derived class owns a dynamic resource.
Delete a derived object through a base pointer first with, and then without, a
virtual base destructor. Explain the risk; do not rely only on printed output.

## 5. Optional extension — 20 minutes

Use a small trace to distinguish static type, dynamic type, and the function
selected at runtime for three different expressions.

