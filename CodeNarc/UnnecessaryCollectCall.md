Pattern: Unnecessary `Object.collect()` call

Issue: -

## Description

Some method calls to `Object.collect(Closure)` can be replaced with the spread operator. For instance, `list.collect  it.multiply(2) ` can be replaced by `list*.multiply(2)`.

Examples of violations include:

``` groovy
assert [1, 2, 3].collect { it.multiply(2) }
assert [1, 2, 3].collect { x -> x.multiply(2) }
["1", "2", "3"].collect { it.bytes }
```

The following code does not produce violations:

``` groovy
[1, 2, 3].collect { it * it }   // OK, closure parameter is referenced twice

[1, 2, 3].mapMethod { it.multiply(5) } // OK, method call is not collect

[1, 2, 3].collect(5) // OK, collect parameter is not a closure

// OK, the closure is not a simple one line statement
[1, 2, 3].collect { println it; it.multiply(5) }

// OK, closure has too many arguments
[1, 2, 3].collect { a, b -> a.multiply(b) }

// OK, closure statement references parameter multiple times
[1, 2, 3].collect { it.multiply(it) }

// OK, it is referenced several times in the closure
[1, 2, 3].collect { it.multiply(2).multiply(it) }
["1", "2", "3"].collect { it.bytes.foo(it) }

// OK, chained methods are too complex to analyze at this point
[1, 2, 3].collect { it.multiply(2).multiply(4) }

// in general the above examples can be rewritten like this:
[1, 2, 3]*.multiply(2)
["1", "2", "3"]*.bytes
```

## Further Reading

* [CodeNarc - UnnecessaryCollectCall](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryCollectCall)