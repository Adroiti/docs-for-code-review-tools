Pattern: Use of redundant visibility modifier

Issue: -

## Description

Redundant visibility modifiers can be safely removed.

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

* [Detekt - RedundantVisibilityModifierRule](https://detekt.github.io/detekt/style.html#redundantvisibilitymodifierrule)