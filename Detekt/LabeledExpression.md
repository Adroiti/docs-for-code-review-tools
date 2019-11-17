Pattern: Use of labeled expression

Issue: -

## Description

Expressions with labels generally increase complexity and worsen the maintainability of the code. Refactor the violating code to not use labels instead. Labeled expressions referencing an outer class with a label from an inner class are allowed, because there is no way to get the instance of an outer class from an inner class in Kotlin.

Example of **incorrect** code:

```kotlin
val range = listOf<String>("foo", "bar")
loop@ for (r in range) {
    if (r == "bar") break@loop
    println(r)
}

class Outer {
    inner class Inner {
        fun f() {
            val i = this@Inner // referencing itself, use this instead
        }
    }
}
```

Example of **correct** code:

```kotlin
val range = listOf<String>("foo", "bar")
for (r in range) {
    if (r == "bar") break
    println(r)
}

class Outer {
    inner class Inner {
        fun f() {
            val outer = this@Outer
        }
        fun Int.extend() {
            val inner = this@Inner // this would reference Int and not Inner
        }
    }
}
```

## Further Reading

* [Detekt - LabeledExpression](https://arturbosch.github.io/detekt/complexity.html#labeledexpression)