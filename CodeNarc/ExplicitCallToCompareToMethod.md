Pattern: Explicit call to `compareTo()`

Issue: -

## Description

This rule detects when the `compareTo(Object)` method is called directly in code instead of using the &lt;=&gt;, &gt;, &gt;=, &lt;, and &lt;= operators. A groovier way to express this: `a.compareTo(b)` is this: `a <=> b`, or using the other operators. Here are some other ways to write groovier code:

``` groovy
a.compareTo(b) == 0               // can be replaced by: a == b
a.compareTo(b)                    // can be replaced by: a <=> b
a.compareTo(b) > 0                // can be replaced by: a > b
a.compareTo(b) >= 0               // can be replaced by: a >= b
a.compareTo(b) < 0                // can be replaced by: a < b
a.compareTo(b) <= 0               // can be replaced by: a <= b
```

This rule can be configured to ignore `this.compareTo(Object)` using the *ignoreThisReference* property. It defaults to `false`, so even `compareTo(x)` will trigger a violation.

This rule also ignores all calls to `super.compareTo(Object)`.

## Further Reading

* [CodeNarc - ExplicitCallToCompareToMethod](http://codenarc.sourceforge.net/codenarc-rules-groovyism.html#ExplicitCallToCompareToMethod)