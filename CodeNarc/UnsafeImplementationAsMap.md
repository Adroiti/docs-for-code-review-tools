Pattern: Unsafe implementation as map

Issue: -

## Description

Reports incomplete interface implementations created by map-to-interface coercions.

By default, this rule does not apply to test files.

Example of violations:

``` groovy
[mouseClicked: { ... }] as MouseListener
//not all MouseListener methods are implemented which can lead to UnsupportedOperationException-s
```

## Further Reading

* [CodeNarc - UnsafeImplementationAsMap](http://codenarc.sourceforge.net/codenarc-rules-enhanced.html#UnsafeImplementationAsMap)