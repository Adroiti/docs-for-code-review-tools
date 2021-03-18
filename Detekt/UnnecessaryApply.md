Pattern: Unnecessary `apply`

Issue: -

## Description

`apply` expressions are used frequently, but sometimes their usage should be replaced with an ordinary method/extension function call to reduce visual complexity.

Example of **incorrect** code:

```kotlin
config.apply { version = "1.2" } // can be replaced with config.version = "1.2"
config?.apply { environment = "test" } // can be replaced with config?.environment = "test"
```

Example of **correct** code:

```kotlin
config.apply {
    version = "1.2"
    environment = "test"
}
```

## Further Reading

* [Detekt - UnnecessaryApply](https://detekt.github.io/detekt/style.html#unnecessaryapply)