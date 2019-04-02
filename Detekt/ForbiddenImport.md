Pattern: Use of forbidden import

Issue: -

## Description

This rule allows to set a list of forbidden imports. This can be used to discourage the use of unstable, experimental
or deprecated APIs. Detekt will then report all imports that are forbidden.

Example of **incorrect** code:

```kotlin
package foo
import kotlin.jvm.JvmField
import kotlin.SinceKotlin
```

## Further Reading

* [Detekt - ForbiddenImport](https://arturbosch.github.io/detekt/style.html#forbiddenimport)