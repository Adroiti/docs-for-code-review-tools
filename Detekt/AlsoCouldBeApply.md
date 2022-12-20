Pattern: `also` could be `apply`

Issue: -

## Description

Detects when an `also` block contains only `it`-started expressions.

By refactoring the `also` block to an `apply` block makes it so that all `it`s can be removed
thus making the block more concise and easier to read.

Example of **incorrect** code:

```kotlin
Buzz().also {
  it.init()
  it.block()
}
```

Example of **correct** code:

```kotlin
Buzz().apply {
  init()
  block()
}

// Also compliant
fun foo(a: Int): Int {
  return a.also { println(it) }
}
```

## Further Reading

* [Detekt - AlsoCouldBeApply](https://detekt.dev/style.html#alsocouldbeapply)