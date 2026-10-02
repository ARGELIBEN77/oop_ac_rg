# Unit 9 — Exception Handling: Exercises

These exercises separate failure detection from the response to failure. For
every example, trace both the normal path and the exceptional path. Catch
exception objects by `const` reference and explain where handling belongs.

## 1. Trace a complete try–catch

Implement `MusicLibrary::getTitle(int index)` so that it throws
`std::out_of_range` for an invalid index. Call it twice inside one `try` block:
first with a valid index and then with an invalid index.

Predict every printed line. Mark which statements after `throw` are skipped,
where execution resumes, and why execution does not return to the throwing
statement after the handler.

## 2. Choose a standard exception type

For each failure, choose `std::invalid_argument`, `std::out_of_range`, or
`std::runtime_error` and justify the category:

- a negative duration supplied to an operation;
- an invalid playlist position;
- an audio source that becomes unavailable while playing.

Throw each exception with a useful message, catch it by `const` reference, and
display the result of `what()`.

## 3. Trace propagation

Create the call chain `main` → `printTitleAt` → `getTitle`. Let `getTitle`
throw, give `printTitleAt` no handler, and catch the exception in `main`.

Draw the active call stack at the throwing point. Explain how C++ searches for
a compatible handler and what happens if no matching handler exists.

## 4. Observe stack unwinding

Create a `PlaybackSession` object that prints from its constructor and
destructor. Construct it inside a function that then throws
`std::runtime_error`.

Predict the order of construction, destruction, and handler output. Explain
why the destructor runs before the handler and how this connects exception
handling to automatic object cleanup.

## 5. Order specific and general handlers

Write handlers for `std::out_of_range`, `std::runtime_error`, and
`std::exception`. Place them in the correct order and explain why C++ selects
the first compatible handler.

Then reverse a specific and general handler. Record the compiler warning or
behavior and explain why the general handler makes the later one unreachable.

## 6. Define a domain-specific exception

Define `PlaybackError` as a class derived from `std::runtime_error`. Throw it
when a song exists but cannot access its audio source.

Catch it once specifically as `PlaybackError` and once through a
`std::exception` reference. Explain what is inherited and when the custom type
adds more meaning than a standard exception alone.

## 7. Catch where recovery is possible

Build a `MusicLibrary::playAll()` loop containing playable and unavailable
items. Catch `PlaybackError` inside the loop so one unavailable item is skipped
and later items still play. Handle an invalid application-level selection in
`main` with `std::out_of_range`.

Explain why these handlers belong at different levels and why catching an
exception only to hide it is a poor design.

## 8. Decide between return and throw

Compare these two operations:

- `add`, where a full fixed-capacity library is an expected outcome that the
  caller routinely checks;
- `at`, which promises to return a valid item reference but receives an
  invalid index.

Decide which should return `false` and which should throw. State a general rule
for choosing between an ordinary return value and an exception.

## 9. Find the beginner mistakes

Review a short program containing these mistakes: throwing a string, catching
by value, placing `catch (const std::exception&)` first, using an empty catch
block, and expecting execution to resume after `throw`.

Correct each mistake and explain the underlying rule. Also explain why a
destructor should not throw while another exception may already be propagating.

## Completion check

You should be able to trace normal and exceptional paths, choose a meaningful
exception type, use `what()`, explain propagation and stack unwinding, order
handlers, define a custom exception, and catch failures where recovery is
possible.
