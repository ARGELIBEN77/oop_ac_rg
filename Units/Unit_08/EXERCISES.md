# Unit 8 — Polymorphism and Abstract Classes: Exercises

These exercises develop a design in which client code depends on an abstract
base interface rather than on concrete media types. Use base references or
pointers for runtime polymorphism; do not select behavior with type checks.

## 1. Turn a virtual operation into a requirement

Define an abstract `MediaItem` class with a pure virtual `play() const`
operation and a virtual destructor. Attempt to create a `MediaItem` object and
explain the compiler error.

Then implement a concrete `Song` whose `play` signature matches exactly.
Explain how `= 0` changes the base class and what responsibility it gives every
concrete derived class.

## 2. Show that abstract does not mean empty

Give `MediaItem` a title, a constructor, and a concrete `getTitle() const`
function while keeping `play() const` pure virtual. Explain which state and
behavior are shared and which behavior derived classes must supply.

Demonstrate that a `Song` uses the base constructor and inherited getter.

## 3. Diagnose an accidentally abstract class

Create a derived `Podcast` with one of these mistakes:

- omit the trailing `const`;
- change a parameter type;
- misspell the function name.

Add `override` and use the compiler message to diagnose the mismatch. Explain
why the class remains abstract when the pure virtual signature has not been
implemented exactly.

## 4. Represent the hierarchy in UML

Draw `MediaItem`, `Song`, and `Podcast` as a UML class diagram. Mark the base
class and pure virtual operation as abstract, include visibility symbols, and
show the generalization arrows in the correct direction.

Explain what the diagram communicates before any implementation is read.

## 5. Build a polymorphic music library

Implement a fixed-capacity `MusicLibrary` that stores `MediaItem*` values and
provides `add` and `playAll` operations. Register at least one `Song` and one
`Podcast` created outside the library.

Trace one iteration of `playAll`: start from the stored base pointer, identify
the dynamic object, and explain how virtual dispatch reaches the correct
override without an `if` statement or type check.

## 6. Reason about references, pointers, and lifetime

Modify one client operation to accept `const MediaItem&` and another to store a
`MediaItem*`. Explain why neither form creates a copy and why both preserve
polymorphism.

State who owns the objects stored by the current `MusicLibrary`, how long they
must remain alive, and what could go wrong if a pointer outlives its object.
Do not introduce smart pointers yet.

## 7. Compare an abstract base with an interface-style class

Design two versions of a playback abstraction:

- an abstract base class that stores shared title data and provides concrete
  behavior;
- an interface-style class containing only public pure virtual operations and
  a virtual destructor.

Explain why both are abstract classes in C++ and when each design is more
appropriate.

## 8. Extend without modifying the client

Add `RadioStream` as a new concrete `MediaItem`. Register it in the existing
library and show that `playAll` needs no new branch and no source-code change.

Explain how the abstract interface supports extension and identify the only
new code that had to be written.

## Completion check

You should be able to define and represent an abstract class, implement exact
overrides, trace runtime dispatch through pointers and references, reason about
object lifetime, and add a new concrete type without rewriting the client.
