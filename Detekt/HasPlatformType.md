Pattern: Implicit platform type

Issue: -

## Description

Platform types must be declared explicitly in public APIs to prevent unexpected errors.
Example of **incorrect** code:

```kotlinclass Person {  fun apiCall() = System.getProperty("propertyName")}```
Example of **correct** code:

```kotlinclass Person {  fun apiCall(): String = System.getProperty("propertyName")}```

## Further Reading

* [Detekt - HasPlatformType](https://detekt.github.io/detekt/potential-bugs.html#hasplatformtype)