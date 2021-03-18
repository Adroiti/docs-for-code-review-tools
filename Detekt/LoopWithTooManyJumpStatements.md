Pattern: Loop with too many jump statements

Issue: -

## Description

Loops which contain multiple `break` or `continue` statements are hard to read and understand. To increase readability they should be refactored into simpler loops.

Example of **incorrect** code:

```kotlin
val strs = listOf("foo, bar")
for (str in strs) {
    if (str == "bar") {
        break
    } else {
        continue
    }
}
```

## Further Reading

* [Detekt - LoopWithTooManyJumpStatements](https://detekt.github.io/detekt/style.html#loopwithtoomanyjumpstatements)