Pattern: GString as map key

Issue: -

## Description

A GString should not be used as a map key since its *hashcode* is not guaranteed to be stable. Consider calling `key.toString()`.

Here is an example of code that produces a violation:

``` groovy
Map map = ["${someRef}" : 'invalid' ]       // violation
```

## Further Reading

* [CodeNarc - GStringAsMapKey](https://codenarc.github.io/CodeNarc/codenarc-rules-groovyism.html#gstringasmapkey-rule)