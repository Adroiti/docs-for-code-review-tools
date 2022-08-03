Pattern: Explicit `it` lambda parameter

Issue: -

## Description

Lambda expressions are one of the core features of the language. They often include very small chunks of
code using only one parameter. In this cases Kotlin can supply the implicit `it` parameter
to make code more concise. It fits most use cases, but when faced with larger or nested chunks of code,
you might want to add an explicit name for the parameter. Naming it just `it` is meaningless and only
makes your code misleading, especially when dealing with nested functions.

Example of **incorrect** code:

```kotlin
a?.let { it -> it.plus(1) }
foo.flatMapObservable { it -> Observable.fromIterable(it) }
listOfPairs.map(::second).forEach { it ->
		it.execute()
}
collection.zipWithNext { it, next -> Pair(it, next) }
```

Example of **correct** code:

```kotlin
a?.let { it.plus(1) } // Much better to use implicit it
foo.flatMapObservable(Observable::fromIterable) // Here we can have a method reference
listOfPairs.map(::second).forEach { apiRequest -> // For multiline blocks it is usually better come up with a clear and more meaningful name
		apiRequest.execute()
}
collection.zipWithNext { prev, next -> // Lambdas with multiple parameter should be named clearly, using it for one of them can be confusing
		Pair(prev, next)
}
```

## Further Reading

* [Detekt - ExplicitItLambdaParameter](https://detekt.dev/docs/rules/style/#explicititlambdaparameter)