Pattern: Unnecessary setter

Issue: -

## Description

Checks for explicit calls to setter methods which can, for the most part, be replaced by assignment to property. A setter is defined as a method call that matches set\[A-Z\] but not set\[A-Z\]\[A-Z\] such as `setURL()`. Setters take one method argument.

These bits of code produce violations:

``` groovy
  x.setProperty(1)
  x.setProperty(this.getA())
  x.setProperty([])
```

These bits of code do not:

``` groovy
  x.set(1)
  x.setup(2)
  x.setURL('')
  x.setSomething('arg1', 'arg2')
```

## Further Reading

* [CodeNarc - UnnecessarySetter](http://codenarc.sourceforge.net/codenarc-rules-unnecessary.html#UnnecessarySetter)