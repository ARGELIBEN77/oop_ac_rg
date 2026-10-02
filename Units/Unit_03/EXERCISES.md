# Unit 3 — Constructors: Exercises

These exercises focus on giving every object a meaningful initial state. Follow
the lecture progression: assignments inside the constructor body and `this`
are sufficient. Member initializer lists and delegating constructors are not
required in this unit.

## 1. Explain the need for a constructor

Compare these two designs:

- create an object and then call several setter functions;
- provide the required values when the object is created.

Discuss when the object begins to exist, when it becomes usable, and who is
responsible for remembering every initialization step. Explain why a
constructor improves the design.

## 2. Implement a default constructor

Add a default constructor to `Song`. Choose valid placeholder values for its
title, artist, duration, and play count. Create an object without arguments and
print its state.

Explain when the constructor runs automatically and why it is not called like
an ordinary member function.

## 3. Overload constructors

Implement these three constructors:

```cpp
Song();
Song(std::string title);
Song(std::string title, std::string artist, int duration);
```

Create one object with each constructor and record the resulting state. Explain
how the compiler selects a constructor and why constructor overloading is
clearer than several differently named initialization functions.

## 4. Use `this` correctly

Begin with this incorrect assignment inside a constructor:

```cpp
title = title;
```

Correct it with `this->title`. Explain which `title` is the parameter, which is
the data member, and what `this` points to while the constructor is running.

## 5. Validate construction arguments

Extend the parameterized constructor so that:

- a negative duration becomes `0`;
- the play count begins at `0`.

Test a positive duration, `0`, and a negative duration. Explain how validation
during construction supports encapsulation and prevents an impossible state.

## 6. Optional extension: forbid default construction

Replace the default constructor with:

```cpp
Song() = delete;
```

Show the statement that now fails to compile. Explain when forbidding default
construction is better than inventing placeholder values.

## Completion check

You should be able to explain the purpose of constructors, implement default
and parameterized constructors, use overloading and `this`, validate arguments,
and decide whether default construction is appropriate.
