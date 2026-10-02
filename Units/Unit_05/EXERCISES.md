# Unit 5 — Working with Objects: Exercises

These exercises connect object passing, copying, initialization, shared class
data, and relationships between classes. For every design choice, explain
whether a copy is made, whether modification is allowed, and who owns each
object.

## 1. Choose a parameter form

Choose pass by value, reference, or `const` reference for each operation:

- display a `Song` without changing it;
- increase a song's play count;
- receive a small integer identifier;
- work with an independent copy of a `Playlist`;
- inspect an `Album` that may be expensive to copy.

Write the complete parameter declaration for each choice. Explain the cost and
the modification rule, then identify the choices that invoke copying.

## 2. Repair const correctness

Design a small `Song` interface containing `play`, `print`, `getTitle`, and
`getDuration`. Mark only the correct member functions as `const`.

Then declare a `const Song` and predict which calls compile. Explain why a
function receiving `const Song&` may call only `const` member functions, and
why the trailing `const` is part of the member-function declaration.

## 3. Recognize copy construction

Add a copy constructor to `Song` that prints a tracing message. For each line,
state whether it uses ordinary construction, copy construction, assignment, or
no copy:

```cpp
Song first("Imagine", "John Lennon", 183);
Song second(first);
Song third = first;
displaySong(first);
third = first;
```

Test `displaySong` once with a value parameter and once with a `const`
reference parameter. Explain the difference. Also explain why a function must
not return a reference to one of its local objects.

## 4. Use constructor initializer lists

Rewrite a constructor that assigns all data members inside its body so that it
uses an initializer list. Then create a class containing:

- a `const` identifier;
- a reference data member;
- a `Song` member that has no default constructor.

Explain why these members must be initialized before the constructor body.
Declare members in one order and deliberately list them in another order;
predict the real initialization order before compiling.

## 5. Work with static and inline members

Add a static counter that records how many `Song` objects have been created and
a static member function that returns the count. Demonstrate a call through the
class name rather than through an object.

Explain why the static function has no `this` pointer and cannot directly read
the title of a particular song. Define one short getter inside the class and
explain why it is implicitly `inline` without promising that the compiler will
actually replace the call.

## 6. Model composition and aggregation

Create these two relationships:

- an `Album` owns a `Song` as a direct data member;
- a `Playlist` refers to an existing `Song` owned elsewhere.

For each relationship, explain ownership, lifetime, and construction. Trace
what happens when the `Album` and `Playlist` are destroyed. State which example
is composition and which is aggregation.

## 7. Draw the music-library design in UML

Draw a UML class diagram for `Song`, `Album`, `Playlist`, and `MusicLibrary`.
Include important attributes and operations, visibility symbols, relationship
types, and multiplicities. Use the design decision that albums own their song
entries while playlists and the library refer to existing objects.

Check that the diagram communicates ownership clearly before writing code.

## 8. Integration challenge

Build a small fixed-capacity music library using separate header and source
files. It should register existing songs, albums, and playlists; search for a
song by title; and return an independent song copy from one operation.

Before implementing, write down:

- which parameters use references or `const` references;
- which operations are `const`;
- where copy construction occurs;
- which relationships express ownership and which do not.

Do not use STL containers yet; fixed-capacity arrays are sufficient for this
unit.

## Completion check

You should be able to justify parameter passing, apply const correctness,
identify copy construction, use initializer lists, explain static and inline
members, and model composition and aggregation in code and UML.
