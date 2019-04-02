Pattern: Malformed space between `package`/`import`/`class`

Issue: -

## Description

This rule verifies spacing between `package` and `import` statements as well as between `import` statements and `class` declarations.

Example of **incorrect** code:

```kotlin
package foo
import a.b
class Bar { }
```

Example of **correct** code:

```kotlin
package foo

import a.b

class Bar { }
```

## Further Reading

* [Detekt - SpacingBetweenPackageAndImports](https://arturbosch.github.io/detekt/style.html#spacingbetweenpackageandimports)