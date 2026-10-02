# Unit 4 — Object Lifetime and Destructors

This unit follows local objects from construction through scope exit and
automatic destruction.

## Learning outcomes

After completing this unit, you should be able to:

- explain when and why a destructor runs;
- predict construction and destruction order in nested scopes and functions;
- explain destruction during an early return;
- state the syntax rules for destructors;
- trace the lifetime of member objects in composition.

## Main ideas

- Object lifetime and scope
- Destructor syntax and responsibilities
- Automatic execution and reverse construction order
- Early return and multiple local objects
- Lifetime of composed objects
- Why destructors must not be called manually

## Study resources

- [Lecture](Unit_4_OOP_Destructors.pdf)
- [Focused lifetime exercises](EXERCISES.md)
- [Song Class Fundamentals](../../Song_Class_Fundamentals/README.md)

Predict every trace on paper before compiling it. The purpose is to learn to
reason about lifetime, not merely to copy the program's output.

Dynamic-memory ownership and the Rule of Three begin in Unit 6.
