# Unit 11 — Smart Pointers and Move Semantics: Exercises

## 1. Choose an ownership model — 15 minutes

Choose `unique_ptr`, `shared_ptr`, or a non-owning reference for four
relationships: library–book, playlist–track, employee–department, and
application–configuration. State who destroys the object in each design.

## 2. Trace a unique transfer — 20 minutes

Create a `unique_ptr<Song>`, move it into a second pointer, and pass ownership
into a function. After every step, state which pointer owns the object and
which pointers are empty.

## 3. Trace shared ownership — 25 minutes

Create a `shared_ptr<Album>` and copy it into a vector and a local variable.
Record the expected `use_count()` after each operation and identify the exact
point at which the album is destroyed.

## 4. Implement a simplified unique pointer — 45 minutes

Implement `UniquePointer<T>` with construction from `T*`, destruction,
deleted copy operations, move construction, move assignment, `operator*`,
`operator->`, and `get`. Test transfer and destruction.

## 5. Optional extension — 30 minutes

Describe the control block required by a simplified `SharedPointer<T>`.
Implement either copy construction or destruction and explain how the two
operations preserve the reference count.

