Pattern: Public nested class

Issue: -

## Description

Nested classes are often used to implement functionality local to the class it is nested in. Therefore it should not be public to other parts of the code. Prefer keeping nested classes `private`.

Example of **incorrect** code:

```kotlin
internal class NestedClassesVisibility {

    public class NestedPublicClass // should not be public
}
```

Example of **correct** code:

```kotlin
internal class NestedClassesVisibility {

    internal class NestedPublicClass
}
```

## Further Reading

* [Detekt - NestedClassesVisibility](https://detekt.dev/docs/rules/style/#nestedclassesvisibility)