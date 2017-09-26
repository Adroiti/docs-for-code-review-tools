Pattern: Random `double` coerced to zero

Issue: -

## Description

The `Math.random()` method returns a `double` result greater than or equal to 0.0 and less than 1.0. If you coerce this result into an `Integer`, `Long`, `int`, or `long` then it is coerced to zero. Casting the result to `int`, or assigning it to an `int` field is probably a bug.

Example of violations:

``` groovy
(int) Math.random()
(Integer) Math.random()
int x = Math.random()
Integer y = Math.random()
int m() { Math.random() }
Integer m() { Math.random() }
(Math.random()) as int
(Math.random()) as Integer
```

## Further Reading

* [CodeNarc - RandomDoubleCoercedToZero](http://codenarc.sourceforge.net/codenarc-rules-basic.html#RandomDoubleCoercedToZero)