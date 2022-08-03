Pattern: Forbidden suppress

Issue: -

## Description

This rule allows to set a list of rules whose suppression is forbidden.
This can be used to discourage the abuse of the `Suppress` and `SuppressWarnings` annotations.
Detekt will report suppression of all forbidden rules.
This rule is not capable of reporting suppression of itself, as that's a language feature with precedence.

Example of **incorrect** code:

```kotlin
package foo

// When the rule "MaximumLineLength" is forbidden
@@Suppress("MaximumLineLength", "UNCHECKED_CAST")
class Bar
```

Example of **correct** code:

```kotlin
package foo

// When the rule "MaximumLineLength" is forbidden
@@Suppress("UNCHECKED_CAST")
class Bar
```

## Further Reading

* [Detekt - ForbiddenSuppress](https://detekt.dev/style.html#forbiddensuppress)