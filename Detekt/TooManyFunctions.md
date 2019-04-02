Pattern: Too many functions

Issue: -

## Description

Too many functions indicate a violation of the single responsibility principle. Prefer extracting functionality which clearly belongs together in separate parts of the code.

This rule reports files, classes, interfaces, objects and enums which contain too many functions. Each element can be configured with different thresholds.

## Further Reading

* [Detekt - TooManyFunctions](https://arturbosch.github.io/detekt/complexity.html#toomanyfunctions)