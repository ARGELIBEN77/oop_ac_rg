# Unit 5 — Objects and Relationships: Exercises

Treat each exercise as a design decision, not only a syntax task. Your answer
should identify ownership, lifetime, and whether an operation may modify an
argument. UML answers must include class names, important members,
relationships, and multiplicities. Code answers should demonstrate the chosen
relationships in a small scenario.

## 1. Choose parameter forms

Choose value, reference, or `const` reference for each parameter and justify
the choice: printing a `Customer`, applying a discount to a `Product`, storing
a small integer identifier, and replacing a `Playlist` supplied by the caller.

## 2. Static class data

Implement an `Employee` class that assigns each new object a unique numeric
identifier. Use a static data member to generate identifiers and a static
observer that reports how many identifiers have been issued.

## 3. Model relationships

Draw a UML class diagram for `Order`, `OrderLine`, `Product`, and `Customer`.
Show multiplicities and classify each connection as association, aggregation,
or composition. Add one sentence explaining the lifetime decision behind each
whole–part relationship.

## 4. Build a collaboration

Implement a small `Library` that stores `Book` objects and searches by title.
Use a separate `Member` class without making the library own its members.
Demonstrate at least one operation involving both classes.

## 5. Optional extension

Return one object from a function by value and one by reference. Explain the
lifetime requirement that makes the reference-returning version safe.

## Completion check

You should be able to justify parameter passing and model relationships from
their meaning and lifetime—not merely from the shape of the code.
