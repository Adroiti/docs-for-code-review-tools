Pattern: Class has too many lines

Issue: -

## Description

Classes should generally have one responsibility. Large classes can indicate that
the class does instead handle multiple responsibilities. Instead of doing many things at once prefer to
split up large classes into smaller classes. These smaller classes are then easier to understand and handle less
things.

## Further Reading

* [Detekt - LargeClass](https://detekt.github.io/detekt/complexity.html#largeclass)