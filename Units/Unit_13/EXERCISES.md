# Unit 13 — Course Integration: Exercises

Use these short exercises between the two practice examinations.
They focus on testing, changing requirements, and explaining design decisions.

Use C++17. For each programming exercise, submit complete compilable code,
tests, and a short explanation. Write predictions before running experiments.

## 1. Test the tests — Copy independence

Use your completed Playlist from Practice Examination 1.

Write separate tests for:
- copy construction;
- assignment between playlists of different sizes;
- assignment from an empty playlist;
- self-assignment;
- using a copy after the original has been destroyed.

For each test, state which incorrect implementation it should detect.
Temporarily introduce one shallow-copy error and identify the test that detects
it. Run this deliberately faulty version separately: it may access freed memory
or attempt to delete the same array twice. Restore the correct implementation
before continuing.

Do not treat a successful run alone as proof that ownership is correct.

## 2. Extend an operator contract

Create a Duration class storing a non-negative number of seconds.
Reject a negative constructor argument with std::invalid_argument.
Use small values; overflow handling is outside this exercise.

Implement += and + so that:
- += modifies the left operand and returns Duration&;
- + returns a new value and leaves both operands unchanged;
- + reuses += rather than repeating the addition logic.

Provide a const observer for the stored seconds. Test:
- addition involving const objects;
- adding zero;
- a += a;
- (a += b) += c;
- independence of the result returned by +;
- rejection of a negative constructor argument.

Explain why returning a reference to a local result from + is invalid.

## 3. Investigate failed construction

Define a Trace class that prints its name during construction and destruction.

Define a Session containing, in this declaration order:
- a Trace member named first;
- a unique_ptr<Trace> member named second.

Initialize both members, then throw std::runtime_error from the Session
constructor body. Give Session a destructor that also prints a message.

Catch the exception in main.

Predict and verify:
- which constructors finish;
- which destructors run and in what order;
- whether Session's destructor runs.

Explain how the initialized members are cleaned up when construction fails.
Do not assume that a destructor runs for an object whose construction failed.

## 4. Change resource management without changing behavior

Take your correct Playlist implementation from Practice Examination 1.
Create a second version using vector<string> instead of an owning raw array.

Preserve its public operations and their documented behavior, including:
- independent copies;
- checked indexing;
- equality based on names and order.

Adapt internal storage without adding new features.

Run the same behavioral tests against both versions.
Identify which special member functions can now be omitted and explain why.

## 5. Diagnose an observer's lifetime

A library exclusively owns Song objects in a vector<unique_ptr<Song>>.
A selected song is observed through a const Song* obtained with get().

Create a small experiment that:
1. selects an existing song;
2. appends another song;
3. removes the selected song.

Explain separately what happens to:
- the pointer to the Song object;
- an iterator into the vector;
- a reference to a unique_ptr element in the vector.

Distinguish appending with and without reallocation. For erasure, distinguish
positions before, at, and after the erased element.
Appending may reallocate the vector, but it does not move the owned Song.
Do not dereference invalid iterators, references, or an observer after its Song
has been destroyed.

Add an erase operation that clears the selection before deleting the selected
song. Test removal of selected and unselected songs.

## 6. Specify and test a generic boundary

Implement:

```cpp
template <typename Iterator, typename Predicate>
bool allMatch(Iterator first, Iterator last, Predicate predicate);
```

Do not use std::all_of. Stop as soon as an element fails the predicate.
For an empty range, return true.

Test:
- an empty range;
- a range in which every element matches;
- failure at the first element;
- failure at the last element;
- vector<int> and list<string>.

Use a predicate with a call counter to verify early termination.
State the operations required from the iterator and the predicate.

## Completion check

For every correction, explain:
- the requirement being preserved;
- the C++ rule involved;
- the test that would detect the original mistake.

Continue with the practice strategy and use the review bank for topics that
still need work.

- [Practice strategy](PRACTICE_STRATEGY.md)
- [Complete-course review bank](REVIEW_QUESTION_BANK.md)
- [Unit resources](README.md)
