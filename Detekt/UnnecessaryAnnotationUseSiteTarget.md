Pattern: Unnecessary annotation use-site Target

Issue: -

## Description

This rule inspects the use of the Annotation use-site Target. In case that the use-site Target is not needed it can be removed. 

Example of **incorrect** code:

```kotlin@@property:Inject private val foo: String = "bar" // violation: unnecessary @property:class Module(@param:Inject private val foo: String) // violation: unnecessary @param:```
Example of **correct** code:

```kotlinclass Module(@Inject private val foo: String)```

## Further Reading

* [Detekt - UnnecessaryAnnotationUseSiteTarget](https://arturbosch.github.io/detekt/style.html#unnecessaryannotationusesitetarget)