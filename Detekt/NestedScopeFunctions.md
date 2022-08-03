Pattern: Use of nested scope function

Issue: -

## Description

Although the scope functions are a way of making the code more concise, avoid overusing them. It can decrease
your code readability and lead to errors. Avoid nesting scope functions and be careful when chaining them. It's easy to get confused about the current context object and the value of this or it.

Example of **incorrect** code:

```kotlin
// Try to figure out, what changed, without knowing the details
first.apply {
    second.apply {
        b = a
        c = b
    }
}
```

Example of **correct** code:

```kotlin
// 'a' is a property of current class
// 'b' is a property of class 'first'
// 'c' is a property of class 'second'
first.b = this.a
second.c = first.b
```

## Further Reading

* [Detekt - NestedScopeFunctions](https://detekt.dev/docs/rules/complexity/#nestedscopefunctions)