Pattern: Unnecessary getter

Issue: -

## Description

Checks for explicit calls to getter/accessor methods which can, for the most part, be replaced by property access. A getter is defined as a method call that matches `get[A-Z]` but not `getClass()` or `get[A-Z][A-Z]` such as `getURL()`. Getters do not take method arguments.

These bits of code produce violations:

``` groovy
x.getProperty()
x.getFirst()
x.getFirstName()
x.getA()
```

These bits of code do not:

``` groovy
x.property
x.first
x.firstName
x.a
x.getURL()
x.getClass()
x.getProperty('key')
```

## Further Reading

* [CodeNarc - UnnecessaryGetter](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessaryGetter)