Pattern: Boolean method returns `null`

Issue: -

## Description

Checks for a method with `Boolean` return type that returns an explicit `null`. A method that returns either `Boolean.TRUE`, `Boolean.FALSE` or `null` is an accident waiting to happen. This method can be invoked as though it returned a value of type `boolean`, and the compiler will insert automatic *unboxing* of the `Boolean` value. If a `null` value is returned, this will result in a `NullPointerException`.

## Further Reading

* [CodeNarc - BooleanMethodReturnsNull](https://codenarc.github.io/CodeNarc/codenarc-rules-design.html#booleanmethodreturnsnull-rule)