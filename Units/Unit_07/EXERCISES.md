# Unit 7 — Inheritance and Binding: Exercises

These exercises focus on designing and tracing class hierarchies. For every
relationship, first decide whether it represents a genuine is-a relationship.
For every trace, record construction, selected function, and destruction as
separate steps.

## 1. Distinguish is-a from has-a

Decide whether public inheritance is appropriate for each pair:

- `LiveRecording` and `Song`;
- `Playlist` and `Song`;
- `SavingsAccount` and `BankAccount`;
- `Car` and `Engine`;
- `Square` and `Rectangle`.

Justify each answer using substitutability: would every operation promised by
the proposed base class remain meaningful for the derived class? Suggest
composition for relationships that are has-a rather than is-a.

## 2. Initialize the base part

Implement `Song` with no default constructor and derive `LiveRecording` from
it. Add `venue` and `audienceSize` to the derived class.

First omit the call to the base constructor and explain the compiler error.
Then correct the derived constructor by initializing the `Song` base part in
its initializer list. Demonstrate that inherited public getters can be called
on a `LiveRecording` object.

## 3. Compare public, protected, and private access

Create one public, one protected, and one private member in a base class. For
each member, state whether it is accessible:

- inside the base class;
- inside a derived class;
- from ordinary client code.

Verify your predictions with small statements. Then explain why making data
`protected` gives every derived class more access than using a protected or
public getter.

## 4. Trace construction and destruction

Add tracing messages to the constructors and destructors of `Song` and
`LiveRecording`. Create one derived object and predict the complete trace.

Explain why the base constructor runs before the derived constructor body and
why the derived destructor runs before the base destructor. Extend the trace
with two derived objects in one scope.

## 5. Separate hiding from overriding

Begin with this interface:

```cpp
class Song {
public:
    virtual void print() const;
};

class LiveRecording : public Song {
public:
    void print();
};
```

Explain why the derived function does not override the base function. Correct
the signature and add `override`. Then remove `virtual` from the base version
and explain how function hiding differs from runtime overriding.

## 6. Trace static and dynamic binding

Use a base object, a derived object, a base reference bound to the derived
object, and a base pointer pointing to the derived object. For each call to
`print`, record:

- the expression's static type;
- the object's dynamic type;
- whether binding is static or dynamic;
- the selected implementation.

Repeat once with a non-virtual function and once with a virtual function.
Explain conceptually how a virtual table supports runtime selection.

## 7. Investigate a virtual call from a constructor

Let a base constructor call a virtual `print` function that is overridden in
the derived class. Predict which implementation runs while the base part is
being constructed, then verify it.

Explain why the derived override is not selected before the derived object has
finished construction and why calling virtual functions from constructors is
usually a design warning.

## 8. Prevent slicing

Pass a `LiveRecording` once by `Song` value and once by `const Song&`. Compare
the static type, dynamic type, available data, and selected virtual function in
the two calls. Explain exactly what is lost during slicing and how references
or pointers preserve polymorphic behavior.

## 9. Make destruction polymorphic

Create and delete a `LiveRecording` through a `Song*`. Trace the result when
the base destructor is virtual. Then explain the risk if it is not virtual,
especially when the derived class owns a resource.

State the general rule for any base class intended for polymorphic deletion.

## Completion check

You should be able to justify inheritance, initialize the base part, apply
access rules, trace construction and binding, distinguish hiding from
overriding, prevent slicing, and explain virtual destruction.
