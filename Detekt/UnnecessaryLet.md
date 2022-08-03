Pattern: Unnecessary `let`

Issue: -

## Description

`let` expressions are used extensively in our code for null-checking and chaining functions, but sometimes their usage should be replaced with a ordinary method/extension function call to reduce visual complexity.

Example of **incorrect** code:

```kotlin
a.let { it.plus(1) } // can be replaced with a.plus(1)
a?.let { it.plus(1) } // can be replaced with a?.plus(1)
a.let { that -> that.plus(1) } // can be replaced with a.plus(1)
a?.let { that -> that.plus(1) } // can be replaced with a?.plus(1)
a?.let { that -> that.plus(1) }?.let { it.plus(1) } // can be replaced with a?.plus(1)?.plus(1)
```

Example of **correct** code:

```kotlin
a?.let { print(it) }
a.let { print(it) }
a?.let { msg -> print(msg) }
a.let { msg -> print(msg) }
a?.let { 1.plus(it) } ?.let { msg -> print(msg) }
a?.let { it.plus(it) }
a?.let { param -> param.plus(param) }
```

## Further Reading

* [Detekt - UnnecessaryLet](https://detekt.dev/docs/rules/style/#unnecessarylet)