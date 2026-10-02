# Unit 4 — Object Lifetime and Destructors: Exercises

These exercises develop the ability to reason about when local objects are
created and destroyed. Predict every trace before running it. After running the
program, explain the rule behind the result instead of recording only the
output.

## 1. Trace one scope

Use this class:

```cpp
class Marker {
private:
    std::string label;

public:
    Marker(std::string label) {
        this->label = label;
        std::cout << "construct " << label << '\n';
    }

    ~Marker() {
        std::cout << "destroy " << label << '\n';
    }
};
```

Create `Marker first("first")` and then `Marker second("second")` in `main`.
Write the exact four output lines and explain why destruction occurs in the
reverse of construction order.

## 2. Follow a nested scope

Add a block between the two declarations from Exercise 1. Inside the block,
create `Marker inner("inner")`.

Predict the complete trace. Mark the exact point at which `inner` is destroyed
and explain why execution then continues in the outer scope.

## 3. Trace a function call and an early return

Write a function that creates two local `Marker` objects. Let the function
return early when a Boolean parameter is true. Call it once with `true` and
once with `false`.

Before running the program, predict which destructors execute on each path.
Explain what this demonstrates about scope and early return.

## 4. Check destructor rules

For each declaration, state whether it is a legal destructor and explain why:

```cpp
~Song();
~Song(std::string message);
void ~Song();
~Album();
```

State how many destructors one class may have, whether a destructor has a
return type, and whether it accepts parameters.

## 5. Trace composition

Define a `Song` class whose constructor and destructor print the song title.
Then define an `Album` class containing two `Song` data members. Its constructor
and destructor should also print messages.

Create one `Album` and predict the complete trace. Explain:

- why both songs are constructed before the `Album` constructor body runs;
- why the `Album` destructor body runs before its songs are destroyed;
- why the two songs are destroyed in reverse declaration order.

## 6. Do not call a destructor manually

Consider this code:

```cpp
Song song("Imagine");
song.~Song();
```

Explain why the explicit destructor call is dangerous when `song` will also
reach the end of its scope. Rewrite the client code correctly.

## 7. Connect lifetime to cleanup

The current `Song` class owns no external resource, so its destructor may have
nothing to release. Suppose a future class owns a file or dynamically allocated
memory. Explain:

1. why cleanup belongs in the destructor;
2. why automatic destructor execution is safer than relying on the caller;
3. what later course topic must be learned before implementing dynamic-memory
   ownership correctly.

This is a conceptual preview only; do not implement dynamic allocation yet.

## Completion check

You should be able to predict destruction at scope exit and early return,
state the syntax rules for destructors, and trace the lifetime of composed
objects without relying on program output.
