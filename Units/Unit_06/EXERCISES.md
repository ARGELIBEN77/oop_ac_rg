# Unit 6 — Operator Overloading and the Rule of Three: Exercises

The goal is to make user-defined types behave naturally without hiding their
meaning. For every operator, state the expected behavior, return type, and
whether it should be a member or non-member. For every class that owns dynamic
memory, draw the owned resource before and after copying or assignment.

## 1. Decide whether an operator is meaningful

For each proposal, decide whether overloading improves the interface or makes
the code misleading:

- compare two songs by title and artist;
- add two playlists to produce a combined playlist;
- multiply two customers;
- use `[]` to access a playlist entry;
- call a playlist like a function to count songs by an artist.

Explain the meaning a reader would reasonably expect. Also name three C++
operators that cannot be overloaded.

## 2. Build consistent comparisons

Implement `==`, `!=`, `<`, `<=`, `>`, and `>=` for `Song`. First define what
makes two songs equal and which property determines ordering. Then reuse the
core operators instead of repeating comparison logic.

Test equal songs, unequal songs, and two songs for which neither is less than
the other. Explain why equality and ordering must be consistent.

## 3. Choose member, non-member, and friend forms

Implement `==` and `+` for a `Fraction` class. Compare a member implementation
with a non-member implementation and discuss symmetry and implicit conversion
of the left operand.

Use `friend` only if the non-member function genuinely needs direct access to
private data. Explain why friendship is a controlled design choice rather than
a replacement for encapsulation.

## 4. Implement stream operators

Add `operator<<` and `operator>>` for one of your classes. Demonstrate chained
output and chained input.

Explain:

- why the stream is the left operand;
- why these operators are non-members;
- why they return `std::ostream&` or `std::istream&`;
- when declaring them as friends is justified.

## 5. Reuse arithmetic and compound assignment

Implement `Playlist::operator+=` and use it to implement `operator+`. Add
`operator-=` and `operator-` with a clearly documented meaning for removal.

Verify that compound assignment modifies its left operand while the binary
operator returns a new object. Test chained assignment and explain why compound
assignment returns a reference to `*this`.

## 6. Implement the Rule of Three

Create a `Playlist` or `IntBuffer` that owns a dynamically allocated array.
Implement:

- the destructor;
- the copy constructor;
- the copy assignment operator.

Test independence after copying, assignment between different-sized objects,
self-assignment, and destruction. Explain exactly why the compiler-generated
memberwise copy would cause shared ownership, double deletion, or dangling
pointers.

## 7. Provide checked element access

Add const and non-const `operator[]` overloads to the owning class from
Exercise 6. Return references so that one overload permits modification and the
other supports read-only access.

Choose and document a response to an invalid index. Demonstrate valid reading,
valid writing, and an invalid access. Explain why returning by value would not
support natural assignment syntax.

## 8. Use the function-call operator

Implement `Playlist::operator()` so that one version counts songs by artist and
another counts songs by artist above a minimum duration. Explain why the
operation makes sense for a callable object and when a named function would be
clearer.

## 9. Compare prefix and postfix operators

For `Fraction`, implement unary `+`, unary `-`, prefix and postfix `++`, and
prefix and postfix `--`. Trace the value returned and the state left behind by
each expression.

Explain the purpose of the dummy `int` parameter in the postfix form and why
prefix returns a reference while postfix returns the saved old value.

## 10. Optional extension: explicit conversion

Add an explicit conversion from `Fraction` to `double`. Demonstrate a legal
explicit conversion and a statement that would be rejected because the
conversion is not implicit. Explain how `explicit` prevents surprising code.

## Completion check

You should be able to design consistent operators, choose member, non-member,
or friend implementations, use correct return types, implement independent
deep copies, and explain subscript, function-call, unary, and conversion
operators.
