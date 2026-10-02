# Unit 10 — Templates and Iterators: Exercises

For every template, write down the operations required from its type or
iterator arguments. Do not use advanced library machinery when the exercise
asks for a simple educational implementation. Code answers should include at
least two substantially different template instantiations and tests of empty,
single-element, and multi-element ranges where relevant.

## 1. State template requirements

Write a `maximum<T>` function template. State exactly which operation `T` must
support. Test it with `int`, `double`, and one user-defined type.

## 2. Build a class template

Implement a fixed-capacity `PairBox<T>` that stores two values, provides const
and non-const access, and swaps the values. Instantiate it with two unrelated
types.

## 3. Complete a simple iterator

Add `begin()` and `end()` to a small linked collection. Its iterator must
support dereference, pre-increment, and inequality—only the operations required
by the supplied loop. Demonstrate a range-based `for` loop.

## 4. Generic search

Write `findFirst(begin, end, predicate)` without using
`std::iterator_traits`. Test it with a named functor and a capturing lambda.
State what the iterator and predicate must support.

## 5. Optional extension

Implement a const iterator or explain precisely what would be required to
prevent modification through iteration.

## Completion check

You should be able to describe template requirements, implement the small
iterator interface actually used by a loop, and pass behavior into a generic
algorithm using either a functor or a lambda.
