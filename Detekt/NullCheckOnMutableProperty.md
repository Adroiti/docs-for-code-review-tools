Pattern: Use of null-check on mutable property

Issue: -

## Description

Reports null-checks on mutable properties, as these properties' value can be
changed and thus make the null-check invalid after the execution of the if-statement.

Example of **incorrect** code:

```kotlin
class A(private var a: Int?) {
  fun foo() {
    if (a != null) {
      println(2 + a!!)
    }
  }
}
```

Example of **correct** code:

```kotlin
class A(private val a: Int?) {
  fun foo() {
    if (a != null) {
      println(2 + a)
    }
  }
}
```

## Further Reading

* [Detekt - NullCheckOnMutableProperty](https://detekt.dev/docs/rules/potential-bugs/#nullcheckonmutableproperty)