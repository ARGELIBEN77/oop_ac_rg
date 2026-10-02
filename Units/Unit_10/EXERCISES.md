# Unit 10 — Templates and Iterators: Exercises

## 1. State template requirements — 15 minutes

Write a `maximum<T>` function template. State exactly which operation `T` must
support. Test it with `int`, `double`, and one user-defined type.

## 2. Build a class template — 35 minutes

Implement a fixed-capacity `PairBox<T>` that stores two values, provides const
and non-const access, and swaps the values. Instantiate it with two unrelated
types.

## 3. Complete a simple iterator — 45 minutes

Add `begin()` and `end()` to a small linked collection. Its iterator must
support dereference, pre-increment, and inequality—only the operations required
by the supplied loop. Demonstrate a range-based `for` loop.

## 4. Generic search — 30 minutes

Write `findFirst(begin, end, predicate)` without using
`std::iterator_traits`. Test it with a named functor and a capturing lambda.
State what the iterator and predicate must support.

## 5. Optional extension — 25 minutes

Implement a const iterator or explain precisely what would be required to
prevent modification through iteration.

