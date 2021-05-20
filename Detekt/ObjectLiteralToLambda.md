Pattern: Missing use of anonymous object as lambda

Issue: -

## Description

An anonymous object that does nothing other than the implementation of a single method can be used as a lambda.

Example of **incorrect** code:

```java
object : Foo {
    override fun bar() {
    }
}
```

Example of **correct** code:

```java
Foo {
}

```

## Further Reading

* [Detekt - ObjectLiteralToLambda](https://detekt.github.io/detekt/style.html#objectliteraltolambda)