Pattern: Method has too many lines

Issue: -

## Description

Methods should have one responsibility. Long methods can indicate that a method handles too many cases at once.
Prefer smaller methods with clear names that describe their functionality clearly.

Extract parts of the functionality of long methods into separate, smaller methods.

## Further Reading

* [Detekt - LongMethod](https://arturbosch.github.io/detekt/complexity.html#longmethod)