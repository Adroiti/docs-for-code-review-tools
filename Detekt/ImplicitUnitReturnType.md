Pattern: Use of implicit unit return type

Issue: -

## Description

Functions using expression statements have an implicit return type.
Changing the type of the expression accidentally changes the functions return type.
This may lead to backward incompatibility.
Use a block statement to make clear this function will never return a value.

Example of **incorrect** code:

```kotlin
fun errorProneUnit() = println("Hello Unit")
fun errorProneUnitWithParam(param: String) = param.run { println(this) }
fun String.errorProneUnitWithReceiver() = run { println(this) }
```

Example of **correct** code:

```kotlin
fun blockStatementUnit() {
    // code
}

// explicit Unit is compliant by default; can be configured to enforce block statement
fun safeUnitReturn(): Unit = println("Hello Unit")
```

## Further Reading

* [Detekt - ImplicitUnitReturnType](https://detekt.dev/potential-bugs.html#implicitunitreturntype)