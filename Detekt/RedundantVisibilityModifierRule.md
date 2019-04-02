Pattern: Use of redundant visibility modifier

Issue: -

## Description

This rule checks for redundant visibility modifiers.

Example of **incorrect** code:

```kotlin
public interface Foo { // public per default

    public fun bar() // public per default
}
```

Example of **correct** code:

```kotlin
interface Foo {

    fun bar()
}
```

## Further Reading

* [Detekt - RedundantVisibilityModifierRule](https://arturbosch.github.io/detekt/style.html#redundantvisibilitymodifierrule)