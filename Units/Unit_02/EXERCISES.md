# Unit 2 — From Struct to Class: Exercises

These exercises practise the transition from a public `struct` to a class that
combines data and behavior. Constructors and `const` member functions are not
required yet. For programming tasks, submit a header, an implementation file,
and a small `main` that demonstrates the requested behavior.

## 1. Find invalid states

Consider this public structure:

```cpp
struct Song {
    std::string title;
    std::string artist;
    int duration;
    int plays;
};
```

Write four statements that are legal C++ but leave a `Song` in a state that is
invalid for the application. Explain why the compiler accepts each statement
and why the application should not.

## 2. Compare parameter passing

Write three small functions that receive a `Song` by value, by pointer, and by
reference. Each function should attempt to increase the play count. Begin with
a play count of `5`, predict the value after each call, and then run the code.

Explain the result using the ideas of copying, addresses, and references. Also
describe how the call syntax differs for the three versions.

## 3. Move behavior into a class

Replace the public structure with a `Song` class that has private data and this
public behavior:

- play the song by increasing its play count;
- print the song details;
- change the duration only when the new value is not negative.

Demonstrate one accepted and one rejected duration change. Your `main` must not
access data members directly. Finally, identify one remaining weakness: the
object can still exist before meaningful values have been supplied. Unit 3
will address that problem.

## 4. Separate interface and implementation

Organize the class from Exercise 3 into `Song.h`, `Song.cpp`, and `main.cpp`.
Label each file as interface, implementation, or client code. Explain what a
user of the class needs to know and what can remain hidden.

## 5. Distinguish a class from an object

In your own words, explain the difference between a class and an object. Write
statements that create three separate `Song` objects and identify which part is
the class name and which parts are object names. Then explain why these objects
should eventually hold independent state, even though the class describes all
three of them.

Do not try to print their data yet: without constructors, their primitive data
members do not begin with predictable values. Explain how this limitation
motivates the next unit.

## Completion check

You should be able to explain the weakness of public data, compare pass by
value, pointer, and reference, distinguish a class from an object, recognize the
initialization problem, and separate a class declaration from its implementation.
